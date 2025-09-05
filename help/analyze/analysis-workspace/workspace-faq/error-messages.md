---
description: 了解 Analysis Workspace 的錯誤和疑難排解。
title: 錯誤和疑難排解
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 100%

---

# 錯誤和疑難排解 

使用 Analysis Workspace 時，您可能會遇到影響功能或效能的錯誤。下方列出最常見的錯誤類型、發生原因，以及可採取的最佳化措施。

## 錯誤訊息

使用 Analysis Workspace 時您可能會看到的一些常見錯誤訊息：

| 錯誤訊息 | 為什麼會出現錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 資料視圖出現了異常繁重的報告。請稍後再試。] | 您的組織針對特定資料視圖同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案、已排程報告、已排程警報，以及同時提出報告請求的用戶數量。 | 在一天中更平均地分佈資料視圖的請求和排程。<p>管理員可以使用[報告活動管理程式來識別和取消](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md)正在消耗報告產能的請求。</p> |
| [!UICONTROL 這份報告過於複雜。請檢閱建置 Analysis Workspace 報告的最佳實務。] | 您的報告請求規模過大，無法執行。造成此錯誤的原因是由於請求的複雜性而導致的逾時。 | 簡化您的要求。例如，縮短日期範圍，或簡化區段，或移除表格中的某些欄或列。您可能考慮將表格拆分為個別的請求。 |
| [!UICONTROL 資料檢視目前超出了其報告容量。請簡化要求或稍後重試。] | 您的組織針對特定資料視圖同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案，以及同時提出報告請求的用戶數量。 | 在一天中更平均地分佈資料視圖的請求和排程。 |
| [!UICONTROL 發生系統錯誤。請在「**[!UICONTROL 說明 > 提交支援票證]**」中提出客戶服務請求，並附上錯誤代碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 錯誤 500：無法載入頁面] | 您的本機網路問題 (例如公司[防火牆設定](/help/technotes/ip-addresses.md)) 是造成此錯誤的因素。此外，Adobe 可能遇到需要解決的問題。 | 請在幾分鐘後再次嘗試登入。如果問題持續發生，請將 EIM 例項 ID 代碼提交給客戶服務。 |
| [!UICONTROL 您的請求失敗，因為有太多欄或預先設定的列。] | 表格有太多自由格式儲存格 (列數 * 欄數)。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |


## 疑難排解

使用 Analysis Workspace 時，您可以使用以下資訊針對常見問題進行疑難排解。

| 問題 | 如何進行疑難排解 |
|---|---|
| 我將量度拖曳到專案後，系統顯示&#x200B;*資料無效*。 | 資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。 |
| 我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。 | 如果您成功建立 Workspace 報告，但當中沒有任何資料，建議您檢查以下幾個事項：<ul><li>如果您在報表中套用了區段，則可能是區段標準與任何資料皆不符。請嘗試移除區段或調整區段定義。</li><li>檢查右上角的日期範圍，確認已設為您預期的值。</li><li>導覽至您的網站，使用[除錯工具](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-tw)驗證有確實收集資料。</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](/help/technotes/ip-addresses.md), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->