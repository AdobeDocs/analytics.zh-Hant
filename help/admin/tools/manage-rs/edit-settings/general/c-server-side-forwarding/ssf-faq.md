---
description: 關於伺服器端轉送的特色、功能及問題的常見問題。
title: 伺服器端轉送常見問題集
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: https://experienceleague.adobe.com/3i6RY7JRPlJc-9NjsQXBPn5SEOn0m4JrtL85Kl84ilM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 74%

---

# 伺服器端轉送常見問題集

關於伺服器端轉送的特色、功能及問題的常見問題。

## 追蹤伺服器 {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 問題 | 回答 |
|--- |--- |
| 問：如果我目前是使用舊版追蹤伺服器的伺服器端轉送會發生什麼事？ | 舊版追蹤伺服器的伺服器端轉送方法仍會繼續將資料從Analytics轉送至Audience Manager，不過如果您想要將Audience Manager區段傳送至Analytics，則需要全新的報表套裝伺服器端轉送。 此外，在您的追蹤伺服器設定之上為報表套裝啟用伺服器端轉送並無壞處 — 每當衝突發生時，都會使用新的報表套裝伺服器端轉送設定。 |
| 問：我應該將舊版追蹤伺服器的伺服器端轉送，移轉至新的報表套裝伺服器端轉送嗎？ | 在可預見的將來，我們仍會持續支援追蹤伺服器的伺服器端轉送，不過如果您想要利用從Audience Manager到Analytics的整合（區段共用到Analytics），則您需要為所有適用的報表套裝啟用新的報表套裝伺服器端轉送。 不過，我們目前並沒有迫切需要停用舊版追蹤伺服器的伺服器端轉送。 |

## 標籤和報告 {#section_71391BA901AC47B9A2286281644FF281}

| 問題 | 回答 |
|--- |--- |
| 問：假如我的網站上有多套裝標記會發生什麼事？ 伺服器端轉送會將對 Audience Manager 的伺服器呼叫數加倍嗎？ | 不會，無論點擊中的報表套裝數量多寡，從 Analytics 轉送至 Audience Manager 的點擊都只會轉送至 Audience Manager 一次。 如果您在 Audience Manager 中擁有點擊中每個報表套裝的相對應資料來源，系統將會從該單一點擊正確填入每個報表套裝。  不過請記住，如果您目前使用用戶端資料收集 (DIL)，並在未安裝「對象管理模組」的情況下啟用伺服器端轉送，則無論您在 Analytics 點擊中有多少報表套裝，都會使對 Audience Manager 的伺服器呼叫數加倍。 |
| 問：如果我有已對應至不同 Experience Cloud 組織的多套裝標記報表套裝，會發生什麼事？ | 您不應該將單一 Analytics 點擊的資料傳送至屬於不同 Experience Cloud 組織的兩個報表套裝，但如果此情況已發生，我們只會將點擊轉送至頁面上與身分識別服務設定相符的 Experience Cloud 組織。 |
| 問：如果我有多套裝標記，但只有其中一個報表套裝有對應至我的 Experience Cloud 組織，其他則沒有時該怎麼辦？ | 我們會針對已對應報表套裝上的 Experience Cloud 組織，將點擊轉送至相對應的資料收集伺服器，但是由於非對應的報表套裝在 Audience Manager 中不會有相關的資料來源，因此系統不會在 Audience Manager 中記錄非對應報表套裝的任何資料。 |
| 問：如果我有已對應至多個 Experience Cloud 組織的報表套裝，會發生什麼事？ | Analytics會將此報表套裝視為未對應，不允許為此報表套裝啟用伺服器端轉送。 請聯絡客戶服務以解決此對應問題。 |
| 問：報表套裝的伺服器端轉送方法會比追蹤伺服器的伺服器端轉送來得慢嗎？ | 不會，兩者的回應時間會相同。 |
| 問：如果我們有兩個 Experience Cloud 組織 (或 Adobe Audience Manager 例項)，且想要在這兩個 Experience Cloud 組織之間共用資料，該怎麼做？ 我是否可以透過伺服器端轉送將單一 Analytics 點擊轉送至多個 Experience Cloud 組織？ | 不可以。 如果您需要將在某個 Experience Cloud 組織底下收集的資料分享至其他 Experience Cloud 組織，我們建議您使用對象市集，將任何適用對象從某個 Audience Manager 例項傳送至另一個例項。 |
| 問：伺服器端轉送在 Audience Manager 或 Analytics 中需要額外付費嗎？ | 在 Analytics 中不需要額外付費。 在 Audience Manager 中，轉送的點擊會被視為與任何其他點擊一樣，且必須付費。  這就是切勿同時啟用 DIL 和伺服器端轉送的原因，因為這麼做可能會造成費用加倍和資料重複。 |

>[!MORELIKETHIS]
>
>* [伺服器端轉送功能](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
