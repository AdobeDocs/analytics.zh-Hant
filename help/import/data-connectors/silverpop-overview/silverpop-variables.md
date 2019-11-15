---
description: Silverpop的「資料連接器」整合使用Analytics變數來追蹤各種Silverpop量度。
title: Analytics整合變數
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop的「資料連接器」整合使用Analytics變數來追蹤各種Silverpop量度。

在識別要與Silverpop整合一起使用的事件和eVar後，請使用Adobe Analytics管理控制台來啟用它們(請參閱報 [表套裝](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html))。

下表說明Silverpop整合所需的Analytics變數。

## 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| 事件（數值） | 彈回數 | 自動從Silverpop匯入。 | 「彈回數」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數目。 |
| 事件（數值） | 點擊次數 | 自動從Silverpop匯入。 | 「點按」事件可讓您查看點按電子郵件訊息的訪客數。 |
| 事件（數值） | 開啟 | 自動從Silverpop匯入。 | 「已開啟」事件可讓您查看開啟電子郵件訊息的訪客人數。 |
| 事件（數值） | 發送 | 自動從Silverpop匯入。 | 「傳送」事件可讓您查看已傳送的電子郵件數目。 |
| 事件（數值） | 取消訂閱 | 自動從Silverpop匯入。 | 「取消訂閱」事件可讓您查看開啟電子郵件訊息但接著按一下「取消訂閱」連結以選擇退出您組織未來的電子郵件訊息的訪客人數。 |
| eVar | Silverpop ID/訪客ID | 透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | 獨特訪客ID |
| eVar或s.campaign | 郵寄ID | 透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | 這通常會儲存在促銷活動變數中。 |

## 選擇性變數 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| event（計數器） | 檔案已下載 | 透過Analytics標籤手動收集。 | 此事件用於識別在網站上下載檔案的使用者。 |
| event（計數器） | 表單已開始 | 透過Analytics標籤手動收集。 | 「已開始的表單」用於識別開始表單但未完成表單的使用者。 |
| event（計數器） | 表單已完成 | 透過Analytics標籤手動收集。 | 「表單已完成」用於識別開始表單但未完成的訪客。 |
| eVar | Email Address | 透過Analytics標籤手動收集。 | 「電子郵件地址」是用於在註冊、登入或收集電子郵件地址的其他頁面上手動收集電子郵件地址。 此變數可用來重新行銷給選擇收到電子郵件但過去可能尚未點選過電子郵件的使用者。 |
| eVar | 下載的檔案 | 透過Analytics標籤手動收集。 | 下載的檔案可識別訪客下載的檔案。 |
| eVar | 表單名稱 | 透過Analytics標籤手動收集。 | 表單名稱可識別放棄的訪客表單。 |

