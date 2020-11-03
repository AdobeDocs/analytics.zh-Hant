---
description: Adobe Analysis工作區及其相關元件中的錯誤訊息清單
title: Analysis Workspace 的常見錯誤訊息
translation-type: tm+mt
source-git-commit: 4fd3cf105dff0723ee6454ab6e3a58119928ddc0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 35%

---


# 常見錯誤訊息

在與分析工作區互動時，您可能會遇到也會影響效能的錯誤。 以下列出最常見的錯誤類型、產生原因，以及可進行的最佳化。

| 錯誤訊息 | 為何發生這項錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 報表套裝正處理異常大量報告。請稍後再試。] | 您的組織針對特定報表套裝同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案、已排程報表、已排程警報，以及同時提出報表請求的使用者數量。 | 將報表套裝的請求和排程分佈在一天中更平均。 |
| [!UICONTROL 發生系統錯誤。 請在「說明>提交支援票證」下記錄客戶服務要求，並包含您的錯誤碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 要求太複雜。] | 您的報表請求規模過大，無法執行。造成此錯誤的因素包括請求的規模所導致的逾時、區段或搜尋篩選器中有過多相符項目、加入的量度過多、維度和量度組合不相容等。 | 移除表格中的某些欄或列，或考慮將表格分割為個別請求，以簡化您的請求。 |
| [!UICONTROL 此視覺化中的其中一個區段或搜尋包含傳回太多結果的文字搜尋。] | 您的區段標準或報表篩選太廣泛。 | 縮小搜尋文字標準並再次嘗試請求。 |
| [!UICONTROL 此維度目前不支援非預設的歸因模式。] | 您使用的維度不支援非預設歸因。 | Replace the dimension in your table with one that is compatible with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL 由於欄數過多或預先設定的列，您的請求失敗。] | 表格的自由格式儲存格太多（列*欄）。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |
