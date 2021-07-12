---
title: Report Builder 中的 Visual Basic 巨集
description: 使用 VBA 擴展 Excel 活頁簿和 Report Builder 的功能。
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 100%

---

# Report Builder 中的 Visual Basic 巨集

VBA 巨集 (也稱為 Visual Basic 巨集) 可讓您以單獨使用 Microsoft Excel 無法辦到的方式操控活頁簿。Visual Basic 可存取活頁簿、Excel 甚至是 Windows。

Adobe 支援三種 Report Builder API 方法。請確定已安裝最新版本 Report Builder，並先登入再執行任何巨集。

>[!IMPORTANT]
>
>基於安全理由，您無法排程包含巨集的活頁簿。

## `RefreshAllReportBuilderRequests()`

`RefreshAllReportBuilderRequests()` 巨集會重新整理作用中活頁簿裡所有的 Report Builder 請求。首先透過其產品 ID 呼叫 Report Builder COM 增益集，然後呼叫 `RefreshAllRequests()` API 命令：

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

`RefreshAllReportBuilderRequestsInActiveWorksheet()` 巨集會重新整理作用中工作表裡所有的 Report Builder 請求。`RefreshWorksheetRequests()` API 呼叫會將工作表物件視為引數。您可以對任何包含 Report Builder 請求的任何工作表使用此呼叫：

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

`RefreshAllReportBuilderRequestsInCellsRange()` 巨集會重新整理儲存格輸出與指定儲存格範圍相交的所有 Report Builder 請求。此範例中使用的儲存格範圍，指向作用中活頁簿內「資料」工作表的 `B1:B54` 範圍。範圍運算式支援所有支援的 Excel 範圍運算式：

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
