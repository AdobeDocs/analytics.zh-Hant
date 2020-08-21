---
title: 自訂事件
description: 有自訂事件存在的點擊次數。
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---


# 自訂事件

*此說明頁面說明自訂事件作為量度時的運作方式。若要瞭解自訂事件作為實作變數時的運作方式，請參閱「實作」使用指南中的[事件概觀](/help/implement/vars/page-vars/events/events-overview.md)。*

自訂事件量度會顯示有指定的自訂事件設定於影像要求中的點擊次數。這些量度可用來深入分析每個組織的特定事件，因此對許多實作而言都十分重要。

## 此量度的計算方式

自訂事件的計算方式依其類型而異。您可以在報表套裝設定中的[成功事件](../../admin/admin/c-success-events/success-event.md)下查看事件的類型。

* **計數器事件**：預設的事件設定。大部分事件都是計數器事件。計算有相符的自訂事件 `event1` - `event1000` 存在於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中的點擊次數。
* **數值事件**：加總為 `events` 變數中的事件指派的數值。
* **貨幣事件**：根據當天的匯率套用貨幣轉換，然後加總為 `events` 變數中的每個點擊指派的數值。

可用事件的數目取決於貴組織的 Analytics 合約。簽訂非舊式合約的組織大多可以使用 1000 個自訂事件。如果您不確定有多少個自訂事件可供使用，請聯絡貴組織的客戶經理。

Adobe 強烈建議您將每個事件的使用方式記錄在組織的[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
