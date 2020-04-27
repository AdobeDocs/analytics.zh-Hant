---
description: 離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。
title: 以離線模式建立及編輯請求
topic: Report builder
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 以離線模式建立及編輯請求

離線模式會傳回預留位置資料，以加速建立及編輯請求的處理程序。

當您建立或編輯新的請求時，系統會進行「報表 API」呼叫以擷取回應。這樣會拖慢請求建立程序，因為您必須先等候資料傳回，才能前往下個步驟。離線模式則只會傳回預留位置資料，因此無須進行任何 API 呼叫。

若要啟用離線模式，請執行下列動作：

1. Click **[!UICONTROL Options]** in the Report Builder menu.

   ![](assets/offline_mode.png)

1. 勾選旁邊的核取方塊 **[!UICONTROL Turn on offline mode for creating and editing requests]**。
1. In the **[!UICONTROL Display Metric Data as]** field, enter the placeholder data that you want returned in your request. 例如，您可以輸入「1」。
1. 按一下 **[!UICONTROL OK]**.
1. 接著，在「請求精靈」中以離線模式建立並執行請求。
1. 帶有預留位置資料「1」的請求如下所示：

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >以真實資料執行請求前，請務必確認您已停用「離線模式」。To do so, just go back to **[!UICONTROL Options]** and remove the checkmark.

