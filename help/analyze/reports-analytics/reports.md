---
title: 報表
description: Reports & Analytics 用於每個報表的維度和量度。
feature: 報表 & Analytics 基本知識
role: Business Practitioner, Administrator
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '1866'
ht-degree: 100%

---

# 報表

Reports &amp; Analytics 中的每個報表都使用專用的維度和預設量度。您可以變更每個報表中的量度，並可視需要新增劃分。下列清單提供每個報表所使用的維度。

>[!NOTE]
>
>您的報表功能表可能會根據組織的管理員所做的自訂而有所不同。請參閱「管理員使用指南」中的[功能表自訂](/help/admin/admin/customize-menus.md)。

## 網站量度

包含通常會使用日期範圍分析趨勢的報表。此外也包含獨特報表，例如「建議」報表和「即時」報表。

* 我的建議報表：建立包含數個小報表的控制面板，以立即進行深入分析。
* 關鍵量度：一次最多可讓您對 5 個量度分析趨勢的報表。依預設會分析[頁面檢視](/help/components/metrics/page-views.md)、[造訪](/help/components/metrics/visits.md)和[不重複訪客](/help/components/metrics/unique-visitors.md)的趨勢。
* 頁面檢視：分析[頁面檢視](/help/components/metrics/page-views.md)量度在一段時間內的趨勢。
* 造訪：分析[造訪](/help/components/metrics/visits.md)量度在一段時間內的趨勢。
* 訪客：分析多個[不重複訪客](/help/components/metrics/unique-visitors.md)量度在一段時間內的趨勢。
   * 不重複訪客：訪客在選取的整個日期範圍內僅計數一次。
   * 每小時不重複訪客：如果訪客在所選日期範圍內的不同時數造訪，則會計入多次。
   * 每日不重複訪客：如果訪客在所選日期範圍內的不同日期造訪，則會計入多次。
   * 每週不重複訪客：如果訪客在所選日期範圍內的不同週別造訪，則會計入多次。
   * 每月不重複訪客：如果訪客在所選日期範圍內的不同月份造訪，則會計入多次。
   * 每季不重複訪客：如果訪客在所選日期範圍內的不同季度造訪，則會計入多次。季度包括 1 月至 3 月、4 月至 6 月、7 月至 9 月和 10 月至 12 月。
   * 每年不重複訪客：如果訪客在所選日期範圍內的不同日曆年度造訪，則會計入多次。
* 每次造訪逗留時間：使用[每次造訪逗留時間 - 分段](/help/components/dimensions/time-spent-per-visit.md)維度。
* 事件之前時間：使用[事件之前時間](/help/components/dimensions/time-prior-to-event.md)維度。
* 購買：包含購買相關量度的報表。
   * 購買轉換漏斗：報告漏斗報表中的[造訪](/help/components/metrics/visits.md)、[購物車](/help/components/metrics/carts.md)、[訂單](/help/components/metrics/orders.md)、[收入](/help/components/metrics/revenue.md)和[件數](/help/components/metrics/units.md)的相關資訊。Analysis Workspace 中會使用[「流失」視覺效果](../analysis-workspace/visualizations/fallout/fallout-flow.md)達到類似的視覺效果。
   * 收入：分析[收入](/help/components/metrics/revenue.md)量度在一段時間內的趨勢。
   * 訂單：分析[訂單](/help/components/metrics/orders.md)量度在一段時間內的趨勢。
   * 件數：分析[件數](/help/components/metrics/units.md)量度在一段時間內的趨勢。
* 購物車：包含關於購物車量度的報表。
   * 購物車轉換漏斗：報告漏斗報表中的[例項](/help/components/metrics/instances.md)、[購物車](/help/components/metrics/carts.md)、[結帳](/help/components/metrics/checkouts.md)、[訂單](/help/components/metrics/orders.md)和[收入](/help/components/metrics/revenue.md)的相關資訊。
   * 購物車：分析[購物車](/help/components/metrics/carts.md)量度在一段時間內的趨勢。
   * 購物車檢視：分析[購物車檢視](/help/components/metrics/cart-views.md)量度在一段時間內的趨勢。
   * 購物車新增：分析[購物車新增](/help/components/metrics/cart-additions.md)量度在一段時間內的趨勢。
   * 購物車移除：分析[購物車移除](/help/components/metrics/cart-removals.md)量度在一段時間內的趨勢。
   * 結帳：分析[結帳](/help/components/metrics/checkouts.md)量度在一段時間內的趨勢。
