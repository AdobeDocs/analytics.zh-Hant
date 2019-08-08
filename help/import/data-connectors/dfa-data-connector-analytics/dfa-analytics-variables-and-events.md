---
description: DFA 的 Data connectors 整合會使用 Analytics 變數來追蹤 DFA 促銷活動結果。
keywords: DFA
seo-description: DFA 的 Data connectors 整合會使用 Analytics 變數來追蹤 DFA 促銷活動結果。
seo-title: Analytics 變數和事件
solution: Analytics
title: Analytics 變數和事件
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3066442 b29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics 變數和事件{#analytics-variables-and-events}

DFA 的 Data connectors 整合會使用 Analytics 變數來追蹤 DFA 促銷活動結果。

除了促銷活動變數以外，您也可以使用對您有意義的 Analytics 事件和 eVar。在您指定要用於此 DFA 整合的事件和 eVar 之後，請使用 Analytics 管理主控台加以啟用。在啟動 DFA 整合之前，必須先啟用整合變數。下表說明 DFA 整合所需的 Analytics 變數。

| 變數 | 友好名稱 | 填入方法 | 說明 |
|---|---|---|---|
| s.campaign 或 eVar | 廣告追蹤代碼 | 由 DFA 促銷活動的 Data Connectors 自動填入。 | 追蹤所有促銷活動的點進轉換。 |
| eVar* | 閱覽 | 透過 DFA 促銷活動的 VISTA 和 DFA 自動填入。 | 追蹤 DFA ID 的閱覽資料。此 eVar 應具有與&#x200B;*`s.campaign`* 變數。必須與變數提供者ID中所識別的轉換變數相同(請參閱 [更新您網站的資料收集代碼](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3))。請確定 eVar 已啟用完整的子關連。啟用此功能的成本是 Data connectors 整合費用的一部分 |
| eVar* | DFA 查詢錯誤 | (可選) 透過 JavaScript 收集代碼填入。 | 包含從 DFA 傳回的數個錯誤代碼之一 (請參閱 [設定整合](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858)中的表格，以取得這些錯誤代碼的清單) |
| 事件* | 閱覽計數 | 由 DFA 促銷活動的 Data Connectors 自動填入。 | 擷取使用者檢視廣告、未點進但進入您的網站的次數。 |
| 事件* | 曝光數 | 透過 DFA 的資料回饋自動填入。 | 追蹤特定 DFA 廣告的提供次數。 |
| 事件* | 點按 | 透過 DFA 的資料回饋自動填入。 | 追蹤使用者點按特定 DFA 橫幅廣告的次數。基於數個原因之一，此量度可能會產生與原生 Analytics 點進量度不同的數值。請參閱[協調量度差異](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f)以取得詳細資訊。 |
| 事件* | DFA 逾時 | (可選) 透過 JavaScript 收集代碼填入。 | 計算 DFA 無法在&#x200B;*`s.maxDelay`*&#x200B;逾時之前回應的次數。這有助於您判斷是否有 DFA 實施問題。 |
| 事件* | DFA 媒體成本 | 透過 DFA 的資料回饋自動填入。 | 包含已在 DFA 介面中輸入的媒體成本量度。必須在 DFA 端啟用此功能，這些量度才會出現。 |

*請選取未使用的 eVar 或自訂事件。
