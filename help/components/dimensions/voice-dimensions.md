---
title: 語音分析維度
description: 語音分析維度
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# 語音分析維度

當您在[!UICONTROL 應用程式報告]上啟用[[!UICONTROL 語音和聊天機器人]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)時，會建立下列維度（和[量度](../metrics/voice-metrics.md)）。 您可以使用[內容資料變數](/help/implement/vars/page-vars/contextdata.md)將它們設定為所需的字串值。 在報表套裝設定中啟用時，會自動建立[處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)，以將語音分析維度對應至其關聯的內容資料變數。

| 維度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| 語音錯誤型別 | 遇到的錯誤型別。 | `a.voiceerrortype` |
| 語音語言 | 使用者與您的語音應用程式互動的語言。 | `a.voicelanguage` |
| 語音意圖 | 使用者要執行的命令。 | `a.voiceintent` |
| 語音應用程式回應 | 語音應用程式傳回給使用者的回應。 | `a.voiceappresponse` |
| 語音驗證 | 使用者與語音應用程式互動時的已驗證狀態。 | `a.voiceauthentication` |
| 興趣點ID | 興趣點ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