* 自訂事件：包含與您的實施特有的自訂[事件](/help/components/metrics/custom-events.md)有關的所有報表。
* 機器人：顯示機器人相關報表。
   * 機器人：顯示最頻繁造訪您網站的機器人。請參閱「管理員使用指南」中的[機器人規則](../../admin/admin/bot-removal/bot-rules.md)。
   * 機器人頁面：顯示機器人點擊最多次的頁面。
* 即時：在資料收集後的數秒內顯示特定維度和量度。如需詳細資訊，請參閱[即時報表](/help/components/c-real-time-reporting/realtime.md)。

## 網站內容

包含通常會顯示網站內容之維度的相關報表。您可以對其中一些報表套用分類。若套用分類，表示報表會變成包含來源報表和分類報表的功能表。

* 頁面：使用[頁面](/help/components/dimensions/page.md)維度。
* 網站區段：使用[網站區段](/help/components/dimensions/site-section.md)維度。
* 伺服器：使用[伺服器](/help/components/dimensions/server.md)維度。
* 連結：包含使用連結追蹤的報表。
   * 退出連結：使用[退出連結](/help/components/dimensions/exit-link.md)維度。
   * 檔案下載：使用[檔案下載](/help/components/dimensions/download-link.md)維度。
   * 自訂連結：使用[自訂連結](/help/components/dimensions/custom-link.md)維度。
   * 找不到頁面：使用[找不到頁面](/help/components/dimensions/pages-not-found.md)維度。

## 行動

包含舊版行動報表的相關報表。這些報表的資料以使用者代理字串為基礎。其各自的報表中會使用各種[行動維度](/help/components/dimensions/mobile-dimensions.md)。

* 裝置：使用[行動裝置](/help/components/dimensions/mobile-dimensions.md)維度。
* 裝置類型：使用[行動裝置類型](/help/components/dimensions/mobile-dimensions.md)維度。
* 製造商：使用[行動製造商](/help/components/dimensions/mobile-dimensions.md)維度。
* 螢幕大小：使用[行動螢幕大小](/help/components/dimensions/mobile-dimensions.md)維度。
* 螢幕高度：使用[行動螢幕高度](/help/components/dimensions/mobile-dimensions.md)維度。
* 螢幕寬度：使用[行動螢幕寬度](/help/components/dimensions/mobile-dimensions.md)維度。
* Cookie 支援：使用[行動 Cookie 支援](/help/components/dimensions/mobile-dimensions.md)維度。
* 影像支援：使用[行動影像支援](/help/components/dimensions/mobile-dimensions.md)維度。
* 色彩深度：使用[行動色彩深度](/help/components/dimensions/mobile-dimensions.md)維度。
* 音訊支援：使用[行動音訊支援](/help/components/dimensions/mobile-dimensions.md)維度。
* 視訊支援：使用[行動視訊支援](/help/components/dimensions/mobile-dimensions.md)維度。
* 作業系統 (已淘汰)：使用[行動作業系統 (已淘汰)](/help/components/dimensions/mobile-dimensions.md) 維度。

## 路徑

包含可讓您查看訪客路徑資料的報表。

