---
description: 下圖說明資料收集的運作方式。
keywords: DFA
seo-description: 下圖說明資料收集的運作方式。
seo-title: Adobe整合即時資料收集
solution: Analytics
title: Adobe整合即時資料收集
topic: Data connectors
uuid: 5dce319c-7d4b-4475-1e6d-dc5 c972 a82 e9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe 整合: 即時資料收集{#adobe-integration-real-time-data-collection}

下圖說明資料收集的運作方式。

![](assets/DFA_data_collection.png)

Adobe 整合的資料收集部分會在訪客進入著陸頁面時展開 (1)。在著陸頁面上執行的 Adobe 資料收集代碼，並不知悉訪客在提供的廣告方面有何歷史記錄。Google DFA 團隊協調出一項執行於 DFA Floodlight 伺服器的服務，可讓 Adobe 代碼查詢與目前在網站上的訪客有關的廣告資訊 (2)。在取得這項資料時，會暫時延遲 Adobe 影像信標，並要求 Floodlight 伺服器中的資料。

在資料送達，或是執行時間過久時，將會對 Adobe 追蹤伺服器引發點擊 (3)。

整合模組是一個特殊核心 Adobe JavaScript 模組，它會使 Adobe 影像信標延遲，而在特定的時間長度內 ( *`s.maxDelay`*). *`s.maxDelay`*&#x200B;會定義整合模組將在等待 DFA Floodlight 伺服器傳回資料多久之後，對訪客的瀏覽器引發影像標記。藉由此行為，即使在 DFA Floodlight 伺服器關閉或負載過重時，仍可收集基本訪客資料，因此這項行為是很重要的。如果 Floodlight 資料在&#x200B;*`s.maxDelay`*&#x200B;到期之前送達，將會立即引發 Adobe 追蹤資料，且其中會包含其他 DFA 資料。

如果發生逾時，頁面代碼可以將 Adobe 報告與分析事件指定作為逾時事件。在診斷整合方面的問題時，此事件將有其用處，或是，在調整&#x200B;*`s.maxDelay`*。如果太常發生逾時，請增加 *`s.maxDelay`*. *`s.maxDelay`* 可設定過高，但在 *`s.maxDelay`* 計時器過期之前，訪客可能有離開網站的可能性。For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

有時候，Floodlight 伺服器在回應時會出現關於訪客的錯誤。此錯誤通常是發生在 Floodlight 伺服器因訪客尚未檢視任何廣告，或沒有 DFA 訪客 cookie，而對訪客一無所知的情況下。頁面代碼可指定一個自訂轉換變數 (eVar)，用來收集這些錯誤，以及協助您進行實施問題的疑難排解，或指出 Google 交易方面的問題。最常見的錯誤是「沒有歷史記錄」、「沒有 cookie」、「查詢錯誤」和「已退出」，如下表所說明:

| 錯誤 | 名稱 | 說明 |
|---|---|---|
| nh | 沒有歷史記錄 | 訪客並未檢視或點按任何廣告。 |
| nc | 沒有 cookie | 訪客沒有 DFA 訪客 cookie。 |
| qe | 查詢錯誤 | 查詢 Floodlight 伺服器的資料時發生錯誤。 |
| oo | 已退出 | 訪客已退出 Google 曝光/點按追蹤。 |

