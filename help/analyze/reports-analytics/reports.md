---
title: 報表
description: 「報告與分析」用於每個報表的維度和量度。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# 報表

「報告與分析」中的每個報表都使用專用的維度和預設度量。 您可以變更每個報表中的量度，並視需要新增劃分。 下列清單提供每個報表中使用的維度。

>[!NOTE]
>
>您的報表功能表會根據您組織中管理員所做的自訂設定而有所不同。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## 網站量度

包含使用日期範圍進行趨勢分析的報表。 也包含獨特報表，例如建議報表和即時報表。

* 我的建議報表： 建立包含數個小報表的控制面板，以便立即獲得深入資訊。
* 關鍵量度： 一次最多可讓您趨勢化5個量度的報表。 依預 [設](/help/components/metrics/page-views.md)，趨勢頁 [面檢視](/help/components/metrics/visits.md)、瀏覽和 [獨特訪客](/help/components/metrics/unique-visitors.md) 。
* 頁面檢視： 隨時間推 [移頁面檢視](/help/components/metrics/page-views.md) 量度的趨勢。
* 瀏覽次數： 隨時間推 [移](/help/components/metrics/visits.md) 「瀏覽」度量。
* 訪客： 隨時間推 [移各種獨特](/help/components/metrics/unique-visitors.md) 訪客量度的趨勢。
   * 獨特訪客： 在整個選取的日期範圍內，僅計算一次訪客。
   * 每小時獨特訪客： 如果訪客在所選日期範圍的不同小時內瀏覽，則會計算多次。
   * 每日獨特訪客： 如果訪客在所選日期範圍的不同日期瀏覽，則會計算多次。
   * 每週獨特訪客： 如果訪客在所選日期範圍的不同周內瀏覽，則會計算多次。
   * 每月獨特訪客： 如果訪客在所選日期範圍的不同月份瀏覽，則會計算多次。
   * 每季獨特訪客： 如果訪客在所選日期範圍的不同季度瀏覽，則會計算多次。 季度包括1-3月、4-6月、7-9月和10-12月。
   * 每年獨特訪客： 如果訪客在所選日期範圍的不同日曆年度瀏覽，則會計算多次。
