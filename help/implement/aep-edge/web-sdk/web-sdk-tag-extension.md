---
title: 使用Web SDK標籤擴充功能將資料傳送至Adobe Analytics
description: 從簡潔的Adobe Experience Platform資料收集實作開始，以便使用XDM和Adobe Analytics ExperienceEvent欄位群組將資料傳送至Adobe Analytics。
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: 316ca1074de36db0d7c9545691e7c6d72a2ed2c4
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 17%

---

# 使用Web SDK標籤擴充功能將資料傳送至Adobe Analytics

此實作路徑牽涉到使用Adobe Experience Platform Data Collection中的標籤的全新Web SDK安裝。 其他實作路徑會在不同頁面上說明：

* [Web SDK JavaScript程式庫](web-sdk-javascript-library.md)：使用Web SDK JavaScript程式庫(`alloy.js`)的全新Web SDK安裝。 類似Web SDK標籤擴充方法（本頁），但您會自行管理實作，而不使用標籤UI。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。
* [Analytics擴充功能改用Web SDK擴充功能](analytics-extension-to-web-sdk.md)：以順暢而有條不紊的方式，從Adobe Analytics標籤擴充功能移至Web SDK標籤擴充功能。 在您的組織準備好使用Adobe Experience Platform服務(例如Customer Journey Analytics)之前，此方法會抑制使用XDM的需求。 使用`data`物件而非`xdm`物件來傳送資料給Adobe。
* [AppMeasurement至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md)：移轉至Web SDK的流暢且有條不紊的方法，但不使用標籤。 請改為手動移除Adobe Analytics資料收集程式庫(`AppMeasurement.js`)，並將其取代為Web SDK JavaScript程式庫(`alloy.js`)。

## 此實作路徑的優缺點

使用Web SDK擴充功能傳送資料給Adobe Analytics有利也有弊。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**最直接的方法**：此實作路徑最直接，通常是新Web SDK實作的建議路徑。 如果您不需擔心目前的Adobe Analytics實作，請填入適用的Web SDK XDM欄位。</li><li>**預先定義的結構描述**：如果您的組織不需要自己的結構描述，您只需使用以Adobe Analytics為根據的結構描述即可。 即使您邁向Customer Journey Analytics，此概念仍適用；prop和eVar的概念不適用於Customer Journey Analytics，但您可以繼續使用prop和eVar作為簡單的自訂維度。</li><li>**無需開發人員介入即可管理標籤**：標籤可讓您管理實作，而不需要開發人員對您的實作進行程式碼變更。 您的開發人員會安裝標籤載入器指令碼，而您可以完全控制資料的收集方式。</li></ul> | <ul><li>**使用特定結構描述鎖定**：當您的組織移至Customer Journey Analytics時，您必須選擇繼續使用Adobe Analytics結構描述，或移轉至您自己的組織結構描述（這將是獨立的資料集）。 如果您的組織想要在移至Customer Journey Analytics時同時避免Adobe Analytics結構描述和移轉至個別的資料集，Adobe建議使用下列兩種方法之一：<ul><li>使用`data`物件： `data`物件可讓您傳送資料給Adobe Analytics，而不符合XDM結構描述。 建立組織的結構描述後，您可以使用資料流對應將`data`物件欄位對應到XDM。 [Analytics擴充功能至Web SDK擴充功能](analytics-extension-to-web-sdk.md)和[AppMeasurement至Web SDK JavaScript程式庫](appmeasurement-to-web-sdk.md)皆使用此`data`物件。</li><li>完全略過Adobe Analytics：如果您正在實作Web SDK，可以將該資料傳送到Adobe Experience Platform中的資料集，以用於Customer Journey Analytics。 您可以使用任何您喜歡的結構描述；Adobe Analytics完全不參與此工作流程，因此不需要Adobe Analytics ExperienceEvent欄位群組。 此方法產生最少的技術債，但也會將Adobe Analytics完全排除在外。</li></ul></ul> |

>[!IMPORTANT]
>
>此實作方法需要您使用為Adobe Analytics設定的結構描述。 如果您的組織計畫在未來使用您自己的方案進行Customer Journey Analytics，使用Adobe Analytics方案可能會對資料管理員或架構師造成混淆。 有幾個選項可以緩解此障礙：
>
>* 您可以在CJA中使用Adobe Analytics結構描述。 請注意，CJA沒有prop或eVar的概念；它們被視為任何其他結構描述欄位。 也請注意，在CJA中使用Adobe Analytics結構描述會使其他平台服務(例如Adobe Journey Optimizer或Real-time Customer Data Platform)的使用更困難。
>* 您可以使用資料物件，類似於移轉工作流程。 請注意，使用資料物件需要將每個資料物件欄位對應到XDM結構描述欄位。
>* 您可以完全略過Adobe Analytics實施，並使用您自己的結構描述傳送資料給Adobe Experience Platform。 這種做法是理想的長期做法，可讓您的組織開始使用Customer Journey Analytics。

## 實作Web SDK標籤擴充功能所需的步驟

實施任務的高層級概觀：

![如何使用Web SDK擴充功能工作流程實作Adobe Analytics，如本節所述。](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定結構描述</b>。 為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">結構描述UI總覽</a></td>
</tr>

<tr>
<td>3</td>
<td><b>建立資料層</b>來管理您網站上的資料追蹤。</td>
<td><a href="../../prepare/data-layer.md">建立資料層</a></td>
</tr>

<tr>
<td>4</td>
<td><b>設定資料流</b>。資料流代表實施 Adobe Experience Platform Web SDK 時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant">設定資料流<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。此服務可控制資料是否及如何傳送至Adobe Analytics，以及特定要將資料傳送到哪些報表套裝。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant#analytics">將 Adobe Analytics 服務新增到資料流</a></td>
</tr>

<tr>
<td>6</td>
<td><b>建立標記屬性</b>。屬性是用來參照標記管理資料的總體容器。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=zh-Hant#for-web">為網路建立或設定標記屬性</a></td>
</tr>

<tr>
<td>7</td> 
<td>在您的標記屬性中<b>安裝和設定 Web SDK 擴衝功能</b>。設定 Web SDK 擴充功能以將資料發送到在步驟 4 中設定的資料流。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=zh-Hant">Adobe Experience Platform Web SDK 擴充功能概觀</a></td>
</tr>

<tr>
<td>8</td>
<td><b>迭代、驗證並發佈</b>至生產環境。內嵌程式碼，以將您的標籤屬性包含在網站頁面中。 然後使用資料元素、規則等來自訂您的實施。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=zh-Hant#embed-code">內嵌程式碼</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant">發佈總覽</a></td>
</tr>

</table>
