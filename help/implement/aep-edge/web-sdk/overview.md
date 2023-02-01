---
title: 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Web SDK 擴充功能傳送資料給 Adobe Analytics。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 27%

---

# 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) 傳送資料給 Adobe Analytics。 此實作方法的運作方式是將[體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 轉譯成 Analytics 所使用的格式。

您可以直接使用Web SDK或透過「標籤」中的Web SDK擴充功能，將資料傳送至Experience Edge。

## Web SDK

實作工作的概觀：

![使用Web SDK工作流程實作Adobe Analytics](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>工作</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確保您 <b>定義報表套裝</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定結構和資料集</b>. 為了標準化資料收集，以便在運用Adobe Experience Platform的應用程式間使用，Adobe建立了開放且公開記錄的標準Experience Data Model(XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">結構描述UI概述</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant">資料集UI概觀</a></td>
</tr>

<tr>
<td>3</td>
<td><b>建立資料層</b> 管理網站上資料的追蹤。</td>
<td><a href="../../prepare/data-layer.md">建立資料層</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>安裝預先建置的獨立版本</b>. 您可以參考程式庫(<code>alloy.js</code>)，或下載並托管於您自己的基礎架構上。 或者，您也可以使用NPM套件。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">安裝預先建置的獨立版本</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">使用NPM套件</a></td>
</tr>

<tr>
<td>5</td>
<td><b>設定資料流</b>. 資料流代表實作Adobe Experience Platform Web SDK時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">設定資料流<a></td> 
</tr>

<td>6</td>
<td><b>新增Adobe Analytics服務</b> 資料流。 該服務會控制資料是否以及如何傳送至Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">將Adobe Analytics服務新增至資料流</a></td>
</tr>

<tr>
<td>7</td>
<td><b>配置Web SDK</b>. 請確定您在步驟4安裝的程式庫已正確設定資料流ID（先前稱為邊緣設定ID）(<code>edgeConfigId</code>)，組織id(<code>orgId</code>)和其他可用選項。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en">配置Web SDK</a></td>
</tr>

<tr>
<td>8</td>
<td><b>執行命令</b> 和/或 <b>追蹤事件</b>. 在您的網頁上實作基礎程式碼後，您就可以開始使用SDK執行命令及追蹤事件。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">執行命令</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">追蹤事件</a></td>
</tr>

<tr>
<td>9</td><td><b>擴充及驗證實作</b> 再推出生產。</td><td></td> 
</tr>
</table>


## Web SDK擴充功能

實作工作的概觀：

![使用Web SDK擴充功能工作流程實作Adobe Analytics](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>工作</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確保您 <b>定義報表套裝</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定結構和資料集</b>. 為了標準化資料收集，以便在運用Adobe Experience Platform的應用程式間使用，Adobe建立了開放且公開記錄的標準Experience Data Model(XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">結構描述UI概述</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant">資料集UI概觀</a></td>
</tr>

<tr>
<td>3</td>
<td><b>建立資料層</b> 管理網站上資料的追蹤。</td>
<td><a href="../../prepare/data-layer.md">建立資料層</a></td>
</tr>

<tr>
<td>4</td>
<td><b>設定資料流</b>. 資料流代表實作Adobe Experience Platform Web SDK時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">設定資料流<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>新增Adobe Analytics服務</b> 資料流。 該服務會控制資料是否以及如何傳送至Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">將Adobe Analytics服務新增至資料流</a></td>
</tr>

<tr>
<td>6</td>
<td><b>建立標籤屬性</b>.屬性是用於參考標籤管理資料的整體容器。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">建立或設定Web的標籤屬性</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>安裝及設定Web SDK擴充功能</b> 在標籤屬性中。 設定Web SDK擴充功能，將資料傳送至步驟4中設定的資料流。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Adobe Experience Platform Web SDK擴充功能概述</a></td>
</tr>

<tr>
<td>8</td>
<td><b>迭代、驗證和發佈</b> 生產。 將標籤屬性新增至您的網站。 然後使用資料元素、規則等來自訂您的實作。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en">發佈概觀</a></td>
</tr>

</table>


## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實作中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [Adobe Experience Platform Web SDK檔案](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hant)