* 每次瀏覽逗留時間： 使用「每 [次瀏覽逗留時間——分組化](/help/components/dimensions/time-spent-per-visit.md) 」維度。
* 事件之前時間： 使用事 [件之前的時間](/help/components/dimensions/time-prior-to-event.md) 維。
* 購買： 包含購買型量度的相關報表。
   * 購買轉換漏斗： 報表關 [於](/help/components/metrics/visits.md)、購物車 [、訂購收入](/help/components/metrics/carts.md)、 [收入](/help/components/metrics/orders.md)和 [漏斗中](/help/components/metrics/revenue.md)[](/help/components/metrics/units.md) 的訂購單位。 「分析工作區」中使用「流失」視覺化也實現了類似 [的視覺化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
   * 收入： 隨時間推移 [量度](/help/components/metrics/revenue.md) 「收入」。
   * 訂購： 隨時間推移 [量度](/help/components/metrics/orders.md) 「訂購」趨勢。
   * 件數： 隨時間推 [移量度](/help/components/metrics/units.md) 單位。
* 購物車： 包含有關購物車量度的報表。
   * 購物車轉換漏斗： 報 [表](/help/components/metrics/instances.md)、 [購物車、購物車、結帳](/help/components/metrics/carts.md)、訂單 [、收入漏斗](/help/components/metrics/checkouts.md)中的「訂單 [](/help/components/metrics/orders.md)[](/help/components/metrics/revenue.md) 和收入」報表例項。
   * 購物車： 隨時間推 [移](/help/components/metrics/carts.md) 。
   * 購物車檢視： 隨時間推移量 [度購物車](/help/components/metrics/cart-views.md) 檢視的趨勢。
   * 購物車新增： 隨時間推移量 [度購物車](/help/components/metrics/cart-additions.md) 新增的趨勢。
   * 購物車移除： 隨時間推移量 [度購物車](/help/components/metrics/cart-removals.md) 移除的趨勢。
   * 結帳： 隨時間推 [移量度](/help/components/metrics/checkouts.md) 結帳。
* 自訂事件： 包含與您的實作相關 [的自訂](/help/components/metrics/custom-events.md) 「事件」所有報表。
* 機器人： 顯示機器人相關報表。
   * 機器人： 顯示網站最頻繁的機器人。 See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * 機器人頁面： 顯示機器人點擊最多的頁面。
* 即時： 在資料收集後數秒內顯示特定維度和量度。 See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## 網站內容

包含通常顯示網站內容之維度的報表。 您可以將分類套用至其中一些報表。 套用分類表示報表會變成包含來源報表和分類報表的功能表。

* 頁面： 使用頁 [面維](/help/components/dimensions/page.md) 。
* 網站區段： 使用「網 [站區域](/help/components/dimensions/site-section.md) 」維。
* 伺服器： 使用服 [務器](/help/components/dimensions/server.md) 維。
* 連結： 包含使用連結追蹤的報表。
   * 退出連結： 使用「退 [出連結](/help/components/dimensions/exit-link.md) 」維度。
   * 檔案下載： 使用「下 [載連結](/help/components/dimensions/download-link.md) 」維度。
   * 自訂連結： 使用自 [訂連結](/help/components/dimensions/custom-link.md) 維度。
   * 找不到頁面： 使用「 [找不到頁面](/help/components/dimensions/pages-not-found.md) 」維度。

## 行動

包含舊版行動報表的報表。 這些報表以使用者代理字串為資料基礎。 他們會針對各自 [的報表](/help/components/dimensions/mobile-dimensions.md) ，使用各種行動維度。

* 裝置： 使用行 [動裝置](/help/components/dimensions/mobile-dimensions.md) 維度。
* 裝置類型： 使用行 [動裝置類型](/help/components/dimensions/mobile-dimensions.md) 維度。
* 製造商： 使用 [Mobile製造商](/help/components/dimensions/mobile-dimensions.md) 維度。
* 螢幕大小： 使用 [Mobile螢幕大小](/help/components/dimensions/mobile-dimensions.md) 。
* 螢幕高度： 使用行 [動螢幕高度](/help/components/dimensions/mobile-dimensions.md) 。
* 螢幕寬度： 使用「 [行動」螢幕寬度](/help/components/dimensions/mobile-dimensions.md) 。
* Cookie支援： 使用 [Mobile Cookie支援維度](/help/components/dimensions/mobile-dimensions.md) 。
* 影像支援： 使用行 [動影像支援](/help/components/dimensions/mobile-dimensions.md) 維度。
* 色彩深度： 使用行 [動色深](/help/components/dimensions/mobile-dimensions.md) 。
* 音訊支援： 使用行 [動音訊支援](/help/components/dimensions/mobile-dimensions.md) 維度。
* 視訊支援： 使用行 [動視訊支援](/help/components/dimensions/mobile-dimensions.md) 維度。
* 作業系統（已過時）: 使用 [Mobile作業系統（已過時）維](/help/components/dimensions/mobile-dimensions.md) 。

## 路徑

包含可讓您查看訪客路徑資料的報表。

* 下一頁流量： 在頂端頁面維度值上使用流量報表。 路徑檢視與例項類 [似](/help/components/metrics/instances.md)。 您可以變更報告的維度值。 「分析工作區」中的類似報表可使用「流量」 [視覺化](../analysis-workspace/visualizations/c-flow/flow.md)。
* 下一頁： 擷取頂端頁面維度值，並顯示訪客瀏覽的下一頁。
* 上一頁流量： 在頂端頁面維度值上使用流量報表分析工作區中的類似報表可使用流量 [視覺化](../analysis-workspace/visualizations/c-flow/flow.md)。
* 上一頁： 擷取頂端頁面維度值，並顯示訪客的上一頁。
* 流失： 可讓您在步驟中選取頁面維度值，並顯示已遵循和未遵循該路徑的人員比例。 「分析工作區」中的類似報表可使用「流失」 [視覺化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 完整路徑： 將個別路徑顯示為維度值。 在分析工作區中退休； 請改用 [流量視覺化](../analysis-workspace/visualizations/c-flow/flow.md) 。
* PathFinder: 提供多種報表類型，可讓您分析路徑（在分析工作區中淘汰）。
* 路徑長度： 使用「瀏 [覽深度](/help/components/dimensions/visit-depth.md) 」維度。
* 頁面分析
   * 頁面摘要： 擷取頂端頁面維度值並顯示趨勢檢視。 也會顯示該頂端頁面維度值的登入點、上一頁、退出點和下一頁。
   * 重新載入： 將頁面 [維度與](/help/components/dimensions/page.md) 「重新載 [入」度量](/help/components/metrics/reloads.md) 一起使用。
   * 頁面逗留時間： 使用頁 [面逗留時間——範圍化維度](/help/components/dimensions/time-spent-on-page.md) 。
   * 頁麵點按次數： 擷取頂端頁面維度值，並顯示在指定瀏覽中到達該頁面所花費的點按次數。
* 登入與退出
   * 登入頁面： 使用「登 [入頁面](/help/components/dimensions/entry-dimensions.md) 」維度。
   * 原始登入頁面： 使用「登 [入」頁原始](/help/components/dimensions/entry-dimensions.md) 維。
   * 單頁瀏覽： 套用Adobe [提供的](/help/components/dimensions/page.md) 「單頁瀏覽」區段時，使用「頁面」維度。
   * 退出頁面： 使用「退 [出頁面](/help/components/dimensions/exit-dimensions.md) 」維度。

>[!NOTE]
>
>其他報表可顯示在此資料夾中。 它們是其他維度，例如prop，您可在報表套裝設 [定下啟用](../../admin/admin/c-traffic-variables/traffic-var.md) 路徑分析。

## 流量來源

包含報告，可讓您分析訪客在到達您的網站前的來源。 除非您在報表套裝設定下正確設定「 [內部URL篩選](../../admin/admin/internal-url-filter-admin.md) 」，否則這些報表無法正常運作。

* 搜尋關鍵字——全部： 使用「搜 [尋關鍵字](/help/components/dimensions/search-keyword.md) 」維度。
* 搜尋關鍵字——付費： 使用「搜 [尋關鍵字——付費](/help/components/dimensions/search-keyword.md) 」維度。
* 搜尋關鍵字——免費： 使用「搜 [尋」關鍵字——免費維](/help/components/dimensions/search-keyword.md) 度
* 搜尋引擎——全部： 使用搜 [尋引擎](/help/components/dimensions/search-engine.md) 維度。
* 搜尋引擎——付費： 使用搜 [尋引擎——付費維度](/help/components/dimensions/search-engine.md) 。
* 搜尋引擎——免費： 使用搜 [尋引擎——免費維](/help/components/dimensions/search-engine.md) 度。
* 所有搜尋頁面排名： 使用「所 [有搜尋頁面排名](/help/components/dimensions/all-search-page-rank.md) 」維度。
* 反向連結網域： 使用反向 [連結網域](/help/components/dimensions/referring-domain.md) 維度
* 原始反向連結網域： 使用原 [始反向連結網域](/help/components/dimensions/original-referring-domain.md) 維
* 反向連結： 使用「反向 [連結](/help/components/dimensions/referrer.md) 」維度。
* 反向連結類型： 使用「反向 [連結類型](/help/components/dimensions/referrer-type.md) 」維度。

## 促銷活動

主要包含追蹤代碼維 [度的報表](/help/components/dimensions/tracking-code.md) 。

* 促銷活動轉換漏斗： 漏斗報表中的報 [表點進](/help/components/metrics/checkouts.md)、結 [帳](/help/components/metrics/orders.md)、訂購 [和](/help/components/metrics/revenue.md) 收入。 點進次數量度與追蹤代碼維 [度的](/help/components/metrics/instances.md) 「例項」量 [度類似](/help/components/dimensions/tracking-code.md) 。 「分析工作區」中使用「流失」視覺化也實現了類似 [的視覺化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 追蹤代碼： 使用追 [蹤代碼](/help/components/dimensions/tracking-code.md) 維度。

## 產品

主要包含產品維 [度的](/help/components/dimensions/product.md) 報表。

* 產品轉換漏斗： 報表 [產品檢視](/help/components/metrics/product-views.md)、購物車 [新增、檢查](/help/components/metrics/cart-additions.md)、訂單 [、訂](/help/components/metrics/checkouts.md)[](/help/components/metrics/orders.md)[](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) 單、單位和漏斗報表中的收入。 「分析工作區」中使用「流失」視覺化也實現了類似 [的視覺化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 產品： 使用「 [產品](/help/components/dimensions/product.md) 」維。
* 交叉銷售： 顯示通常一起銷售的產品（在分析工作區中淘汰）。
* 類別： 使用「類 [別](/help/components/dimensions/category.md) 」維。

## 訪客保留率

包含有關回訪您網站之訪客的報表。

* 回訪頻率： 使用「 [返回頻率](/help/components/dimensions/return-frequency.md) 」維。
* 回訪： 套用Adobe [提供](/help/components/metrics/visits.md) 的「回訪」區段後，「造訪」量度隨時間變化趨勢。
* 瀏覽次數： 使用瀏覽 [次數維](/help/components/dimensions/visit-number.md) 。
* 銷售週期： 購買相關報表的資料夾。
   * 客戶忠誠度： 使用「客 [戶忠誠度](/help/components/dimensions/customer-loyalty.md) 」維度。
   * 首次購買前的天數： 使用第 [一次購買的天數](/help/components/dimensions/days-before-first-purchase.md) 維。
   * 上次購買間隔天數： 使用「 [上次購買間隔天數](/help/components/dimensions/days-since-last-purchase.md) 」維度。
   * 每日獨特客戶： 趨勢 [套用Adobe提供的](/help/components/metrics/unique-visitors.md) 「購買者」區段，即可隨時間推移的每日獨特訪客。
   * 每週獨特客戶： 趨勢 [套用Adobe提供的](/help/components/metrics/unique-visitors.md) 「購買者」區段後，每週獨特訪客隨時間推移。
   * 每月獨特客戶： 趨勢 [套用Adobe提供的](/help/components/metrics/unique-visitors.md) 「購買者」區段後，每月獨特訪客隨時間變化。
   * 每季獨特客戶： 趨勢 [套用Adobe提供的](/help/components/metrics/unique-visitors.md) 「購買者」區段後，每季獨特訪客會隨時間變化。 季度包括1-3月、4-6月、7-9月和10-12月。
   * 每年獨特客戶： 趨勢 [套用Adobe提供](/help/components/metrics/unique-visitors.md) 的「購買者」區段後，每年的獨特訪客會隨時間變化。

## 訪客資料

包含有關瀏覽您網站的訪客的報表。

* 地域劃分： 關於您網站全球點擊來源的報表。
   * 國家： 使用「國 [家](/help/components/dimensions/countries.md) 」維度。
   * 地區： 使用「 [區域](/help/components/dimensions/regions.md) 」維。
   * 城市： 使用「城 [市](/help/components/dimensions/cities.md) 」維度。
   * 美國州： 使用美 [國州](/help/components/dimensions/us-states.md) 維。
   * 美國DMA: 使用 [美國DMA](/help/components/dimensions/us-dma.md) 維。
* 語言： 使用「語 [言](/help/components/dimensions/language.md) 」維。
* 時區： 使用時區維度（在分析工作區中退役）。 維度值是點擊的GMT偏移。
* 網域： 使用 [Domain](/help/components/dimensions/domain.md) 維。
* 頂層網域： 使用頂層網域維度（在分析工作區中退役）。 它會將網 [域維](/help/components/dimensions/domain.md) 度分組為較高層級的類別，通常依網域的國家／地區而定。
* 技術： 資料夾包含訪客用來存取您網站的報表。
   * 瀏覽器： 使用「瀏 [覽器](/help/components/dimensions/browser.md) 」維度。
   * 瀏覽器類型： 使用「瀏 [覽器類型](/help/components/dimensions/browser-type.md) 」維。
   * 瀏覽器寬度： 使用瀏 [覽器寬度——範圍化](/help/components/dimensions/browser-width.md) 維度。
   * 瀏覽器高度： 使用瀏 [覽器高度——範圍化](/help/components/dimensions/browser-height.md) 維度。
   * 作業系統： 使用「操 [作系統](/help/components/dimensions/operating-systems.md) 」維。
   * 作業系統類型： 使用「操 [作系統類型](/help/components/dimensions/operating-system-types.md) 」維。
   * 螢幕色彩深度： 使用「顏 [色深度](/help/components/dimensions/color-depth.md) 」尺寸。
   * 螢幕解析度： 使用「監 [視器解析度](/help/components/dimensions/monitor-resolution.md) 」維。
   * Java: 使用啟 [用Java的維](/help/components/dimensions/java-enabled.md) 。
   * JavaScript: 使用啟用JavaScript的維度（在分析工作區中退役）。 維度值為「已啟用」、「已停用」或「未知」，視瀏覽器是否已啟用JavaScript而定。
   * JavaScript版本： 使用JavaScript版本維度（在分析工作區中退役）。 維度值顯示瀏覽器使用的JavaScript版本。
   * Cookie: 使用 [Cookie支援維](/help/components/dimensions/cookie-support.md) 。
   * 連線類型： 使用「連 [接類型](/help/components/dimensions/connection-type.md) 」維。
   * 行動電信業者： 使用行 [動電信業者](/help/components/dimensions/mobile-dimensions.md) 維度。
* 訪客狀態： 使用「狀態」維（在分析工作區中退役）。 維度值源自變 [`state`](../../implement/vars/page-vars/state.md) 數。
* 訪客郵遞區號： 使用郵 [遞區號](/help/components/dimensions/zip-code.md) 維度。

## 自訂轉換

包含您實作的特定報表。 自訂轉換報表 [使用eVar](/help/components/dimensions/evar.md) 作為維度。

## 自訂流量

包含您實作的特定報表。 自訂流量報表 [使用](/help/components/dimensions/prop.md) prop作為維度。

## 行銷管道

包含與行銷管道 [有關的報表](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

* 渠道概述報告： 「報告與分析」專屬的自訂報表。 使用行銷渠道作為維度值，並使用首次接觸或上次接觸歸因的量度。
* 首次接觸渠道： 使用「首 [次接觸渠道](/help/components/dimensions/first-touch-channel.md) 」尺寸。
* 首次接觸渠道的詳細資訊： 使用「首 [次接觸渠道」細節](/help/components/dimensions/first-touch-detail.md) 維度。
* 上次接觸渠道： 使用「上 [次接觸渠道](/help/components/dimensions/last-touch-channel.md) 」維度。
* 上次接觸渠道的詳情： 使用「上 [次接觸渠道詳細資料](/help/components/dimensions/last-touch-detail.md) 」維度。

## 書籤

包含您建立書籤的報表。 See [Bookmarks](bookmarks.md) for more information.

## 控制面板

包含您建立的控制面板。 See [Dashboards](dashboard.md) for more information.

## 目標

包含您建立的目標。 See [Targets](targets.md) for more information.

>[!NOTE]
>
>如果您在此說明頁面上找不到報表，則管理員可能會重新命名或調整資料夾。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
