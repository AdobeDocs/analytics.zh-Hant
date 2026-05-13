---
description: 使用 A4T 和 Adobe Analytics 虛擬報表套裝時的特殊考量事項
title: 虛擬報表套裝和 Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 100%

---

# 虛擬報表套裝和 Analytics for Target (A4T)

在 Adobe Target 的環境中使用虛擬報表套裝，請考量以下注意事項：

* 您無法直接將 Target 中的資料傳送到虛擬報表套裝，只能傳送到真實的報表套裝。
* 您可以在虛擬報表套裝中報告 A4T 活動。 然而，A4T 資料僅限於符合虛擬報表套裝區段 (以及其他任何套用的區段) 的資料列。 例如，如果您為 EMEA 客戶建立了虛擬報表套裝，則該虛擬報表套裝中的 A4T 資料只會反映您的 EMEA 客戶的 Target 資料。
* 您無法將虛擬報表套裝中的區段發佈回 Target 來進行啟用。
