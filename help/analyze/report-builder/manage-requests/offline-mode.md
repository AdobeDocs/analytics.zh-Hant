---
description: 離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。
title: 以離線模式建立及編輯請求
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 98%

---


# 以離線模式建立及編輯請求

離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。

當您建立或編輯新的請求時，系統會進行「報表 API」呼叫以擷取回應。這樣會拖慢請求建立程序，因為您必須先等候資料傳回，才能前往下個步驟。離線模式則只會傳回預留位置資料，因此無須進行任何 API 呼叫。

若要啟用離線模式，請執行下列動作：

1. 按一下 Report Builder 功能表中的&#x200B;**[!UICONTROL 「選項」]**。

   ![](assets/offline_mode.png)

1. 勾選「**[!UICONTROL 開啟離線模式以建立和編輯請求]**」旁的核取方塊。
1. 在「**[!UICONTROL 將度量資料顯示為]**」欄位中，輸入您想要在請求中傳回的預留位置資料。例如，您可以輸入「1」。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。
1. 接著，在「請求精靈」中以離線模式建立並執行請求。
1. 帶有預留位置資料「1」的請求如下所示：

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >以真實資料執行請求前，請務必確認您已停用「離線模式」。若要停用「離線模式」，只要返回&#x200B;**[!UICONTROL 「選項」]**&#x200B;清除勾選記號即可。

