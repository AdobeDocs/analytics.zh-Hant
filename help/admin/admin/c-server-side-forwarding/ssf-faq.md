---
description: 關於伺服器端轉送的特色、功能及問題的常見問題。
title: 伺服器端轉送常見問題集
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 伺服器端轉送常見問題集

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
| 問：如果我的多套裝標籤報表套裝已對應至個別的Experience cloud組織，該怎麼辦？ | 您絕不應將單一Analytics點擊的資料傳送至屬於個別Experience cloud組織的兩個報表套裝，但如果發生此情況，我們只會將點擊轉送至符合頁面上Identity service設定的Experience cloud組織。 |
| 問：如果我有多套裝標籤，且只有一個報表套裝對應至我的Experience cloud組織，而另一個則不對應，該怎麼辦？ | 我們會將點擊轉送至您映射報表套裝上Experience cloud組織的對應資料收集伺服器，但由於非映射報表套裝在Audience Manager中沒有關聯的資料來源，因此Audience manager中不會記錄未映射報表套裝的任何資料。 |
| 問：如果我的報表套裝已對應至多個Experience cloud組織，該怎麼辦？ | Analytics 會將此報表套裝視為未對應，且不會為此報表套裝啟用伺服器端轉送。請連絡客戶服務以解決此對應問題。 |
| 問: 報表套裝的伺服器端轉送方法會比追蹤伺服器的伺服器端轉送來得慢嗎? | 不會，兩者的回應時間會相同。 |
| 問：如果我們有兩個Experience cloud組織（或AAM例項），並且想要在兩個Experience cloud組織之間共用資料，該怎麼辦？ 我是否可在伺服器端將單一Analytics點擊轉送至多個Experience cloud組織？ | 不會。如果您需要將在一個Experience cloud組織下收集的資料共用至另一個Experience cloud組織，我們建議您使用觀眾市場將任何適用的觀眾從一個Audience manager例項傳送至另一個。 |
| 問: 伺服器端轉送在 Audience Manager 或 Analytics 中需要額外付費嗎? | 在 Analytics 中不需要額外付費。在 Audience Manager 中，轉送的點擊會被視為與任何其他點擊一樣，且必須付費。這就是切勿同時啟用 DIL 和伺服器端轉送的原因，因為這麼做可能會造成費用加倍和資料重複。 |

>[!MORELIKETHIS]
>
>* [伺服器端轉送功能](/help/admin/admin/c-server-side-forwarding/ssf.md)

