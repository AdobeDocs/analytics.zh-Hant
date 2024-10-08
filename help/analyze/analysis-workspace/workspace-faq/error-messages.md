---
description: Adobe Analysis Workspace 及其相關元件的錯誤訊息清單
title: Analysis Workspace 的常見錯誤訊息
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e7e03531454bd56ebe6152edc08765f42ebec728
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 100%

---

# 常見錯誤訊息

使用 Analysis Workspace 時，您可能會遇到也會影響效能的錯誤。下方列出最常見的錯誤類型、發生原因，以及可採取的最佳化措施。

| 錯誤訊息 | 為何發生這項錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 報告套裝出現了異常繁重的報告。請稍後再試。] | 您的組織針對特定報表套裝同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案，以及同時提出報告請求的用戶數量。 | 在一天中更平均地分佈報表套裝的要求和排程。 <p>管理員可以使用[報告活動管理程式來識別和取消](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)正在消耗報告產能的請求。 |
| [!UICONTROL 該報告套件目前已超出其報告容量。請簡化要求或稍後重試。] | 您的組織針對特定報表套裝同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案、已排程報表、已排程警報，以及同時提出報表請求的用戶數量。 | 在一天中更平均地分佈報表套裝的要求和排程。 |
| [!UICONTROL 發生系統錯誤。請在「說明 > 提交支援服務單」中提出客戶服務請求，並附上錯誤代碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 發生非預期的錯誤；請再次嘗試重新整理您的專案。如果問題仍然存在，請提交此錯誤 ID 給 Adobe 客戶服務以取得進一步的診斷。] | Adobe 遇到需要解決的問題。 | 如果問題仍然存在，請嘗試重新整理您的專案，提交錯誤代碼給客戶服務。 |
| [!UICONTROL 錯誤 500：無法載入頁面] | 您的本機網路問題 (例如公司[防火牆設定](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-Hant)) 是造成此錯誤的因素。此外，Adobe 可能遇到需要解決的問題。 | 請在幾分鐘後再次嘗試登入。如果問題持續發生，請將 EIM 例項 ID 代碼提交給客戶服務。 |
| [!UICONTROL 此視覺效果中，有一個區段或是搜尋包含文字搜尋，並傳回太多結果。] | 您的區段條件或報表篩選條件太廣泛。 | 請縮小搜尋文字條件，然後再次嘗試傳送請求。 |
| [!UICONTROL 此維度目前不支援非預設的歸因模型。] | 您使用的維度不支援非預設歸因。 | 使用與[歸因](/help/analyze/analysis-workspace/attribution/overview.md)相容的維度來取代表格中的維度。 |
| [!UICONTROL 您的請求失敗，因為有太多欄或預先設定的列。] | 表格有太多自由形式儲存格 (列數 * 欄數)。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |
