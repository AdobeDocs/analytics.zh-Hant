---
title: 使用 Adobe Experience Platform Mobile SDK 實作 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Mobile SDK 擴充功能傳送資料給 Adobe Analytics。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 28%

---

# 使用 Adobe Experience Platform Mobile SDK 實作 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助於在行動應用程式中強化 Adobe 的 Experience Cloud 解決方案和服務。 適用於Android™、iOS和各種跨平台開發架構。 透過 Adobe Experience Platform Data Collection 進行設定。
>[!IMPORTANT]
>
>Adobe Analytics 擴充功能也可以在 Adobe Experience Platform Data Collection 中取得。如果您安裝此擴充功能，就不會利用 XDM 或 Edge Network。

## Adobe Experience Platform SDK

實作工作的概觀：

![Adobe Analytics使用Analytics擴充功能工作流程](../../assets/mobilesdk-annotated.png)

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
<td><b>設定資料流</b>. 資料流代表實作Adobe Experience Platform Web SDK時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">設定資料流<a></td> 
</tr>

<td>4</td>
<td><b>新增Adobe Analytics服務</b> 資料流。 該服務會控制資料是否以及如何傳送至Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">將Adobe Analytics服務新增至資料流</a></td>
</tr>

<tr>
<td>5</td>
<td><b>建立行動屬性</b>. 屬性是一個容器，您在其中填入擴充功能、規則、資料元素和程式庫。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">設定行動屬性</a></tr>

<tr>
<td>6</td>
<td><b>安裝Adobe Experience Platform Edge Network擴充功能</b> 在行動標籤屬性中，並在擴充功能中設定資料流。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>在您的應用程式中使用程式碼</b> 來註冊必要的擴充功能並載入您的標籤設定。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定設定</a></td>
</tr>

<tr>
<td>8</td>
<td><b>實作和測試功能</b> 在應用程式中結合使用標籤的資料元素、規則、其他擴充功能及SDK API呼叫。 Inspect、驗證並除錯行動應用程式的資料收集和體驗。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用範例應用程式</a>
</tr>

<tr>
<td>9</td>
<td><b>延伸及驗證您的行動應用程式實作</b> 再推出生產。</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 擴充功能.

實作工作的概觀：

![Adobe Analytics使用Analytics擴充功能工作流程](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>安裝Adobe Analytics擴充功能</b> 在行動標籤屬性中，並設定指向您報表套裝的擴充功能。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Adobe Analytics行動屬性擴充功能</a>
</tr>

<tr>
<td>4</td>
<td><b>在您的應用程式中使用程式碼</b> 來註冊必要的擴充功能並載入您的標籤設定。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定設定</a></td>
</tr>

<tr>
<td>5</td>
<td><b>實作和測試功能</b> 在應用程式中結合使用標籤的資料元素、規則、其他擴充功能及SDK API呼叫。 Inspect、驗證並除錯行動應用程式的資料收集和體驗。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用範例應用程式</a>
</tr>

<tr>
<td>6</td>
<td><b>延伸及驗證您的行動應用程式實作</b> 再推出生產。</td>
<td></td> 
</tr>

</table>

## 其他資源

- [標籤檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)

- [Mobile SDK 文件](https://developer.adobe.com/client-sdks/documentation/)



