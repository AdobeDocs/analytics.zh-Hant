---
description: '使用A4T和Adobe Analytics虛擬報表套裝時的特殊考量 '
title: 虛擬報表套裝和Analytics for Target(A4T)
source-git-commit: 6a47ebc58cb36079940cfc4e5cdc80cf99c18a50
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# 虛擬報表套裝和Analytics for Target(A4T)

在Adobe Target中使用虛擬報表套裝時，請注意以下幾點：

* 您無法直接將資料從Target傳送至虛擬報表套裝，而只傳送至真實的報表套裝。
* 您可以報告虛擬報表套裝中的A4T活動。 不過，A4T資料僅限於符合虛擬報表套裝區段（以及套用的任何其他區段）的列。 例如，如果您為EMEA客戶建立虛擬報表套裝，則該虛擬報表套裝中的A4T資料只會反映EMEA客戶的Target資料。
* 您無法將虛擬報表套裝中的區段發佈回Target以進行啟用。