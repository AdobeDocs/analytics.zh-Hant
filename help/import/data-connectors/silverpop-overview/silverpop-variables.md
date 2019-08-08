---
description: Silverpop的Data Connectors整合使用Analytics變數來追蹤各種Silverpop度量。
seo-description: Silverpop的Data Connectors整合使用Analytics變數來追蹤各種Silverpop度量。
seo-title: Analytics整合變數
title: Analytics整合變數
uuid: af3af-e24 e-4e-4fe7-b4 d7-50ca0 f6703 b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop的Data Connectors整合使用Analytics變數來追蹤各種Silverpop度量。

識別用於Silverpop整合的事件和eVar後，請使用Adobe Analytics管理控制台啓用它們(請參閱 [報表套裝](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin))。

下表說明Silverpop整合所需的Analytics變數。

## 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| event(數值) | 彈回數 | 自動從Silverpop匯入。 | 「彈回數」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數量。 |
| event(數值) | 點擊次數 | 自動從Silverpop匯入。 | 點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 |
| event(數值) | 開啓次數 | 自動從Silverpop匯入。 | 「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 |
| event(數值) | 傳送 | 自動從Silverpop匯入。 | 「傳送」事件可讓您查看傳送的電子郵件訊息數目。 |
| event(數值) | 取消訂閱 | 自動從Silverpop匯入。 | 「取消訂閱」事件可讓您查看開啓電子郵件訊息但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 |
| eVar | Silverpop ID/訪客ID | 透過自動化收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | 獨特訪客ID |
| eVar或s. campaign | Mailing ID | 透過自動化收集方法或JavaScript外掛程式，從電子郵件連結中的查詢參數收集。 | 這通常會儲存在促銷活動變數中。 |

## 選擇性變數 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| event(計數器) | 檔案已下載 | 透過Analytics標記手動收集。 | 此事件用於識別在網站上下載檔案的使用者。 |
| event(計數器) | 表單已開始 | 透過Analytics標記手動收集。 | 「表單開始」用於識別開始表單但未完成的使用者。 |
| event(計數器) | 表單填寫 | 透過Analytics標記手動收集。 | 「填寫完成」可用來識別開始表單且未完成表單的訪客。 |
| eVar | Email Address | 透過Analytics標記手動收集。 | 電子郵件地址是用於手動收集註冊、登入或其他電子郵件地址上的電子郵件地址。此變數用於重新行銷給選擇接收電子郵件的使用者，但過去可能尚未點進過電子郵件。 |
| eVar | 下載的檔案 | 透過Analytics標記手動收集。 | 下載的檔案會識別訪客下載的檔案。 |
| eVar | 表單名稱 | 透過Analytics標記手動收集。 | 「表單名稱」可識別訪客放棄的表單。 |

