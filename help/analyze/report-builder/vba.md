---
title: 報告建立工具中的Visual Basic巨集
description: 使用VBA展開Excel活頁簿和Report Builder的功能。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# 報告建立工具中的Visual Basic巨集

VBA巨集（也稱為Visual Basic巨集）可讓您以Microsoft Excel無法獨立處理的方式來控制活頁簿。 Visual Basic可存取活頁簿、Excel甚至Windows。

Adobe支援三種Report Builder API方法。 請確定已安裝最新版本的報告建立工具，並在執行任何巨集前先登入。

>[!IMPORTANT]
>
>出於安全原因，您無法排程包含巨集的活頁簿。

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. 首先，透過其產品ID呼叫報告建立工具COM增益集，然後呼叫 `RefreshAllRequests()` API命令：

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

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. API `RefreshWorksheetRequests()` 呼叫會將工作表物件視為引數。 您可以對任何包含報告建立工具請求的工作表使用此呼叫：

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

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. 此範例中使用的儲存格範圍指向作用中活 `B1:B54` 頁簿內「資料」工作表的範圍。 範圍運算式支援所有支援的Excel範圍運算式：

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
