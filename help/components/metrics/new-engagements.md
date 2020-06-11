---
title: 新增參與
description: 首次接觸渠道的設定次數。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---


# 新增參與

「新增參與」度量顯示訪客參與期間首次符合行銷渠道的次數。 當您想要將任何維度與首次符合行銷渠道處理規則的訪客進行比較時，此度量很有用。

## 此度量的計算方式

在資料處理期間，每次點擊都會透過 [行銷渠道處理規則執行](../c-marketing-channels/c-rules.md)。 如果點擊符合任何行銷渠道處理規則，且訪客尚未擁有首次接觸渠道，則點擊是新的參與。 如果點擊不符合任何行銷渠道處理規則，或如果訪客已有首次接觸渠道，則點擊不是新的參與。

如果訪客的訪客參與期間過期，則可以有多個新參與。