---
description: 'null'
keywords: DFA
title: 常見問題集
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 常見問題集{#frequently-asked-questions}

## 為何 Data connectors 精靈不接受我的登入認證？{#section-f019b3de18774df3954af7881aa564fa}

如果您已驗證登入認證是否有效，請接著驗證提供給整合的使用者名稱是否已啟用API存取。 「資料連接器」精靈會使用DFA API來驗證登入憑證，以及在DFA API中關閉和開啟Adobe特定設定。 「API存取」是必須由管理員在DFA介面中開啟的設定。 接著，請確定您擁有存取精靈中選取之廣告商ID或Floodlight設定ID的權限。

## 為何我看不見任何夜間上傳量度的資料 (DFA 曝光數、DFA 點按等)?  {#section-465fd22ae6b447ffb6baf20b57daa433}

如果您使用1.5版的整合，可能是因為您的整合尚未指派用戶端網站ID。 需要用戶端網站ID(CSID)才能進行夜間交換，並向DFA廣告伺服器要求資料。 CSID在整合日期起最多需要3天，才能與Google交換。 接收到 Google 提供的 CSID 後，系統會透過整合的電子郵件地址告知您新的 CSID，以及最新的 JavaScript 代碼。

如果超過3天而您尚未收到設定電子郵件且量度不會流動，則最可能的問題是CSID已指派給其他整合。 Google會維護CSID和報表套裝之間的1到1對應，這表示如果一個報表套裝中的整合使用與另一個報表套裝中的另一個整合相同的廣告商ID，則只有第一個整合會獲得CS ID。 若要變更CSID對應至的報表套裝或廣告商ID，必須使用Google支援開啟票證。

例如，假設報表套裝A與廣告商ID Z有整合，並指派了CSID。 如果報表套裝B中稍後設定了另一個與廣告商Z的整合，則此較新的整合將不會重新指派CSID。 這需要Google票證。 另一方面，以報表套裝A中與廣告商ID Z的整合為例，以及報表套裝A中的其他整合為例，設定了廣告商Z。 只有第一個整合會收到整合的資料；不過，在此情況下，第一個整合可以停用，而資料會流入第二個整合。

>[!NOTE] CSID 不會在 2.0 版的整合中使用，因此 CSID 交涉程序並不適用。

## 我使用2.0版的整合，而DFA廣告不會顯示成本量度。 為什麼會這樣?  {#section-805748111bbe4bbf918d6dbbb2641fff}

成本量度必須同時從Google DFA端開啟，並在DFA介面中提供，以及在「資料連接器」精靈中開啟。 首先要驗證的是，您已將Analytics事件對應至DFA媒體成本，並提供貨幣代碼。 如果您已對應「媒體成本」事件，並完成並儲存精靈，DFA API中將會開啟DFA omnitureCostData標幟。 這會向Google發出訊號，指出量度應在夜間檔案中傳送。 您可以透過DFA介面，透過檢視整合Floodlight的屬性，再次檢查omnitureCostData是否已啟用。 最後，在檢查這兩處之後，請確定屬於整合Floodlight的廣告會指定成本資料和成本結構。 如果DFA介面中未提供成本資料，則不會在Analytics中顯示。

## 為何有某些廣告不會顯示任何 DFA 曝光數或閱覽，但會顯示點按和點進?  {#section-39b2eeeefd7f43d1a373df0b987bacef}

有些廣告只記錄點按資料，稱為點按追蹤器。 這些類型的廣告不會傳回查詢Floodlight伺服器時的最後印象資料。 若要確認某個廣告是點按追蹤器還是僅點按廣告，請連絡您的DFA機構或您的Google支援代表。

## 為何顯示 DFA 點按的廣告沒有任何點進？{#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

對此，有許多答案。

首先，檢查相關廣告是否有著陸頁面URL，其中(a)針對您檢視不一致的相同報表套裝加上Adobe程式碼標籤，且(b)包含查詢字串參 *`clickThroughParam`* 數。

其次，請依照[確認成功的 DFA 整合](../dfa-data-connector-analytics/dfa-integration.md)中的步驟，確認您具備有效的整合。如果您在著陸頁面上看見具有 Adobe 點擊的 DFA 追蹤代碼，則應該會在 DFA 促銷活動報表中看見點進。如果您未看到報表套裝傳入，請確認報表套裝符合登陸頁面的 *`s.account`* 變數，以及「報表與分析」中正在檢視的報表套裝。如果符合，請在「檢視eVar」報表中檢查追蹤代碼，其外觀類似DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX。

這表示DFA VISTA規則無法摘取DFA的原始資料。 您可以透過Adobe帳戶代表開立支援票證來修正此問題。

如果上述所有解決方案都未說明問題，請參閱協調 [量度差異](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) ，以探索其他可能性。
