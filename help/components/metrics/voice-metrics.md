---
title: 語音分析量度
description: 語音分析量度
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# 語音分析量度

當您在[!UICONTROL 應用程式報告]上啟用[[!UICONTROL 語音和聊天機器人]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)時，會建立下列量度（和[維度](../dimensions/voice-dimensions.md)）。 您可以使用[內容資料變數](/help/implement/vars/page-vars/contextdata.md)將它們設定為`1`的值（如果適用的話，還會設定更多）。 在報表套裝設定中啟用時，會自動建立[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，以將語音分析量度對應至其關聯的內容資料變數。

| 量度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| 語音語調 | 當對語音助理發出命令時觸發。 | `a.voiceutterances` |
| 語音結束工作階段 | 語音應用程式關閉時觸發。 | `a.voiceendsession` |
| 語音錯誤 | 語音應用程式發生錯誤時觸發。 | `a.voiceerror` |

{style="table-layout:auto"}
