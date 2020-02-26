---
description: 您可以建立自訂運算式來指定複雜的日期範圍。
title: 自訂日期運算式 - 概觀
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: fa1b0b7fb24d0cd2c205fbbb6a1e526f243531f8

---


# 自訂日期運算式 - 概觀

您可以建立自訂運算式來指定複雜的日期範圍。

我們建議您在建立運算式時參考日曆，以正確指定周數和天數。 Excel 有數種內建的功能可讓您計算日期間的天數、工作日數、月數及年份數。您可以在公式中使用這些功能來計算其他間隔，如週數和季數。

**啟用自訂運算式**

這是使用的範例 **[!UICONTROL Rolling Dates]**。

1. 在上， [!UICONTROL Request Wizard: Step 1]而不是使用 **[!UICONTROL Preset Dates]**，選擇 **[!UICONTROL Rolling Dates]**。

   ![](assets/rolldates1.png)

1. 切換為每週、每月、每季或每年滾動。 請注意以下選項的變更。
1. 如需更多自訂選項，請按一下 **[!UICONTROL Show Advanced Options]**。

   ![](assets/rolldates2.png)

1. 例如，如果您將上述日期變更為每月滾動，從三個月前的第一天起至本月的第一天，預先選項部分中的日期會自行更新，以反映：

   ![](assets/rolldatesfor3.png)

1. 啟用 **[!UICONTROL Customize Expression]**. 透過選取下方的選 **[!UICONTROL Rolling Dates]**&#x200B;項，您可以輕鬆查看自訂日期運算式的語法。

   ![](assets/rolldatesfor5.png)

   您可以使用「進階選項」來混合和比對自訂日期運算式。 例如，如果您想查看從年初到上個完整月末的資料，可以輸入下列： `From: cy``To: cm-1d`. 在精靈中，這些日期會顯示為1/1/2020-1/31/2020。
