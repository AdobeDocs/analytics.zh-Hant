---
description: DFA 的 Data connectors 整合會使用 Analytics 變數來追蹤 DFA 促銷活動結果。
keywords: DFA
title: Analytics 變數和事件
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analytics 變數和事件{#analytics-variables-and-events}

DFA 的 Data connectors 整合會使用 Analytics 變數來追蹤 DFA 促銷活動結果。

除了促銷活動變數以外，您也可以使用對您有意義的 Analytics 事件和 eVar。在您指定要用於此 DFA 整合的事件和 eVar 之後，請使用 Analytics 管理主控台加以啟用。在啟動 DFA 整合之前，必須先啟用整合變數。下表說明 DFA 整合所需的 Analytics 變數。

| 變數 | 友好名稱 | 填入方法 | 說明 |
|---|---|---|---|
| s.campaign 或 eVar | 廣告追蹤代碼 | 由 DFA 促銷活動的 Data Connectors 自動填入。 | 追蹤所有促銷活動的點進轉換。 |
| eVar* | 閱覽 | 透過 DFA 促銷活動的 VISTA 和 DFA 自動填入。 | 追蹤 DFA ID 的閱覽資料。此 eVar 應具有與&#x200B;*`s.campaign`* 變數中。必須與變數提供者ID中所識別的轉換變數相同。 請確定 eVar 已啟用完整的子關連。啟用此功能的成本是 Data connectors 整合費用的一部分 |
| eVar* | DFA 查詢錯誤 | (可選) 透過 JavaScript 收集代碼填入。 | 包含從DFA傳回的數個錯誤碼之一。 |
| 事件* | 閱覽計數 | 由 DFA 促銷活動的 Data Connectors 自動填入。 | 擷取使用者檢視廣告、未點進但進入您的網站的次數。 |
| 事件* | 曝光數 | 透過 DFA 的資料回饋自動填入。 | 追蹤特定 DFA 廣告的提供次數。 |
| 事件* | 點按 | 透過 DFA 的資料回饋自動填入。 | 追蹤使用者點按特定 DFA 橫幅廣告的次數。基於數個原因之一，此量度可能會產生與原生 Analytics 點進量度不同的數值。請參閱[協調量度差異](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md)以取得詳細資訊。 |
| 事件* | DFA 逾時 | (可選) 透過 JavaScript 收集代碼填入。 | 計算 DFA 無法在&#x200B;*`s.maxDelay`*&#x200B;逾時之前回應的次數。這有助於您判斷是否有 DFA 實施問題。 |
| 事件* | DFA 媒體成本 | 透過 DFA 的資料回饋自動填入。 | 包含已在 DFA 介面中輸入的媒體成本量度。必須在 DFA 端啟用此功能，這些量度才會出現。 |

*請選取未使用的 eVar 或自訂事件。