* 下一頁流量：使用上層頁面維度項目的流量報表。路徑檢視與[例項](/help/components/metrics/instances.md)類似。您可以變更報告的維度項目。Analysis Workspace 中使用[流量視覺效果](../analysis-workspace/visualizations/c-flow/flow.md)提供了類似報表。
* 下一頁：取用上層頁面維度項目，並顯示訪客瀏覽的後續頁面。
* 上一頁流量：使用上層頁面維度項目的流量報表。Analysis Workspace 中使用[流量視覺效果](../analysis-workspace/visualizations/c-flow/flow.md)提供了類似報表。
* 上一頁：取用上層頁面維度項目，並顯示訪客先前瀏覽過的頁面。
* 流失：可讓您選取步驟中的頁面維度項目，且會顯示依照和未依照該路徑瀏覽的訪客比例。Analysis Workspace 中使用[流失視覺效果](../analysis-workspace/visualizations/fallout/fallout-flow.md)提供了類似報表。
* 完整路徑：將個別路徑顯示為維度項目。Analysis Workspace 已淘汰此功能；請改用[流量視覺效果](../analysis-workspace/visualizations/c-flow/flow.md) 。
* PathFinder：提供多種報表類型讓您分析路徑 (Analysis Workspace 已淘汰此功能)。
* 路徑長度：使用[造訪深度](/help/components/dimensions/visit-depth.md)維度。
* 頁面分析
   * 頁面摘要：取用上層頁面維度項目，並顯示趨勢檢視。此外也會顯示該上層頁面維度項目的登入點、先前的頁面、退出點和後續頁面。
   * 重新載入：搭配使用[頁面](/help/components/dimensions/page.md)維度和[重新載入](/help/components/metrics/reloads.md)量度。
   * 頁面逗留時間：使用[頁面逗留時間 - 分段](/help/components/dimensions/time-spent-on-page.md)維度。
   * 進入頁面點按次數：取用上層頁面維度項目，並顯示在指定造訪中到達該頁面所花費的點按次數。
* 登入與退出
   * 登入頁面：使用[登入頁面](/help/components/dimensions/entry-dimensions.md)維度。
   * 原始登入頁面：使用[原始登入頁面](/help/components/dimensions/entry-dimensions.md)維度。
   * 單頁造訪次數：使用[頁面](/help/components/dimensions/page.md)維度，並套用 Adobe 提供的「單頁造訪次數」區段。
   * 退出頁面：使用[退出頁面](/help/components/dimensions/exit-dimensions.md)維度。

>[!NOTE]
>
>其他報表也可能顯示在此資料夾中。這是其他維度 (例如 Prop)，可讓您在報表套裝設定下[啟用路徑分析](../../admin/admin/c-traffic-variables/traffic-var.md)。

## 流量來源

包含可讓您深入分析訪客在到達您的網站前經過何處的報表。您必須在報表套裝設定下正確設定[內部 URL 篩選器](../../admin/admin/internal-url-filter-admin.md)，這些報表才可正常運作。

* 搜尋關鍵字 - 全部：使用[搜尋關鍵字](/help/components/dimensions/search-keyword.md)維度。
* 搜尋關鍵字 - 付費：使用[搜尋關鍵字 - 付費](/help/components/dimensions/search-keyword.md)維度。
* 搜尋關鍵字 - 免費：使用[搜尋關鍵字 - 免費](/help/components/dimensions/search-keyword.md)維度。
* 搜尋引擎 - 全部：使用[搜尋引擎](/help/components/dimensions/search-engine.md)維度。
* 搜尋引擎 - 付費：使用[搜尋引擎 - 付費](/help/components/dimensions/search-engine.md)維度。
* 搜尋引擎 - 免費：使用[搜尋引擎 - 免費](/help/components/dimensions/search-engine.md)維度。
* 所有搜尋頁面排名：使用[所有搜尋頁面排名](/help/components/dimensions/all-search-page-rank.md)維度。
* 反向連結網域：使用[反向連結網域](/help/components/dimensions/referring-domain.md)維度
* 原始反向連結網域：使用[原始反向連結網域](/help/components/dimensions/original-referring-domain.md)維度
* 反向連結：使用[反向連結](/help/components/dimensions/referrer.md)維度。
* 反向連結類型：使用[反向連結類型](/help/components/dimensions/referrer-type.md)維度。

## 行銷活動

主要包含以[追蹤代碼](/help/components/dimensions/tracking-code.md)維度為主的報表。

