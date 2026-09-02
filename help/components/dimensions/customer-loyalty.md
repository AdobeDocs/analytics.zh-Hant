---
title: 客戶忠誠度
description: 根據訪客先前購買次數分類的類別。
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 88%

---

# 客戶忠誠度

「客戶忠誠度」 [維度](overview.md)會報告您網站上先前購買0次、先前購買1次、先前購買2次或先前購買3次以上的訪客數量。 此維度對於了解網站如何影響購買行為十分有用。 您也可以在區段中使用此維度，將焦點放在回訪進行購買的訪客上，藉此鼓勵新訪客採取類似的行為。

## 將資料填入此維度中

Adobe 會根據您實施作業中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件自動填入此維度。 如果您在網站上實施作業 `purchase` 事件，此維度一律有效。

## 維度項目

維度項目包括下列幾項：

* **非客戶**：在點擊當下，訪客從未購買過產品。
* **新客戶**：在點擊當下，訪客之前曾購買過一次。
* **回頭客戶**：在點擊當下，訪客之前曾購買過兩次。
* **忠誠客戶**：在點擊當下，訪客之前曾購買過三次或更多次。

訪客進行購買時 (觸發 `purchase` 事件)，該點擊和所有後續點擊會移至下一個「貯體」。 例如，如果訪客首次從您的網站購買產品，他們會從「非客戶」移至「新客戶」，而訂單歸因於「新客戶」。 無法將訂單歸因於「非客戶」維度項目。
