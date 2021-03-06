---
description: 當報表中有許多不重複值時，Adobe 會使用低流量維度項目來提高報表效能。
title: Adobe Analytics 中的低流量值
feature: Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: ddd1473ccfe27dbcb28c0c51992628c9bf03cb5c
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---

# Adobe Analytics 中的低流量值

當報表中有大量不重複值時，Adobe 提供的功能可確保最重要的值出現在您的報表中。在約 500,000 個現有值之後收集的不重複變數值會列在標示為「**[!UICONTROL 低流量]**」的維度項目底下。

## [!UICONTROL 低流量]的運作方式

* 如果指定月份中變數未達到 500,000 個不重複值，則不會影響報表。
* 當變數達到 500,000 個不重複值時，數值會開始貯存在「[!UICONTROL 低流量]」底下超過此臨界值的每個值都會依照下列邏輯執行後續作業：
   * 如果值已存在於報表中，則照常新增該值。
   * 如果報表中尚未看到某個值，這個值原先是貯存在「[!UICONTROL 低流量]」維度項目中。
   * 如果貯存在「[!UICONTROL 低流量]」底下的值收到大批流量 (通常一天收到兩位數的執行個體) 時，該值開始會被識別為是其本身的維度項目。在達到臨界值之前收集的執行個體仍然會留在「[!UICONTROL 低流量]」底下。正確臨界值有許多相依性，例如處理該報告套裝資料的伺服器數量，以及每個維度項目執行個體之間的時間長度。
* 如果報告套裝達到超過 1,000,000 個不重複值，則套用更嚴格的篩選條件。不重複值在被識別為其本身的維度項目之前，需要在一天內收到三位數的執行個體。

此邏輯允許 Adobe 進行報告功能最佳化，同時仍然允許您的組織報告本月稍後收集的重要維度項目。例如，您的組織執行一個有數百萬篇文章的網站，其中有一篇新文章在月底成為熱門項目 (在超過兩個不重複的臨界值之後)。您仍然可以分析該文章的表現，而不必理會該文章是貯存在「[!UICONTROL 低流量]」底下。此邏輯的用意並非解除每天或每月獲得一定頁面檢視次數的所有內容。

>[!NOTE]
>[頁面](../components/dimensions/page.md)維度會使用所有計入不重複臨界值的多個後端列，包含`pagename`、`page_url`、`first_hit_pagename`、`first_hit_page_url`、`visit_pagename`、`visit_page_url` 和 `click_context`。工作區內的不重複頁面維度項目數量達到 500,000 以前，這些後端列可能會讓系統妥善套用「[!UICONTROL 低流量]」邏輯。

## 變更不重複限制臨界值

這些臨界值限制預設為 500,000 和 100 萬個唯一值。這些限制可依各變數變更。聯絡 Adobe 客戶服務或組織的客戶經理，以便提出這項變更要求。要求變更時，請提供以下資料：

* 報告套裝 ID
* 您想要提高臨界值的變數
* 需要的第一臨界值和第二臨界值

變更臨界值可能會影響報表效能。Adobe 強烈建議，要求增加某變數中的不重複值時，務必做出正確的判斷。只有對您組織報表需求的重要變數提高不重複的限制。

Analytics UI 中不會顯示低流量臨界值。如果您想取得現有臨界值的更多資訊，請聯絡 Adobe 客戶服務。

## 使用元件和其他功能的低流量

不同的功能可能會以不同的方式處理低流量值。

* **Data Warehouse：** Data Warehouse 報表中的不重複值數目沒有限制。其獨特的架構可將任意數目的不重複值納入報表中。
   * 在某些有限的情況下，低流量值仍可能顯示。範例包括清單變數、清單 prop、銷售 eVar 和行銷管道詳細資訊維度。
* **分段：**&#x200B;如果區段準則包含具有大量不重複值的變數，則不會包含低流量底下擷取的值。
* **分類：**&#x200B;分類報表也受到不重複限制的約束。如果分類的上層變數值包含在低流量底下，則不會分類該值。
   * 若是透過匯入工具取得的低流量分類值，您可在 Data Warehouse 中查看。<!-- AN-115871 -->
   * 若是透過規則產生器取得的低流量分類值，*無法*&#x200B;在 Data Warehouse 中查看。<!-- AN-122872 -->
