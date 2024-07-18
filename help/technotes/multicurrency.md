---
description: 說明如何定義目標貨幣代碼以便讓多貨幣支援運作。
title: 多貨幣支援
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# 多貨幣支援

Adobe提供多個貨幣轉換層級，讓您的組織可以在許多報表中達到所需的貨幣。 轉換會發生在三個層級：

## 頁面層級

您可以使用[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)變數在每個頁面上設定所要的貨幣。 如果頁面上的貨幣與目的地報表套裝的貨幣不符，Adobe會根據當天的匯率將貨幣轉換為報表套裝的貨幣。 會記錄轉換後的貨幣。

## 報表套裝層級

每個報表套裝都有&#x200B;**基本貨幣**。 此貨幣會指定所有貨幣量度的內容（例如[收入](/help/components/metrics/revenue.md)）。 所有儲存的貨幣資料都會以報表套裝的基本貨幣表示。

