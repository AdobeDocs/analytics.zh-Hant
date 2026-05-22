---
title: 使用 Adobe Experience Platform Mobile SDK 實施 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Mobile SDK 擴充功能傳送資料給 Adobe Analytics。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/ooh8s8pNYbbsD9BmF48Nv3OyHN5JtDQonQw0Z1t4XXc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 94%

---

# 使用 Adobe Experience Platform Mobile SDK 實施 Adobe Analytics

Adobe Experience Platform Mobile SDK可協助您在行動應用程式中強化Adobe的CX企業解決方案和服務。 它適用於 Android™、iOS 及各種跨平台開發架構。 透過 Adobe Experience Platform Data Collection 進行設定。

>[!IMPORTANT]
>
>Adobe Analytics 擴充功能也可以在 Adobe Experience Platform Data Collection 中取得。 如果您安裝此擴充功能，就不會利用 XDM 或 Edge Network。

## Adobe Experience Platform SDK

實施任務的高層級概觀：

![使用 Analytics 擴充功能工作流程的 Adobe Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>設定資料流</b>。 資料流代表實施 Adobe Experience Platform Web SDK 時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant">設定資料流<a></td> 
</tr>

<td>3</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。 該服務控制資料是否以及如何發送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant#analytics">將 Adobe Analytics 服務新增到資料流</a></td>
</tr>

<tr>
<td>4</td>
<td><b>建立行動裝置屬性</b>。 屬性是個容器，您可以在其中裝入擴充功能、規則、資料元素和程式庫。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">設定行動裝置屬性</a></tr>

<tr>
<td>5</td>
<td>在行動裝置標記屬性中<b>安裝 Adobe Experience Platform Edge Network 擴充功能</b>，並在擴充功能中設定資料流。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>6</td>
<td><b>在您的應用程式中使用程式碼</b>來註冊必要的擴充功能，並載入您的標記設定。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定配置</a></td>
</tr>

<tr>
<td>7</td>
<td>在您的應用程式中使用標記的資料元素、規則、附加擴充功能和 SDK API 呼叫組合，來<b>實施和測試功能</b>。 檢查、驗證和偵錯行動應用程式的資料彙集和體驗。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用範例應用程式</a>
</tr>

<tr>
<td>8</td>
<td><b>先擴充和驗證您的行動應用程式實施</b>，再將其投入生產。</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 擴充功能。

實施任務的高層級概觀：

![使用 Analytics 擴充功能工作流程的 Adobe Analytics](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td>在行動裝置標記屬性中<b>安裝 Adobe Analytics 擴充功能</b>，並將擴充功能設定為指向您的報表套裝。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">適用於行動裝置屬性的 Adobe Analytics 擴充功能</a>
</tr>

<tr>
<td>3</td>
<td><b>在您的應用程式中使用程式碼</b>來註冊必要的擴充功能，並載入您的標記設定。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定配置</a></td>
</tr>

<tr>
<td>4</td>
<td>在您的應用程式中使用標記的資料元素、規則、附加擴充功能和 SDK API 呼叫組合，來<b>實施和測試功能</b>。 檢查、驗證和偵錯行動應用程式的資料彙集和體驗。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用範例應用程式</a>
</tr>

<tr>
<td>5</td>
<td><b>先擴充和驗證您的行動應用程式實施</b>，再將其投入生產。</td>
<td></td> 
</tr>

</table>

## 其他資源

- [標籤檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant#)

- [行動SDK檔案](https://developer.adobe.com/client-sdks/documentation/)
