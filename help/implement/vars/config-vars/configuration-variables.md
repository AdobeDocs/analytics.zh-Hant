---
title: 設定變數
description: 使用設定變數協助判斷資料的收集方式。
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 19%

---

# 設定變數概觀

設定變數會控制資料在報表中擷取及處理的方式。 這些變數通常不包含維度或量度值。

## 配置設定變數

在使用Web SDK擴充功能或Analytics擴充功能的實作中，通常會從擴充功能的設定中找到設定變數：

1. 使用您的Adobe Experience Platform認證登入[Adobe ID資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下[擴充功能]索引標籤]，然後按一下擴充功能下方的[設定]。[!UICONTROL 

在使用 `AppMeasurement.js` 的 JavaScript 實施中，通常會在 JS 檔案的頂端對配置設定變數。

>[!IMPORTANT]
>
>呼叫追蹤方法（[`t()`](../functions/t-method.md)或[`tl()`](../functions/tl-method.md)）之前，請確定所有設定變數均已設定完畢。 請避免在 [`doPlugins()`](../functions/doplugins.md) 函數中配置設定變數。

## 淘汰的設定變數

下列設定變數已淘汰。 如果您在舊版實作中遇到這些錯誤，請參考這裡檔案。

* **`account`**：已決定資料要傳送到的報表套裝。 報表套裝現在已透過追蹤物件例項化（[`s_gi()`](../functions/s-gi.md)方法）處理。 如果您需要在追蹤物件例項化後變更報表套裝，請使用[`s.sa()`](../functions/sa-method.md)方法。
* **`cookieDomain`**：已判斷AppMeasurement設定Cookie的網域。 目前版本的AppMeasurement會自動偵測正確的Cookie網域，使此變數過時。
* **`cookieDomainPeriods`**：協助AppMeasurement判斷當網域包含多個句號時儲存Cookie的位置。 目前版本的AppMeasurement會自動偵測正確的網域，使此變數過時。
* **`fpCookieDomainPeriods`**： `cookieDomainPeriods`的第一方對等項，用來在第一方網域的尾碼包含額外句號（例如`example.co.uk`）時在正確位置設定Cookie。 目前版本的AppMeasurement會自動偵測正確的網域，使此變數過時。
* **`trackingServer`**：指定用來透過HTTP傳送資料給Adobe的網域。 它已被取代，代之以安全資料收集而非HTTPS。 請改用 [`trackingServerSecure`](trackingserversecure.md)。
* **`trackInlineStats`**：啟用或停用舊版[Activity Map](/help/analyze/activity-map/overview.md)。
* **`visitorMigrationKey`**：攜帶用來將訪客從第三方移轉至第一方Cookie的金鑰。 已淘汰，因為現代資料庫會設定第一方備援Cookie (`fid`)，並依賴訪客ID服務來取得身分。
* **`visitorMigrationServer`**：指定在第三方到第一方Cookie移轉期間使用的伺服器。
* **`visitorMigrationServerSecure`**： `visitorMigrationServer`的HTTPS對等項。
* **`visitorNameSpace`**：協助判斷第三方Cookie網域。 已淘汰，改用[`trackingServerSecure`](trackingserversecure.md)變數用於未使用訪客ID服務的實作。
