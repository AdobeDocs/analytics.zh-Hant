---
title: Adobe Analytics的訪客ID服務移轉考量事項
description: 概述Adobe Analytics與訪客ID服務的介面。
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Adobe Analytics的訪客ID服務移轉考量事項

如果您的組織打算使用現有的Analytics實作改用訪客ID服務，有些重要主題值得考慮。 這些考量事項對於維持訪客身分識別的完整性，以及瞭解ID服務在存在現有Analytics實作時如何運作非常重要。

## 訪客ID服務如何與舊版Analytics訪客Cookie介面

由於AppMeasurement有專屬的識別訪客方法，因此當組織部署訪客ID服務時，有些訪客可能會有舊有的Analytics Cookie。 下列清單概述在不同情況下如何識別訪客。

* **沒有訪客Cookie**： ID服務會指派Experience Cloud ID (`mid`)。
* **`s_vi` Cookie存在**： ID服務除了Experience Cloud ID (`aid`)之外，還會將現有的舊版Analytics ID (`AMCV`)寫入`mid` Cookie。 由於`aid`在[操作順序](overview.md)中較高，在`AMCV` Cookie過期或被清除之前，舊版Analytics ID都是訪客識別碼。 啟用寬限期時，ID服務會在其回應中同時包含`mid`和`aid`。
* **備援Cookie存在**： ID服務未將備援Cookie (`fid`)寫入`AMCV` Cookie。 相反地，訪客會收到Experience Cloud ID (`mid`)，就好像他們是新訪客一樣。

## 訪客ID服務寬限期

如果您有多個將資料傳送至相同報表套裝的實作，而且只能對某些實作實作實施訪客ID服務，Adobe建議您設定寬限期。 例如，若您網站的支援區段是由獨立的標籤解決方案所管理，您可能會將訪客ID服務部署在網站其餘部分的支援區段之前。 如果沒有寬限期，檢視支援區段的新訪客會收到舊版Analytics訪客ID，導致系統計算兩個不同的訪客。 若使用寬限期，訪客ID服務會同時發出Experience Cloud ID (`mid`)和舊版Analytics訪客ID (`aid`)，讓沒有ID服務的網站區域能持續識別訪客。

如果您在網站的所有區域間協調訪客ID服務的部署，就不需要寬限期。 若要設定寬限期，請連絡[Adobe客戶服務](https://helpx.adobe.com/tw/marketing-cloud/contact-support.html)。

## 跨網域追蹤

有些舊版Analytics訪客ID實作可能會使用「友善的第三方Cookie」，也就是兩個網域在像`data.example.com`這樣的通用網域上共用相同的訪客Cookie。 由於友善的第三方Cookie仍是第三方Cookie，因此大部分的現代瀏覽器都會加以拒絕，導致Analytics仰賴備援ID (`fid`)來識別訪客。 移至ID服務可讓所有網域在第一方內容中設定`AMCV` Cookie，增加其保留訪客ID的可行性。

當訪客ID服務嘗試為跨網域追蹤設定第三方Cookie ([`demdex` Cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies))時，它經常被大多數的現代瀏覽器拒絕。 請考慮使用[`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid)方法，在您擁有的網域之間傳遞Experience Cloud ID。

## 伺服器端追蹤

您可以呼叫[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)以取得Experience Cloud ID (`mid`)和[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid)以取得舊版Analytics ID (`aid`)。 Adobe建議同時檢查兩者，以保留訪客身分識別邏輯。
