---
title: 使用Adobe Experience Platform Edge Network Server API實作Adobe Analytics
description: 使用Adobe Experience Platform Edge Network Server API傳送資料給Adobe Analytics。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
source-git-commit: 5a57f4d2d73f16a72fbe8b198b1609a8bffc38b6
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 40%

---

# 使用Adobe Experience Platform Edge Network Server API實作Adobe Analytics

您通常會使用Experience PlatformEdge Network Server API從IoT裝置、機上盒、案頭應用程式等裝置收集資料。 然後將該資料傳送至Edge Network，再傳送至Adobe Analytics等服務。

如果您需要安全地收集敏感資料並在整個網路上進行驗證，也請考量邊緣網路伺服器API。 另請參閱 [驗證](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html?lang=en) 以取得詳細資訊。

實施任務的高層級概觀：

![使用 Analytics 擴充功能工作流程的 Adobe Analytics](../../assets/edge-network-server-api.png)

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
<td><b>設定綱要和資料集</b>。為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">綱要 UI 概觀</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant">資料集 UI 概觀</a></td>
</tr>

<tr>
<td>3</td>
<td><b>設定資料流</b>。資料流代表使用Adobe Experience Platform Edge Network API的API時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant">設定資料流<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>實作及測試資料收集</b> 使用單一事件資料和批次事件資料收集API。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en">單一事件資料收集</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en">批次事件資料收集</a>
</tr>

<td>5</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。該服務控制資料是否以及如何發送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ens">與Adobe Analytics互動</a></td>
</tr>


</table>

另請參閱 [Edge Network伺服器API檔案](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=zh-Hant)、和範例 [與Adobe Analytics整合](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=zh-Hant) 以取得詳細資訊。
