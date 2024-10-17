---
description: 瞭解如何使用離線模式傳回預留位置資料。
title: 如何啟用離線模式
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 33%

---

# 以離線模式建立及編輯請求

{{legacy-arb}}

離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。

當您建立或編輯新請求時，會執行Report API呼叫以擷取回應。 有時這些呼叫會減慢要求建立程式的速度，因為您必須等待資料傳回，才能進行下一個步驟。 離線模式只會傳回預留位置資料，不會產生API。

啟用離線模式

1. 按一下 Report Builder 功能表中的&#x200B;**[!UICONTROL 「選項」]**。

   ![選取離執行緒式碼的[選項]熒幕擷圖。](assets/offline_mode.png)

1. 勾選「**[!UICONTROL 開啟離線模式以建立和編輯請求]**」旁的核取方塊。
1. 在「**[!UICONTROL 將度量資料顯示為]**」欄位中，輸入您想要在請求中傳回的預留位置資料。例如，您可以輸入「1」。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。
1. 使用「請求精靈」以離線模式建立及執行您的請求。 下列熒幕擷圖顯示以「1」作為預留位置資料的請求範例。

   ![熒幕擷圖顯示離線模式範例使用1做為預留位置。](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >以真實資料執行請求前，請務必確認您已停用「離線模式」。
