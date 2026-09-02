---
description: 說明如何定義目標貨幣代碼以便讓多貨幣支援運作。
title: 多貨幣支援
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# 多貨幣支援

Adobe提供多個貨幣轉換層級，讓您的組織可以在許多報表中達到所需的貨幣。 轉換會發生在三個層級：

## 頁面層級

您可以使用[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)變數在每個頁面上設定所要的貨幣。 如果頁面上的貨幣與目的地報表套裝的貨幣不符，Adobe會根據當天的匯率，執行報表套裝的貨幣轉換。 會記錄轉換後的貨幣。

## 報表套裝層級

每個報表套裝都有&#x200B;**基本貨幣**。 此貨幣會指定所有貨幣量度的內容（例如[收入](/help/components/metrics/revenue.md)）。 所有儲存的貨幣資料都會以報表套裝的基本貨幣表示。

