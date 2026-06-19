---
title: Data Warehouse的元件支援
description: 瞭解當您建置Data Warehouse請求時可以使用哪些維度和量度，哪些無法使用，以及哪些維度和量度的行為不同。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Data Warehouse 中的元件支援

本頁說明您在建立Data Warehouse請求時可使用的維度和量度。 區段包含哪些元件可供使用、哪些元件無法使用，以及哪些元件的行為與其他Adobe Analytics工具中不同。

## Data Warehouse專屬的維度

下列維度可用於Data Warehouse，但不可用於其他Adobe Analytics功能。

* [[!UICONTROL Experience Cloud訪客ID]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL IP位址]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL 頁面 URL]](/help/components/dimensions/page-url.md)
* [[!UICONTROL 購買ID]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL 訪客 ID]](/help/components/dimensions/visitor-id.md)

## 不支援的維度

下列維度無法在Data Warehouse報表或區段中使用：

* [[!UICONTROL 上午/下午]](/help/components/dimensions/am-pm.md)
* 除[[!UICONTROL 登入頁面]](/help/components/dimensions/entry-dimensions.md)和[[!UICONTROL 原始登入頁面]](/help/components/dimensions/entry-dimensions.md)之外允許的所有登入維度
* 除了允許的[[!UICONTROL 退出頁面]](/help/components/dimensions/exit-dimensions.md)和[[!UICONTROL 退出連結]](/help/components/dimensions/exit-link.md)之外，所有退出維度
* [[!UICONTROL 點選深度]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL 回訪頻率]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL 事件之前時間]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL 頁面逗留時間 — 分段]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL 每次造訪逗留時間 — 分段]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL 所有搜尋頁面排名]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL 階層]](/help/components/dimensions/overview.md#retired-dimensions)變數
* [[!UICONTROL 點擊類型]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL 付費搜尋]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL 單頁存取次數]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL 追蹤選擇退出原因]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL 美國州]](/help/components/dimensions/us-states.md)

有些維度可在Data Warehouse請求中使用，但無法用於區段內。 如需詳細資訊，請參閱[Data Warehouse區段相容性](segment-compatibility.md)。

## 具有非標準日期格式的維度

Data Warehouse報表支援下列以時間為基礎的維度，但其輸出使用非標準格式：

* [[!UICONTROL 年]](/help/components/dimensions/year.md)
* [[!UICONTROL 季度]](/help/components/dimensions/quarter.md)
* [[!UICONTROL 月]](/help/components/dimensions/month.md)
* [[!UICONTROL 週]](/help/components/dimensions/week.md)
* [[!UICONTROL 日]](/help/components/dimensions/day.md)
* [[!UICONTROL 小時]](/help/components/dimensions/hour.md)
* [[!UICONTROL 分鐘]](/help/components/dimensions/minute.md)

日期值以`1YYMMDDHHMM`格式輸出：

* **年(YY)**：位移1900。 將`1900`加到前三位數。 例如，`125` =年&#x200B;**2025**。
* **月**：以零為基礎。 一月= `00`，二月= `01`， ...，十二月= `11`。

例如，如果日期範圍周欄位顯示`1260901`，則年份是1900 + 126 = **2026**，而月份是09 = **10月**。

## Data Warehouse中定義不同的量度

* **[[!UICONTROL 瀏覽次數]](/help/components/metrics/visits.md)**：排除非永久性Cookie瀏覽次數，不同於其他Adobe Analytics工具中的瀏覽次數量度。
* **[[!UICONTROL 造訪 — 所有訪客]](/help/components/metrics/visits.md)**：計算所有訪客，包含具有非永久性Cookie的訪客，使其更接近於Adobe Analytics其他位置的標準[!UICONTROL 造訪]量度。

## 不支援的量度

下列量度無法在Data Warehouse中使用：

* [[!UICONTROL 退回]](/help/components/metrics/bounces.md)
* [[!UICONTROL 登入]](/help/components/metrics/entries.md)
* [[!UICONTROL 退出]](/help/components/metrics/exits.md)
* [[!UICONTROL 重新載入]](/help/components/metrics/reloads.md)
* [[!UICONTROL 單次存取]](/help/components/metrics/single-access.md)
* 任何[[!UICONTROL 逗留時間]](/help/components/metrics/time-spent.md)量度
* 任何使用[參與率](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)歸因模型的量度
