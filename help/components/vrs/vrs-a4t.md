---
description: 使用 A4T 和 Adobe Analytics 虛擬報表套裝時的特殊考量事項
title: 虛擬報表套裝和 Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%

---

# 虛擬報表套裝和 Analytics for Target (A4T)

在 Adobe Target 的環境中使用虛擬報表套裝，請考量以下注意事項：

* 您無法直接將 Target 中的資料傳送到虛擬報表套裝，只能傳送到真實的報表套裝。
* 您可以在虛擬報表套裝中報告 A4T 活動。 然而，A4T 資料僅限於符合虛擬報表套裝區段 (以及其他任何套用的區段) 的資料列。 例如，如果您為 EMEA 客戶建立了虛擬報表套裝，則該虛擬報表套裝中的 A4T 資料只會反映您的 EMEA 客戶的 Target 資料。
* 您無法將虛擬報表套裝中的區段發佈回 Target 來進行啟用。
