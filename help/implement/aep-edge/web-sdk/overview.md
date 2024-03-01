---
title: 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Web SDK 擴充功能傳送資料給 Adobe Analytics。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 76%

---

# 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=zh-Hant) 傳送資料給 Adobe Analytics。 此實施方法的運作方式是將[體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 轉譯成 Analytics 所使用的格式。

您可以使用直接將資料傳送至Experience Edge [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/overview.html?lang=en)或透過Tags中的Web SDK擴充功能存取。

## Web SDK

實施任務的高層級概觀：

![如何使用使用Web SDK工作流程實作Adobe Analytics，如本節所述。](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定綱要</b>. 為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
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
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant#option-2%3A-installing-the-prebuilt-standalone-version">安裝預先建立的獨立版本</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant#option-3%3A-using-the-npm-package">使用 NPM 套件</a></td>
</tr>

<tr>
<td>5</td>
<td><b>設定資料流</b>。資料流代表實施 Adobe Experience Platform Web SDK 時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant">設定資料流<a></td> 
</tr>

<td>6</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。此服務可控制資料是否及如何傳送至Adobe Analytics，以及特定要將資料傳送到哪些報表套裝。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant#analytics">將 Adobe Analytics 服務新增到資料流</a></td>
</tr>

<tr>
<td>7</td>
<td><b>設定 Web SDK</b>。請確認您在步驟4安裝的程式庫已正確設定資料串流ID (先前稱為邊緣設定ID (<code>edgeConfigId</code>)，組織id (<code>orgId</code>)，以及其他可用選項。 請確定變數對應正確。 </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant">設定Web SDK</a><br/><a href="https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en">Analytics變數對應</a><br/><a href="https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en">手動對應變數</a></td>
</tr>

<tr>
<td>8</td>
<td><b>執行命令</b> 和/或<b>追蹤事件</b>。在您的網頁上實施基礎程式碼後，您可以開始使用 SDK 執行命令和追蹤事件。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=zh-Hant">執行命令</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant">追蹤事件</a></td>
</tr>

<tr>
<td>9</td><td><b>先擴充和驗證您的實施</b>，再將其投入生產。</td><td></td> 
</tr>
</table>


## Web SDK 擴充功能

實施任務的高層級概觀：

![如何使用使用Web SDK擴充功能工作流程來實作Adobe Analytics，如本節所述。](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定綱要</b>. 為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
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
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=en#embed-code">內嵌程式碼</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant">發佈概觀</a></td>
</tr>

</table>


## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實施中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [Adobe Experience Platform Web SDK 文件](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hant)
