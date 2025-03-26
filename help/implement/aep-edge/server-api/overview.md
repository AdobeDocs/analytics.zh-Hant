---
title: 使用Adobe AnalyticsEdge Network伺服器API實作Adobe Experience Platform
description: 使用Adobe Experience PlatformEdge Network伺服器API傳送資料給Adobe Analytics。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 2e5171842794d7acc7bb67048b734f47a438cf1c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 33%

---

# 使用Adobe AnalyticsEdge Network伺服器API實作Adobe Experience Platform

從IoT裝置、機上盒、案頭應用程式等裝置收集資料時，您通常會使用Experience PlatformEdge Network伺服器API來收集伺服器端資料，而非使用者端。 然後，將該資料傳送至Edge網路和Adobe Analytics等服務。

如果您需要安全地收集敏感資料並在整個網路上進行驗證，也請考慮Edge Network伺服器API。 如需詳細資訊，請參閱[驗證](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html)。

實施任務的高層級概觀：

![使用 Analytics 擴充功能工作流程的 Adobe Analytics](../../assets/edge-network-server-api-annotated.png)

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
<td><b>設定結構描述</b>。 為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">結構描述UI總覽</a></td>
</tr>
<tr>
<td>3</td>
<td><b>設定資料流</b>。資料流代表使用Adobe Experience PlatformEdge NetworkAPI的API時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html">設定資料流<a></td> 
</tr>
<tr>
<td>4</td>
<td><b>使用單一事件資料和批次事件資料收集API實作及測試資料收集</b>。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html">單一事件資料集合</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">批次事件資料集合</a>
</tr>
<td>5</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。該服務控制資料是否以及如何發送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=zh-Hant">與Adobe Analytics互動</a></td>
</tr>


</table>

如需詳細資訊，請參閱[Edge Network伺服器API檔案](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=zh-Hant)，以及範例[與Adobe Analytics整合](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=zh-Hant)。