* 行銷活動轉換漏斗：報告漏斗報表中的點進次數、[結帳](/help/components/metrics/checkouts.md)、[訂單](/help/components/metrics/orders.md)和[收入](/help/components/metrics/revenue.md)的相關資訊。點進次數量度與[追蹤代碼](/help/components/dimensions/tracking-code.md)維度內容中的[例項](/help/components/metrics/instances.md)量度類似。Analysis Workspace 中會使用[「流失」視覺效果](../analysis-workspace/visualizations/fallout/fallout-flow.md)達到類似的視覺效果。
* 追蹤代碼：使用[追蹤代碼](/help/components/dimensions/tracking-code.md)維度。

## 產品

主要包含以[產品](/help/components/dimensions/product.md)維度為主的報表。

* 產品轉換漏斗：報告漏斗報表中的[產品檢視](/help/components/metrics/product-views.md)、[購物車新增](/help/components/metrics/cart-additions.md)、[結帳](/help/components/metrics/checkouts.md)、[訂單](/help/components/metrics/orders.md)、[件數](/help/components/metrics/units.md)和[收入](/help/components/metrics/revenue.md)的相關資訊。Analysis Workspace 中會使用[「流失」視覺效果](../analysis-workspace/visualizations/fallout/fallout-flow.md)達到類似的視覺效果。
* 產品：使用[產品](/help/components/dimensions/product.md)維度。
* 交叉銷售：顯示通常會一起銷售的產品 (Analysis Workspace 已淘汰此功能)。
* 類別：使用[類別](/help/components/dimensions/category.md)維度。

## 訪客保留率

包含與回訪網站的訪客有關的報表。

* 回訪頻率：使用[回訪頻率](/help/components/dimensions/return-frequency.md)維度。
* 回訪：套用 Adobe 提供的「回訪」區段，分析[造訪](/help/components/metrics/visits.md)量度在一段時間內的趨勢。
* 造訪次數：使用[造訪次數](/help/components/dimensions/visit-number.md)維度。
* 銷售週期：購買相關報表的資料夾。
   * 客戶忠誠度：使用[客戶忠誠度](/help/components/dimensions/customer-loyalty.md)維度。
   * 首次購買間隔天數：使用[首次購買間隔天數](/help/components/dimensions/days-before-first-purchase.md)維度。
   * 上次購買間隔天數：使用[上次購買間隔天數](/help/components/dimensions/days-since-last-purchase.md)維度。
   * 每日獨特客戶：套用 Adobe 提供的「購買者」區段，分析[每日不重複訪客](/help/components/metrics/unique-visitors.md)在一段時間內的趨勢。
   * 每週獨特客戶：套用 Adobe 提供的「購買者」區段，分析[每週不重複訪客](/help/components/metrics/unique-visitors.md)在一段時間內的趨勢。
   * 每月獨特客戶：套用 Adobe 提供的「購買者」區段，分析[每月不重複訪客](/help/components/metrics/unique-visitors.md)在一段時間內的趨勢。
   * 每季獨特客戶：套用 Adobe 提供的「購買者」區段，分析[每季不重複訪客](/help/components/metrics/unique-visitors.md)在一段時間內的趨勢。季度包括 1 月至 3 月、4 月至 6 月、7 月至 9 月和 10 月至 12 月。
   * 每年獨特客戶：套用 Adobe 提供的「購買者」區段，分析[每年不重複訪客](/help/components/metrics/unique-visitors.md)在一段時間內的趨勢。

## 訪客設定檔

包含您的網站訪客的相關報表。

* 地域劃分：關於您的網站訪客來自哪些地域的報表。
   * 國家：使用[國家](/help/components/dimensions/countries.md)維度。
   * 地區：使用[地區](/help/components/dimensions/regions.md)維度。
   * 城市：使用[城市](/help/components/dimensions/cities.md)維度。
   * 美國州：使用[美國州](/help/components/dimensions/us-states.md)維度。
   * 美國 DMA：使用[美國 DMA](/help/components/dimensions/us-dma.md) 維度。
