---
title: 首次購買間隔天數
description: 訪客首次造訪與首次購買之間的天數。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 83%

---

# 首次購買間隔天數

「首次購買間隔天數」維度[維度](overview.md)會報告訪客首次造訪您的網站與購買之間的間隔天數。 舉例來說，如果訪客在首次造訪一天後購買，則所有後續造訪或事件都屬於「1 天」維度項目。

訪客首次購買後，就會在訪客的 Cookie 期限剩餘時間內屬於相同的維度項目。

## 將資料填入此維度中

Adobe 會根據您實施作業中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件自動填入此維度。 如果您在網站上實施作業 `purchase` 事件，此維度一律有效。

## 維度項目

維度項目包括訪客首次造訪網站與首次購買之間的天數。 每個天數都是個別的維度項目，若訪客的首次造訪與首次購買發生於同一天，則會出現「同一天」。
