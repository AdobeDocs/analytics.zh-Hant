---
title: 上次購買間隔天數
description: 目前點擊與上次進行購買的間隔天數。
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 84%

---

# 上次購買間隔天數

「上次購買間隔天數」維度[維度](overview.md)會測量訪客目前的點選與當時最近一次購買之間所經過的時間量。 此維度可協助您了解訪客在您網站上購買商品後的行為。

從未購買過商品的訪客不會納入此維度中。 此外，訪客首次購買前引發的點擊也不包含在內。 僅包含訪客首次購買後的點擊。

## 將資料填入此維度中

Adobe 會根據您實施作業中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件自動填入此維度。 如果您在網站上實施作業 `purchase` 事件，此維度一律有效。

## 維度項目

維度項目包含訪客最近一次購買與目前點擊的間隔天數。 每個天數都是獨立的維度項目，若訪客的最近一次購買與目前點擊發生於同一天，則會出現「同一天」。
