---
title: 使用Adobe Experience Platform Edge Network API實作Adobe Analytics
description: 使用Adobe Experience Platform Edge Network API傳送資料給Adobe Analytics。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg
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
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 42%

---

# 使用Adobe Experience Platform Edge Network API實作Adobe Analytics

從IoT裝置、機上盒和案頭應用程式等裝置收集資料時，您通常使用Experience Platform Edge Network API在伺服器端而非使用者端收集資料。 然後，將該資料傳送至Edge網路和Adobe Analytics等服務。

如果您需要安全地收集敏感資料並透過網路驗證，也請考慮Edge Network API。 如需詳細資訊，請參閱[驗證](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html)。

實施任務的高層級概觀：

![使用 Analytics 擴充功能工作流程的 Adobe Analytics](../../assets/edge-network-server-api-annotated.png)

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
<td><b>設定結構描述</b>。 為了標準化資料彙集以跨利用 Adobe Experience Platform 的應用程式使用，Adobe 建立了開放且公開記錄標準，即體驗資料模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant">結構描述UI總覽</a></td>
</tr>

<tr>
<td>3</td>
<td><b>設定資料流</b>。 資料流代表使用Adobe Experience Platform Edge Network API的API時的伺服器端設定。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html">設定資料流<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>使用單一事件資料和批次事件資料收集API實作及測試資料收集</b>。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=zh-Hant">單一事件資料集合</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">批次事件資料集合</a>
</tr>

<td>5</td>
<td><b>將 Adobe Analytics 服務</b>新增到您的資料流。 該服務控制資料是否以及如何發送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=zh-Hant">與Adobe Analytics互動</a></td>
</tr>


</table>

如需詳細資訊，請參閱[Edge Network API檔案](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=zh-Hant)。