* 語言：使用[語言](/help/components/dimensions/language.md)維度。
* 時區：使用時區維度 (Analysis Workspace 已淘汰此功能)。維度項目是點擊時的時間 (以 GMT 時差表示)。
* 網域：使用[網域](/help/components/dimensions/domain.md)維度。
* 上層網域：使用上層網域維度 (Analysis Workspace 已淘汰此功能)。這會將[網域](/help/components/dimensions/domain.md)維度分組為較高層級的類別，通常依網域的所在國家/地區分組。
* 技術：包含報表的資料夾，這類報表說明訪客用哪些方式存取您的網站。
   * 瀏覽器：使用[瀏覽器](/help/components/dimensions/browser.md)維度。
   * 瀏覽器類型：使用[瀏覽器類型](/help/components/dimensions/browser-type.md)維度。
   * 瀏覽器寬度：使用[瀏覽器寬度 - 分段](/help/components/dimensions/browser-width.md)維度。
   * 瀏覽器高度：使用[瀏覽器高度 - 分段](/help/components/dimensions/browser-height.md)維度。
   * 作業系統：使用[作業系統](/help/components/dimensions/operating-systems.md)維度。
   * 作業系統類型：使用[作業系統類型](/help/components/dimensions/operating-system-types.md)維度。
   * 監視器色彩深度：使用[色彩深度](/help/components/dimensions/color-depth.md)維度。
   * 監視器解析度：使用[監視器解析度](/help/components/dimensions/monitor-resolution.md)維度。
   * Java：使用 [Java 已啟用](/help/components/dimensions/java-enabled.md)維度。
   * JavaScript：使用「JavaScript 已啟用」維度 (Analysis Workspace 已淘汰此功能)。維度項目為「已啟用」、「已停用」或「未知」，端視瀏覽器是否已啟用 JavaScript。
   * JavaScript 版本：使用「JavaScript 版本」維度 (Analysis Workspace 已淘汰此功能)。維度項目會顯示瀏覽器使用的 JavaScript 版本。
   * Cookie：使用 [Cookie 支援](/help/components/dimensions/cookie-support.md)維度。
   * 連線類型：使用[連線類型](/help/components/dimensions/connection-type.md)維度。
   * 行動電信業者：使用[行動電信業者](/help/components/dimensions/mobile-dimensions.md)維度。
* 訪客狀態：使用「狀態」維度 (Analysis Workspace 已淘汰此功能)。維度項目來自 [`state`](../../implement/vars/page-vars/state.md) 變數。
* 訪客郵遞區號：使用[郵遞區號](/help/components/dimensions/zip-code.md)維度。

## 自訂轉換

包含您的實施特有的報表。自訂轉換報表以 [eVar](/help/components/dimensions/evar.md) 作為維度。

## 自訂流量

包含您的實施特有的報表。自訂流量報表以 [Prop](/help/components/dimensions/prop.md) 作為維度。

## 行銷管道

包含與[行銷管道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)有關的報表。

* 管道概觀報表：Reports &amp; Analytics 特有的自訂報表。以行銷管道作為維度項目，且量度使用首次接觸或最後接觸歸因。
* 首次接觸管道：使用[首次接觸管道](/help/components/dimensions/first-touch-channel.md)維度。
* 首次接觸管道詳細資料：使用[首次接觸管道詳細資料](/help/components/dimensions/first-touch-detail.md)維度。
* 最後接觸管道：使用[最後接觸管道](/help/components/dimensions/last-touch-channel.md)維度。
* 最後接觸管道詳細資料：使用[最後接觸管道詳細資料](/help/components/dimensions/last-touch-detail.md)維度。

## 書籤

包含您已建立書籤的報表。如需詳細資訊，請參閱[書籤](bookmarks.md)。

## 控制面板

包含您已建立的控制面板。如需詳細資訊，請參閱[控制面板](dashboard.md)。

## 目標

包含您已建立的目標。如需詳細資訊，請參閱[目標](targets.md)。

>[!NOTE]
>
>如果您在此說明頁面上找不到您的報表，可能是管理員已資料夾重新命名或加以調整。請參閱「管理員使用指南」中的[功能表自訂](/help/admin/admin/customize-menus.md)。
