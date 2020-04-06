---
description: 有了計算量度產生器，任何人都可以建立參與率量度。
title: 參與率量度
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 參與率量度

以下是一個簡單的使用案例：您是內容擁有者，且想查看是哪些頁面促成 (即參與) 包含訂單的造訪。方法如下：

>[!NOTE] 您以前必須透過「管理工具」執行此工作。您仍可在「管理工具」中啟用參與率量度，但僅限自訂事件1 - 100。

以下是一個簡單的使用案例：您是內容擁有者，並想查看是哪些頁面促成 (參與) 包含電子郵件註冊的造訪。方法如下：

1. 在計算量度產生器中建立新量度。
1. 將成功事件「訂單」拖曳至「定義」畫布。
1. Change the [attribution model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. 選擇 **[!UICONTROL Visit]** 回顧。 定義應該看起來類似下列：

   ![](assets/participation.png)

1. 儲存量度。
1. Use the calculated metric in a **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (選用) 與組織中的其他使用者共用量度。

