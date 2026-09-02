---
title: 語音分析維度
description: 語音分析維度
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 16%

---

# 語音分析維度

當您在[[!UICONTROL 應用程式報告]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)上啟用[!UICONTROL 語音和聊天機器人]時，會建立下列維度（和[量度](../metrics/voice-metrics.md)）。 您可以使用[內容資料變數](/help/implement/vars/page-vars/contextdata.md)將它們設定為所需的字串值。 在報表套裝設定中啟用時，會自動建立[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，以將語音分析維度對應至其關聯的內容資料變數。

| 維度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| 語音錯誤類型 | 遇到的錯誤型別。 | `a.voiceerrortype` |
| 語音語言 | 使用者與您的語音應用程式互動的語言。 | `a.voicelanguage` |
| 語音意圖 | 使用者要執行的命令。 | `a.voiceintent` |
| 語音應用程式回應 | 語音應用程式傳回給使用者的回應。 | `a.voiceappresponse` |
| 語音驗證 | 使用者與語音應用程式互動時的已驗證狀態。 | `a.voiceauthentication` |
| 興趣點 ID | 興趣點ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
