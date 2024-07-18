---
title: 使用Web SDK JavaScript資料庫傳送資料給Adobe Analytics
description: 從乾淨的Web SDK實作開始，以便使用JavaScript程式庫傳送資料給Adobe Analytics。
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: 316ca1074de36db0d7c9545691e7c6d72a2ed2c4
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 18%

---

# 使用Web SDK JavaScript資料庫傳送資料給Adobe Analytics

此實作路徑牽涉到使用Web SDK JavaScript程式庫的全新Web SDK安裝。 其他實作路徑會在不同頁面上說明：

* [Web SDK標籤擴充功能](web-sdk-tag-extension.md)：使用Web SDK標籤擴充功能的全新Web SDK安裝。 與Web SDK JavaScript程式庫方法（本頁）類似，但您可以使用Adobe Experience Platform資料收集中的標籤來管理實作。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。
* [Analytics擴充功能改用Web SDK擴充功能](analytics-extension-to-web-sdk.md)：以順暢而有條不紊的方式，從Adobe Analytics標籤擴充功能移至Web SDK標籤擴充功能。 在您的組織準備好使用Adobe Experience Platform服務(例如Customer Journey Analytics)之前，此方法會抑制使用XDM的需求。 使用`data`物件而非`xdm`物件來傳送資料給Adobe。
* [AppMeasurement至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md)：移轉至Web SDK的流暢且有條不紊的方法，但不使用標籤。 您可以手動移除Adobe Analytics資料收集程式庫(`AppMeasurement.js`)，並將其取代為Web SDK JavaScript程式庫(`alloy.js`)。

## 此實作路徑的優缺點

使用Web SDK JavaScript資料庫將資料傳送至Adobe Analytics有利也有弊。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**直接方法**：此實作路徑比移動現有Adobe Analytics實作的方法更直接。 如果您不需擔心目前的Adobe Analytics實作，請填入適用的Web SDK XDM欄位。</li><li>**預先定義的結構描述**：如果您的組織不需要自己的結構描述，您只需使用以Adobe Analytics為根據的結構描述即可。 即使您邁向Customer Journey Analytics，此概念仍適用；prop和eVar的概念不適用於Customer Journey Analytics，但您可以繼續使用prop和eVar作為簡單的自訂維度。</li></ul> | <ul><li>**實作變更需要開發人員介入**：若要變更Web SDK實作，您必須與開發團隊合作，編輯網站上的程式碼。 使用[Web SDK標籤延伸模組](web-sdk-tag-extension.md)的方法可避免此缺點。</li><li>**使用特定結構描述鎖定**：當您的組織移至Customer Journey Analytics時，您必須選擇繼續使用Adobe Analytics結構描述，或移轉至您自己的組織結構描述（這將是獨立的資料集）。 如果您的組織想要在移至Customer Journey Analytics時同時避免Adobe Analytics結構描述和移轉至個別的資料集，Adobe建議使用下列兩種方法之一：</li><ul><li>使用`data`物件： `data`物件可讓您傳送資料給Adobe Analytics，而不符合XDM結構描述。 建立組織的結構描述後，您可以使用資料流對應將`data`物件欄位對應到XDM。 [Analytics擴充功能至Web SDK擴充功能](analytics-extension-to-web-sdk.md)和[AppMeasurement至Web SDK JavaScript程式庫](appmeasurement-to-web-sdk.md)皆使用此`data`物件。</li><li>完全略過Adobe Analytics：如果您正在實作Web SDK，可以將該資料傳送到Adobe Experience Platform中的資料集，以用於Customer Journey Analytics。 您可以使用任何您喜歡的結構描述；Adobe Analytics完全不參與此工作流程，因此不需要Adobe Analytics ExperienceEvent欄位群組。 此方法產生最少的技術債，但也會將Adobe Analytics完全排除在外。</li></ul></ul> |

>[!IMPORTANT]
>
>此實作方法需要您使用為Adobe Analytics設定的結構描述。 如果您的組織計畫在未來使用您自己的方案進行Customer Journey Analytics，使用Adobe Analytics方案可能會對資料管理員或架構師造成混淆。 有幾個選項可以緩解此障礙：
>
>* 您可以在CJA中使用Adobe Analytics結構描述。 請注意，CJA沒有prop或eVar的概念；它們被視為任何其他結構描述欄位。 也請注意，在CJA中使用Adobe Analytics結構描述會使其他平台服務(例如Adobe Journey Optimizer或Real-time Customer Data Platform)的使用更困難。
>* 您可以使用資料物件，類似於移轉工作流程。 請注意，使用資料物件需要將每個資料物件欄位對應到XDM結構描述欄位。
>* 您可以完全略過Adobe Analytics實施，並使用您自己的結構描述傳送資料給Adobe Experience Platform。 這種做法是理想的長期做法，可讓您的組織開始使用Customer Journey Analytics。

## 實作Web SDK JavaScript程式庫所需的步驟

實施任務的高層級概觀：

![如何使用Web SDK工作流程實作Adobe Analytics，如本節所述。](../../assets/websdk-annotated.png)

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
<td> 4</td>
<td><b>安裝預先建立的獨立版本</b>。您可以直接在您的頁面上參考 CDN 上的程式庫 (<code>alloy.js</code>)，或將其下載並託管在您自己的基礎結構上。或者，您可以使用 NPM 套件。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">安裝預先建立的獨立版本</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">使用 NPM 套件</a></td>
</tr>

<tr>
<td>5</td>
<td><b>設定資料流</b>。資料流代表實施 Adobe Experience Platform Web SDK 時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant">設定資料流<a></td> 
</tr>

<td>6</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。此服務可控制資料是否及如何傳送至Adobe Analytics，以及特定要將資料傳送到哪些報表套裝。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">將 Adobe Analytics 服務新增到資料流</a></td>
</tr>

<tr>
<td>7</td>
<td><b>設定 Web SDK</b>。請確認您在步驟4安裝的程式庫已正確設定資料串流ID (先前稱為邊緣組態ID (<code>edgeConfigId</code>))、組織ID (<code>orgId</code>)及其他可用選項。 請確定變數對應正確。 </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">設定Web SDK</a><br/><a href="../xdm-var-mapping.md">XDM物件變數對應</a></td>
</tr>

<tr>
<td>8</td>
<td><b>執行命令</b> 和/或<b>追蹤事件</b>。在您的網頁上實施基礎程式碼後，您可以開始使用 SDK 執行命令和追蹤事件。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">傳送事件</a></td>
</tr>

<tr>
<td>9</td><td><b>先擴充和驗證您的實施</b>，再將其投入生產。</td><td></td> 
</tr>
</table>
