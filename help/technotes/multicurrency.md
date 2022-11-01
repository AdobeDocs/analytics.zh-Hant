---
description: 說明如何定義目標貨幣代碼以便讓多貨幣支援運作。
title: 多貨幣支援
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 多貨幣支援

Adobe提供多個貨幣轉換層級，讓您的組織能在許多報表中達到所需的貨幣。 轉換會發生在三個層級：

## 頁面層級

您可以使用 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 變數來設定每個頁面上所需的貨幣。 如果頁面上的貨幣不符合目標報表套裝的貨幣，Adobe會根據當天的匯率，執行報表套裝貨幣的貨幣轉換。 已記錄轉換的貨幣。

## 報表套裝層級

每個報表套裝都有 **基本貨幣**. 此貨幣會指定所有貨幣量度的內容(例如 [收入](/help/components/metrics/revenue.md))。 儲存的所有貨幣資料都以報表套裝的基本貨幣計算。

## 使用者層級

若為Reports &amp; Analytics，使用者可在下方設定與報表套裝的基本貨幣不同的貨幣 [報表設定](/help/analyze/reports-analytics/report-settings.md). 此設定不具破壞性，表示不會變更基礎資料。 而是會將基本貨幣轉換套用至根據今天的匯率檢視的所有報表。 如果您在不同天檢視相同的報表，數字可能會因每日匯率不同而改變。

Analysis Workspace目前不提供使用者層級貨幣轉換。
