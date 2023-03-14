---
description: 說明如何建立量度，以顯示哪些行銷管道有助於提升訂購量。這可用於任何可能有助益的維度或成功案例。
title: 訂購協助量度
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 100%

---

# 訂購協助量度

說明如何建立量度，以顯示哪些行銷管道有助於提升訂購量。這可用於任何可能有助益的維度或成功案例。

1. 在計算量度產生器中，將量度命名為「Assisted Orders」(受協助的訂購量)。
1. 將「訂購」量度拖進「定義」畫布。接著，在設定齒輪中勾選&#x200B;**[!UICONTROL 「使用非預設歸因模型」]**&#x200B;核取方塊，調整歸因模型。

   ![](assets/attr-model.png)

1. 選取&#x200B;**[!UICONTROL 「自訂」]**&#x200B;歸因模型。將加權變更為 0 (首次接觸)、100 (中間接觸) 和 0 (最後接觸)。

   ![](assets/custom-attr-model.png)

1. 儲存量度。
1. 在 Analysis Workspace 建立自由表格，內含「行銷管道」維度、「訂購」和全新「受協助的訂購量」維度。

   ![](assets/mktg-channel-assists.png)

這是輕鬆辨別哪些行銷管道有助於提升訂購量的一種方式。另外，您也可以在自由表格中，以滑鼠右鍵按一下量度，直接在表格中調整歸因模型。
