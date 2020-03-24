---
description: Silverpop 的 Data Connectors 整合使用 Analytics 變數來追蹤各種 Silverpop 量度。
title: Analytics 整合變數
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 整合變數{#analytics-integration-variables}

Silverpop 的 Data Connectors 整合使用 Analytics 變數來追蹤各種 Silverpop 量度。

識別要與 Silverpop 整合搭配使用的事件和 eVar 後，請使用 Adobe Analytics Admin Console 啟用它們 (請參閱[報表套裝](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/manage-report-suites/report-suites-admin.html))。

下表說明 Silverpop 整合所需的 Analytics 變數。

## 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| 事件 (數值) | 彈回數 | 自動從 Silverpop 匯入。 | 「跳出數」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數。 |
| 事件 (數值) | 點擊次數 | 自動從 Silverpop 匯入。 | 「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 |
| 事件 (數值) | 開啟數 | 自動從 Silverpop 匯入。 | 「已開啟」事件可讓您查看已開啟電子郵件訊息的訪客數。 |
| 事件 (數值) | 傳送數 | 自動從 Silverpop 匯入。 | 「已傳送」事件可讓您查看已傳送的電子郵件訊息數目。 |
| 事件 (數值) | 取消訂閱數 | 自動從 Silverpop 匯入。 | 「已取消訂閱」事件可讓您查看在開啟電子郵件訊息後按一下「取消訂閱」連結以選擇退出貴組織未來的電子郵件訊息的訪客人數。 |
| eVar | Silverpop ID/訪客 ID | 透過自動收集方法或 JavaScript 外掛程式，從電子郵件連結中的查詢參數收集。 | 獨特訪客 ID |
| eVar 或 s.campaign | 郵件 ID | 透過自動收集方法或 JavaScript 外掛程式，從電子郵件連結中的查詢參數收集。 | 此項通常會儲存在促銷活動變數中。 |

## 選擇性變數 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| 事件 (計數器) | 檔案已下載 | 透過 Analytics 標籤手動收集。 | 此事件用於識別在網站上下載檔案的使用者。 |
| 事件 (計數器) | 表單已開始 | 透過 Analytics 標籤手動收集。 | 「表單已開始」用於識別開始表單但未完成的使用者。 |
| 事件 (計數器) | 表單已完成 | 透過 Analytics 標籤手動收集。 | 「表單已完成」用於識別開始表單且已完成的訪客。 |
| eVar | 電子郵件地址 | 透過 Analytics 標籤手動收集。 | 「電子郵件地址」用於在註冊、登入或其他收集電子郵件地址的頁面上，手動收集電子郵件地址。此變數可用來對曾選擇收到電子郵件，但過去可能尚未點進電子郵件的使用者進行再行銷。 |
| eVar | 已下載檔案 | 透過 Analytics 標籤手動收集。 | 「已下載檔案」可識別訪客下載哪個檔案。 |
| eVar | 表單名稱 | 透過 Analytics 標籤手動收集。 | 「表單名稱」可識別訪客放棄的表單。 |

