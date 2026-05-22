---
description: 瞭解如何使用離線模式傳回預留位置資料。
title: 如何啟用離線模式
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 12%

---

# 建立及編輯請求的離線模式

{{legacy-arb}}

離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。

當您建立或編輯新請求時，會執行Report API呼叫以擷取回應。 有時這些呼叫會減慢要求建立程式的速度，因為您必須等待資料傳回，才能進行下一個步驟。 離線模式只會傳回預留位置資料，不會產生API。

啟用離線模式

1. 按一下Report Builder功能表中的&#x200B;**[!UICONTROL 選項]**。

   ![選取離執行緒式碼的[選項]熒幕擷圖。](assets/offline_mode.png)

1. 勾選&#x200B;**[!UICONTROL 開啟離線模式以建立及編輯請求]**&#x200B;旁的核取方塊。
1. 在&#x200B;**[!UICONTROL 將量度資料顯示為]**&#x200B;欄位中，輸入您要在要求中傳回的預留位置資料。 例如，輸入&quot;1&quot;。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。
1. 使用「請求精靈」以離線模式建立及執行您的請求。 下列熒幕擷圖顯示以「1」作為預留位置資料的請求範例。

   ![熒幕擷圖顯示離線模式範例使用1做為預留位置。](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >以真實資料執行請求前，請務必確認您已停用「離線模式」。
