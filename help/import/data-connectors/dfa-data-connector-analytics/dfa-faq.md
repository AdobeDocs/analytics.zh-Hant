---
description: 'null'
keywords: DFA
title: 常見問題集
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 常見問題集{#frequently-asked-questions}

## 為何 Data connectors 精靈不接受我的登入認證？{#section-f019b3de18774df3954af7881aa564fa}

如果您確認登入認證是有效的，請接著確認已為提供給整合的使用者名稱啟用 API 存取。Data connectors 精靈會使用 DFA API 來驗證登入認證，以及關閉和開啟 DFA API 中的 Adobe 特定設定。「API 存取」是必須由系統管理員從 DFA 介面中開啟的設定。接下來，請確定您有權存取在精靈中選取的廣告主 ID 或 Floodlight 設定 ID。

## 為何我看不見任何夜間上傳量度的資料 (DFA 曝光數、DFA 點按等)? {#section-465fd22ae6b447ffb6baf20b57daa433}

如果您使用 1.5 版的整合，則可能是因為您的整合尚未被指派客戶網站 ID。要執行夜間交換以及要求 DFA 廣告伺服器的資料，必須要有客戶網站 ID (CSID)。從整合當天起算，CSID 最多要 3 天才能與 Google 進行交換。接收到 Google 提供的 CSID 後，系統會透過整合的電子郵件地址告知您新的 CSID，以及最新的 JavaScript 代碼。

如果在 3 天之後您仍未收到設定電子郵件，且量度並未傳遞，則最有可能的問題是 CSID 已指派給其他整合。Google 會保有 CSID 與報表套裝之間的 1 對 1 對應，這表示，如果一個報表套裝中的整合所使用的廣告主 ID 與另一個報表套裝中的其他整合相同，將只有第一個整合會被指派 CS ID。若要變更 CSID 所要對應到的報表套裝或廣告主 ID，必須透過支援人員開立票證。

例如，假設報表套裝 A 中有廣告主 ID 為 Z 的整合，被指派了一個 CSID。如果後續在報表套裝 B 中特定了另一個廣告主 ID 為 Z 的整合，系統將不會再次為這個較新的整合指派 CSID。這時候將需要 Google 票證。另一方面，以報表套裝 A 中具有廣告主 ID Z 的整合為例，假設後續在報表套裝 A 中設定了另一個廣告主 Z 的整合。只有第一個整合會接收到整合的資料；但在此情況下，第一個整合可以停用，而資料將會傳遞到第二個整合。

> [!NOTE] CSID 不會在 2.0 版的整合中使用，因此 CSID 交涉程序並不適用。

## 我使用 2.0 版的整合，但並未出現我的 DFA 廣告的成本量度。為什麼會這樣? {#section-805748111bbe4bbf918d6dbbb2641fff}

成本量度必須在 Google DFA 端開啟並提供於 DFA 介面中，同時也須在 Data connectors 精靈中開啟。首先應確認的是，您已對應 DFA 媒體成本的 Analytics 事件，並提供貨幣代碼。如果您已對應媒體成本事件，並且完成並儲存精靈，則 DFA API 將會開啟 DFA omnitureCostData 旗標。這會告知 Google 這些量度應在夜間檔案中傳送。您可以透過 DFA 介面查看已整合之 Floodlight 的屬性，以進一步確認 omnitureCostData 已啟用。在檢查過這兩處後，最後請確定屬於已整合之 Floodlight 一部分的廣告是否指定了成本資料和成本結構。成本資料若未提供在 DFA 介面中，則不會顯示在 Analytics 中。

## 為何有某些廣告不會顯示任何 DFA 曝光數或閱覽，但會顯示點按和點進? {#section-39b2eeeefd7f43d1a373df0b987bacef}

有些廣告只會記錄點按資料，我們稱之為點按追蹤。這些類型的廣告不會傳回自查詢 Floodlight 伺服器起的最後一個曝光數資料。若要確認某個廣告是點按追蹤廣告還是純點按廣告，請連絡您的 DFA 代理商或 Google 支援人員。

## 為何顯示 DFA 點按的廣告沒有任何點進？{#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

此問題有許多可能的成因。

首先，請確認有問題的廣告具有下列型態的著陸頁面: (a) 已為您要檢視差異的相同報表套裝加上 Adobe 代碼的標記，且 (b) 包含&#x200B;*`clickThroughParam`*&#x200B;查詢字串參數。

其次，請依照[確認成功的 DFA 整合](../dfa-data-connector-analytics/dfa-integration.md)中的步驟，確認您具備有效的整合。如果您在著陸頁面上看見具有 Adobe 點擊的 DFA 追蹤代碼，則應該會在 DFA 促銷活動報表中看見點進。如果您未看到報表套裝傳入，請確認報表套裝符合登陸頁面的 *`s.account`* 變數，以及「報表與分析」中正在檢視的報表套裝。如果相符，請在閱覽 eVar 報表中檢查顯示如下的追蹤代碼: DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX。

這些代碼表示 DFA VISTA 規則無法從 DFA 摘錄原始資料。此問題是可以修正的；請透過 Adobe 帳戶代表開立支援票證。

如果前述解決方案都未涵蓋您的問題，請參閱[協調量度差異](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md)以探索其他可能性。
