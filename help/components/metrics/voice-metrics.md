---
title: 語音分析量度
description: 語音分析量度
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
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
source-wordcount: 102
ht-degree: 21%

---

# 語音分析量度

當您在[[!UICONTROL 應用程式報告]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)上啟用[!UICONTROL 語音和聊天機器人]時，會建立下列量度（和[維度](../dimensions/voice-dimensions.md)）。 您可以使用[內容資料變數](/help/implement/vars/page-vars/contextdata.md)將它們設定為`1`的值（如果適用的話，還會設定更多）。 在報表套裝設定中啟用時，會自動建立[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，以將語音分析量度對應至其關聯的內容資料變數。

| 量度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| 語音語調 | 當對語音助理發出命令時觸發。 | `a.voiceutterances` |
| 語音結束工作階段 | 語音應用程式關閉時觸發。 | `a.voiceendsession` |
| 語音錯誤 | 語音應用程式發生錯誤時觸發。 | `a.voiceerror` |

{style="table-layout:auto"}
