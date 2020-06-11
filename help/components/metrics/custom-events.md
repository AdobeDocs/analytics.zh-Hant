---
title: 自訂事件
description: 自訂事件存在的點擊數。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 19%

---


# 自訂事件

*此說明頁面說明自訂事件如何以量度的形式運作。 如需自訂事件如何當做實作變數的詳細資訊，請參閱「實[作使用指南](/help/implement/vars/page-vars/events/events-overview.md)」中的「事件概述」。*

自訂事件度量顯示在影像請求中設定指定自訂事件的點擊數。 這些量度對許多實作而言至關重要，因為它們可提供每個組織特定事件的分析。

## 此度量的計算方式

自訂事件的計算方式依其類型而異。 您可以在「報表套裝設定」的「成功 [事件](../../admin/admin/c-success-events/success-event.md) 」下檢查事件類型。

* **計數器事件**: 預設事件設定。 大部分事件都是計數器事件。 計算相符自訂事件——存在於變數中 `event1` 的 `event1000` 點擊 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 數。
* **數值事件**: 總和指派給變數中事件的數值 `events` 值。
* **貨幣事件**: 套用該日的兌換率貨幣兌換，然後加總指派給變數中每個點擊的數值 `events` 值。

可用事件的數目取決於貴組織的 Analytics 合約。簽訂非舊式合約的組織大多可以使用 1000 個自訂事件。如果您不確定有多少個自訂事件可供使用，請聯絡貴組織的客戶經理。

Adobe強烈建議您記錄在組織解決方案設計檔案中使用每個事件 [的方式](/help/implement/prepare/solution-design.md)。
