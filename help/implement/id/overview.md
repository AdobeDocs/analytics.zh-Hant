---
title: Adobe Analytics中的訪客身分識別
description: 瞭解如何使用最新最佳實務在Adobe Analytics中識別訪客。
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 17%

---

# Adobe Analytics中的訪客身分識別

訪客身分識別對於Adobe Analytics提供的瞭解線上使用者行為的值至關重要。 它涉及使用通用識別碼將點選隨時間連結至相同人員。 精確的訪客身分識別可確保可靠的量度，並支援健康的實作策略。 Adobe建議組織優先考慮現代化的身分識別服務，以提升各平台的一致性和資料完整性。

Adobe Analytics中的訪客身分識別包含下列元件：

* 使用者端識別碼：通常儲存在第一方Cookie中。 由於現今的瀏覽器隱私權標準，依賴第三方Cookie的實施與訪客身分識別不太一致。
* 伺服器端識別碼：每個Analytics訪客ID都會繫結至Adobe伺服器上的設定檔。 無論訪客 ID Cookie 過期與否，這些訪客輪廓只要閒置至少 13 個月，就會遭到刪除。

## Adobe Analytics識別作業順序

Adobe收到點選時，會依序進行下列檢查。 如果特定屬性存在，Adobe會使用該識別碼進行點選。 如果點選中有多個識別碼，則只會使用第一個方法。

| 使用的順序 | 查詢參數 | 顯示時機 |
|---|---|---|
| **1<sup>st</sup>** | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 變數已設定。 |
| **2<sup>nd</sup>** | `aid` | 訪客有現有的[`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。 在不實作訪客 ID 服務的情況下或實作該服務之前，設定於實作上。 |
| **3<sup>rd</sup>** | `mid` | 訪客有現有的[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。 在使用[Adobe Experience Cloud Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)的實施上設定。 Adobe建議儘可能將ID服務用於所有實作。 |
| **4<sup>th</sup>** | `fid` | 訪客有現有的[`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) Cookie，或因任何原因而無法設定`aid`和`mid`。 |
| **5<sup>th</sup>** | IP 位址、使用者代理、閘道 IP 位址 | 當訪客的瀏覽器不接受Cookie時，作為最後的手段用來識別不重複訪客。 |

## 影響不重複訪客計數的行為

不重複訪客識別碼通常會儲存在瀏覽器 Cookie 中。如果發生下列任一情況，則會計為新的不重複訪客：

* 隨時清除其Cookie。 每次清除其快取後，點選會計為一位不重複訪客。
* 訪客ID Cookie會因瀏覽器的隱私權設定而過期。 許多現代瀏覽器都包含某種形式的預防追蹤。
* 在同一部電腦上開啟不同的瀏覽器。每個瀏覽器各會計算一個不重複訪客。
* 開啟私人瀏覽工作階段(例如Chrome的「無痕」標籤)。 所有索引標籤關閉後，每個瀏覽工作階段各會計算一個不重複訪客。
* 在不同裝置上造訪您的網站。 每個裝置各會計算一個不重複訪客。
* 閒置超過13個月後造訪您的網站。

請考慮使用Customer Journey Analytics中的[拼接](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview)，使用多個瀏覽器或多個裝置來識別同一個人。

## 不影響不重複訪客計數的行為

只要保留訪客識別碼，就不會計算新的不重複訪客&#x200B;**：

* 關閉瀏覽器（少於13個月）
* 將其瀏覽器升級至最新版本
* 重新啟動電腦
