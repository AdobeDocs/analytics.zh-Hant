---
title: 使用 Analytics 擴充功能實施 Adobe Analytics
description: 了解如何使用標記和 Analytics 擴充功能來實施 Adobe Analytics
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/bnn0eqUbhHvQL2YPd1qVa9cSWWvGbAAae33IyC-w9kA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 74%

---

# 使用 Analytics 擴充功能實施 Adobe Analytics

在 Adobe Analytics 的生命週期內，Adobe 提供了數種不同的方式，可在您的網站上實施用於收集資料的程式碼。 Adobe目前的建議方法是透過Adobe Experience Platform中的[標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant)。

Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。 您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。

所有擁有有效Adobe Experience Cloud合約的客戶都可以使用標籤。 如果您不確定您是否擁有存取權，請聯絡貴組織的任一位 Experience Cloud 系統管理員。

實施任務的高層級概觀：



![如何使用Analytics擴充功能工作流程實施Adobe Analytics，如本節所述。](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任務</b></th><th style="width:35%"><b>更多資訊</b></th>
</tr>

<tr>
<td> 1</td>
<td>確定您<b>已定義報表套裝</b>。</td>
<td><a href="../../admin/tools/manage-rs/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td>
<td><b>建立資料層</b>來管理您網站上的資料追蹤。</td>
<td>
<a href="../prepare/data-layer.md">建立資料層</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>建立標籤屬性</b>。 屬性是用於參考標籤管理資料的總體容器。</td>
<td><a href="../launch/create-analytics-property.md">建立 Adobe Analytics 標記屬性</a></td>
</tr>

<tr>
<td>4</td><td>在標記屬性中<b>安裝 Analytics 擴充功能</b>。 設定 Analytics 擴充功能以將資料發送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hant">Adobe Analytics 擴充功能概觀</a></td>
</tr>

<tr>
<td>5</td>
<td><b>部署至開發環境</b>。 有一個讓您可反複進行標籤開發程式的環境。</td>
<td><a href="./deploy-dev.md">將 Analytics 實施部署至開發環境</td>
</tr>

<tr>
<td>6</td> 
<td><b>驗證並發佈至生產環境</b>. 內嵌程式碼，以將您的標籤屬性包含在網站頁面中。 然後使用資料元素、規則等來自訂您的實施。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=zh-Hant#embed-code">內嵌程式碼</a><br/><a href="./validate-publish-prod.md">驗證開發實作並發佈至生產環境</a></td>
</tr>

</table>

## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實施中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [實施變數](../vars/overview.md)：決定您要將哪些變數傳送至資料彙集伺服器。
