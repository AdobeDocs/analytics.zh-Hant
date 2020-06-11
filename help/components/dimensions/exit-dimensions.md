---
title: 退出維度
description: 列出退出維度及其使用。
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# 退出維度

*此說明頁面說明退出作為維度的運作方式。 如需退出作為度量運作的詳細資訊，請參閱退出[度量](../metrics/exits.md)。*

退出維度會記錄最後一個維度值，並追溯套用至瀏覽中的所有點擊。 退出維度適用於所有在「報表套裝」設定中的「流量變數」 [下啟用路徑](/help/admin/admin/c-traffic-variables/traffic-var.md) 的變數。

## 以資料填入退出維度

指定的退出維度是以其關聯的流量變數為基礎。 如果非退出變數有資料，其關聯的退出維度也包含資料。 如果您的流量變數包含資料，退出維度不需要實施變更。

## 維度值

由於退出變數通常以實作中的自訂字串為基礎，因此您的組織會決定維度值。 給定退出維中的值與其關聯的非退出維中的維值匹配。 例如，「退出頁面」維度中的維度值在「頁面」維度中包含類似的維度值。
