---
title: 不同的機器人排除方法比較
description: 讓您比較不同的排除機器人方法。
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
TQID: 'https://experienceleague.adobe.com/lbb7D0NNvtqw-65JRgT-K7I1k0lBw2ekfcoOTAmbQi0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: ec140990-1570-4311-94d4-2d6b38511bbe
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 46%

---

# 不同的機器人排除方法比較

下表顯示不同的排除機器人方法以及彼此的比較結果。

| 方法 | 機器人規則 | 依 IP 位址排除 | 客戶屬性 | 區段 | 協力廠商評分 + 分段 | 在執行階段隱藏機器人的伺服器呼叫 | 自訂 DB VISTA 規則 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **排除資料方法說明** | 根據使用者代理、IP位址或IP位址範圍進行排除 | IP 位址 | 將ECID識別為機器人的客戶屬性中的旗標 | 根據機器人行為識別已知機器人的Analytics區段中的條件 | 第三方（例如[Perimeter X](https://www.perimeterx.com)或[Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp)）會針對每個頁面檢視成為機器人的可能性指定一個分數。 分數會被送進 Analytics，而區段可用於根據分數來篩選出資料。 | 使用者端邏輯會停止為機器人執行Analytics伺服器呼叫。 | VISTA規則會將流量從符合特定條件的機器人移動至單獨的報表套裝。 |
| **有機器人名稱可用於報告嗎？** | 是 | 無 | 否 | 否 | 否 | 無 | 是 |
| **能夠檢視哪些頁面正由機器人造訪中嗎？** | 是 | 無 | 否 | 無 | 是 | 無 | 是 |
| **發生機器人的伺服器呼叫成本？** | 是 | 是 | 是 | 是 | 是 | 無 | 是 |
| **資料摘要中是否有機器人資料？** | 否 | 無 | 是 | 無 | 是 | 無 | 是 |
| **是否能夠報告機器人流量，就好像它們是實際的伺服器呼叫？** | 否 | 無 | 是 | 是 | 是 | 無 | 否 |
| **是否可從資料集追溯移除資料？** | 否 | 否 | 是，實施宣告ID之後 | 是 | 是，實施評分之後 | 否 | 否 |
| **是否需遵循標準中規定的不重複限制？** | 否 | 否 | 無 | 是 | 無 | 否 | 否 |
| **是否有額外的費用？** | 否 | 否 | 有可能，依Analytics SKU而定 | 無 | 是 | 無 | 是 — 實作與維護VISTA規則的成本 |
