---
description: 建立直接呼叫規則的條件.
keywords: 動態標籤管理；規則；建立規則；新規則；直接調用規則
seo-description: 建立直接呼叫規則的條件.
seo-title: 建立直接呼叫規則的條件
solution: Experience Cloud,Analytics,Target，動態標籤管理
title: 建立直接呼叫規則的條件
uuid: bab0e058-a5b8-4039-8333-5e8f3d06ade4
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 建立直接呼叫規則的條件

建立直接呼叫規則的條件.

1. In the **[!UICONTROL Conditions]** dialog, specify the string that will be passed to `_satellite.track()` in your direct call, without quotes.

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >If you specify the string that will be passed to `_satellite.track()` in your direct call using the UI, as described above, do not use quotation marks. If you insert [customized page code](../../../implement/c-implement-with-dtm/c-aa-tool/customize-page-code.md#concept_7D6390823DFE4D29AF9505CCE1A79C3B) using the editor, you must use quotation marks.

