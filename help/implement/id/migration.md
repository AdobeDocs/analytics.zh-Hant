---
title: Adobe Analytics的訪客ID服務移轉考量事項
description: 概述Adobe Analytics與訪客ID服務的介面。
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 2%

---

# Adobe Analytics的訪客ID服務移轉考量事項

如果您的組織打算使用現有的Analytics實作改用訪客ID服務，有些重要主題值得考慮。 這些考量事項可讓您維持訪客身分識別的完整性，並瞭解訪客ID服務在現有Analytics實作情況下的運作方式。

>[!TIP]
>
>此頁面僅適用於現有的AppMeasurement或Analytics擴充功能實作，且正在新增訪客ID服務或升級至網路SDK實作。 換言之，您的實作使用舊版Analytics ID (`aid`)，而正在改用ECID (`mid`)。 所有Web SDK實作都使用[Experience Platform Identity Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/home)，預設會使用ECID (`mid`)。

## 訪客ID服務如何與舊版Analytics訪客Cookie介面

由於AppMeasurement有其專屬的舊式方法來識別訪客，因此當組織部署訪客ID服務時，某些訪客可能會有現有的Analytics Cookie。 下列清單概述在不同情況下如何識別訪客。

* **沒有訪客Cookie**：訪客ID服務會指派ECID (`mid`)。
* **`s_vi` Cookie存在**：訪客ID服務除了ECID (`mid`)之外，還會將現有的舊版Analytics ID (`aid`)寫入`AMCV` Cookie。 由於`aid`在[操作順序](overview.md)中較高，在`AMCV` Cookie過期或被清除之前，舊版Analytics ID都是訪客識別碼。 啟用寬限期時，訪客ID服務會在其回應中同時包含`mid`和`aid`。
* **備援Cookie存在**：訪客ID服務未將備援Cookie (`fid`)寫入`AMCV` Cookie。 相反地，訪客會收到ECID (`mid`)，就像他們是新訪客一樣。

## 訪客ID服務寬限期

如果您有多個將資料傳送至相同報表套裝的實作，而且只能對某些實作實作實施訪客ID服務，Adobe建議您設定寬限期。 例如，若您網站的支援區段是由獨立的標籤解決方案所管理，您可能會將訪客ID服務部署在網站其餘部分的支援區段之前。 如果沒有寬限期，檢視支援區段的新訪客會收到舊版Analytics訪客ID，導致系統計算兩個不同的訪客。 若使用寬限期，訪客ID服務會同時發出ECID (`mid`)和舊版Analytics訪客ID (`aid`)，如此一來您網站中沒有訪客ID服務的區域將能持續識別訪客。

如果您在網站的所有區域間協調訪客ID服務的部署，就不需要寬限期。 若要設定寬限期，請連絡[Adobe客戶服務](https://helpx.adobe.com/tw/marketing-cloud/contact-support.html)。 寬限期最多可設定180天，且可續約。 Adobe建議您在整個屬性設定為使用訪客ID服務後，停止寬限期。

## 跨網域追蹤

有些舊版Analytics訪客ID實作可能會使用「友善的第三方Cookie」，也就是兩個網域在像`data.example.com`這樣的通用網域上共用相同的訪客Cookie。 由於好記的第三方Cookie仍是第三方Cookie，許多現代瀏覽器會加以拒絕，導致Analytics依賴備援ID (`fid`)來識別訪客。 移至訪客ID服務可讓所有網域在第一方內容中設定`AMCV` Cookie，增加其保留訪客ID的可行性。

當訪客ID服務嘗試設定跨網域追蹤的第三方Cookie ([`demdex` Cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies))時，它經常被現代瀏覽器拒絕。 請考慮使用[`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid)方法，在您擁有的網域之間傳遞訪客的ECID (`mid`)。

## 伺服器端追蹤

您可以呼叫[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)以取得ECID (`mid`)和[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid)以取得舊版Analytics ID (`aid`)。 Adobe建議同時檢查兩者，以保留訪客身分識別邏輯。
