---
description: The Data Connectors integration for Silverpop uses Analytics variables to track various Silverpop metrics.
seo-description: Silverpop的「資料連接器」整合使用Analytics變數來追蹤各種Silverpop量度。
seo-title: Analytics整合變數
title: Analytics整合變數
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop的「資料連接器」整合使用Analytics變數來追蹤各種Silverpop量度。

在識別要與Silverpop整合一起使用的事件和eVar後，請使用Adobe Analytics管理控制台來啟用它們(請參閱報 [表套裝](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html))。

The following table describes the Analytics variables needed for the Silverpop integration.

## 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| 事件（數值） | 彈回數 | 自動從Silverpop匯入。 | 「彈回數」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數目。 |
| 事件（數值） | 點擊次數 | 自動從Silverpop匯入。 | 「點按」事件可讓您查看點按電子郵件訊息的訪客數。 |
| 事件（數值） | 開啟 | 自動從Silverpop匯入。 | 「已開啟」事件可讓您查看開啟電子郵件訊息的訪客人數。 |
| 事件（數值） | 發送 | 自動從Silverpop匯入。 | 「傳送」事件可讓您查看已傳送的電子郵件數目。 |
| 事件（數值） | 取消訂閱 | 自動從Silverpop匯入。 | 「取消訂閱」事件可讓您查看開啟電子郵件訊息但接著按一下「取消訂閱」連結以選擇退出您組織未來的電子郵件訊息的訪客人數。 |
| eVar | Silverpop ID/訪客ID | 透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | Unique Visitor ID |
| eVar或s.campaign | 郵寄ID | 透過自動收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | This is often stored in the campaign variable. |

## 選擇性變數 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| event (counter) | File Downloaded | Manually collected through Analytics tags. | This event is used to identify users who downloaded a file on the site. |
| event (counter) | Form Started | Manually collected through Analytics tags. | Form Started is used to identify users who begin a form, but do not complete it. |
| event (counter) | Form Completed | 透過Analytics標籤手動收集。 | Form Completed is used to identify visitors who begin a form and do not complete it. |
| eVar | Email Address | Manually collected through Analytics tags. | Email Address is for manually collecting the email address on sign-up, log-in, or other pages that the email address is collected on. 此變數可用來重新行銷給選擇收到電子郵件但過去可能尚未點選過電子郵件的使用者。 |
| eVar | Downloaded File | 透過Analytics標籤手動收集。 | 下載的檔案可識別訪客下載的檔案。 |
| eVar | 表單名稱 | 透過Analytics標籤手動收集。 | 表單名稱可識別放棄的訪客表單。 |

