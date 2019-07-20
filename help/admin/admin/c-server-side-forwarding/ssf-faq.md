---
description: 關於伺服器端轉送的特色、功能及問題的常見問題。
seo-description: 關於伺服器端轉送的特色、功能及問題的常見問題。
seo-title: 伺服器端轉送常見問題
title: 伺服器端轉送常見問題
uuid: decd0bc9b-ef7-414e-88a2-eba3 fd75 c92
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 伺服器端轉送常見問題

關於伺服器端轉送的特色、功能及問題的常見問題。

## 追蹤伺服器 {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 問題 | 回答 |
|--- |--- |
| 問: 如果我目前是使用舊版追蹤伺服器的伺服器端轉送會發生什麼事? | 舊版追蹤伺服器的伺服器端轉送方法會持續將資料從 Analytics 轉送至 Audience Manager，但是如果您要將 Audience Manager 區段傳送至 Analytics，則需要新的報表套裝伺服器端轉送。此外，在追蹤伺服器設定上啟用報表套裝的伺服器端轉送不會造成任何損害，每當發生衝突時，系統將會使用新的報表套裝伺服器端轉送設定。 |
| 問: 我應該將舊版追蹤伺服器的伺服器端轉送移轉至新的報表套裝伺服器端轉送嗎? | 在可見的未來，我們仍會持續支援以追蹤伺服器為基礎的伺服器端轉送，但是如果您想要運用從 Audience Manager 到 Analytics (分享至 Analytics 的區段) 的整合，則必須對所有適用的報表套裝啟用新的報表套裝伺服器端轉送。不過，目前仍無須立即停用舊版追蹤伺服器的伺服器端轉送。 |

## 標記和報告 {#section_71391BA901AC47B9A2286281644FF281}

| 問題 | 回答 |
|--- |--- |
| 問: 假如我的網站上有多套裝標記會發生什麼事? 伺服器端轉送會將對 Audience Manager 的伺服器呼叫數加倍嗎? | 不會，無論點擊中的報表套裝數量多寡，從 Analytics 轉送至 Audience Manager 的點擊都只會轉送至 Audience Manager 一次。如果您在 Audience Manager 中擁有點擊中每個報表套裝的相對應資料來源，系統將會從該單一點擊正確填入每個報表套裝。不過請記住，如果您目前使用用戶端資料收集 (DIL)，並在未安裝「對象管理模組」的情況下啟用伺服器端轉送，則無論您在 Analytics 點擊中有多少報表套裝，都會使對 Audience Manager 的伺服器呼叫數加倍。 |
| 問：如果我已將多套裝標記報表套裝對應至個別的Experience Cloud組織，該怎麼辦？ | 您不應將資料從單一Analytics點擊傳送至屬於個別Experience Cloud組織的兩個報表套裝，但如果發生這種情況，我們只會將點擊轉送至頁面上的Identity Service設定相符的Experience Cloud組織。 |
| 問：如果我有多套裝標記，而其中只有其中一個報表套裝對應至我的Experience Cloud Org，而另一個報表套裝不正確，該怎麼辦？ | 我們會將點擊轉送至對應報表套裝上的Experience Cloud組織對應資料收集伺服器，不過，由於未對應的報表套裝在Audience Manager中將不會有相關聯的資料來源，因此Audience Manager中未映射的報表套裝不會記錄資料。 |
| 問：如果我的報表套裝已對應至多個Experience Cloud組織，該怎麼辦？ | Analytics 會將此報表套裝視為未對應，且不會為此報表套裝啟用伺服器端轉送。請連絡客戶服務以解決此對應問題。 |
| 問: 報表套裝的伺服器端轉送方法會比追蹤伺服器的伺服器端轉送來得慢嗎? | 不會，兩者的回應時間會相同。 |
| 問：如果我們有兩個Experience Cloud組織(或AAM例項)，並想要在Experience Cloud組織之間共用資料，該怎麼辦？我是否可將單一Analytics點擊轉送至多個Experience Cloud組織？ | 不會。如果您需要將收集到的資料共用至另一個Experience Cloud組織，我們建議您使用觀眾市場將任何適用的受眾從一個Audience Manager實例傳送至另一個。 |
| 問: 伺服器端轉送在 Audience Manager 或 Analytics 中需要額外付費嗎? | 在 Analytics 中不需要額外付費。在 Audience Manager 中，轉送的點擊會被視為與任何其他點擊一樣，且必須付費。這就是切勿同時啟用 DIL 和伺服器端轉送的原因，因為這麼做可能會造成費用加倍和資料重複。 |

>[!MORE_LIKE_THIS]
>
>* [伺服器端轉送功能](ssf.md#concept_9563FCADF29748928E770EC5221B2685)

