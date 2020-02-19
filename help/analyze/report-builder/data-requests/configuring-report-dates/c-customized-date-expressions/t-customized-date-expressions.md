---
description: 您可以建立自訂運算式來指定複雜的日期範圍。
title: 自訂日期運算式 - 概觀
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: 9e1fdd7785b7323e4f667eab58a1f107272493f0

---


# 自訂日期運算式 - 概觀

您可以建立自訂運算式來指定複雜的日期範圍。

在建立運算式來指定正確的週數和天數時，建議您參考日曆。Excel 有數種內建的功能可讓您計算日期間的天數、工作日數、月數及年份數。您可以在公式中使用這些功能來計算其他間隔，如週數和季數。

**啟用自訂運算式**

1. 在上， [!UICONTROL Request Wizard: Step 1]而不是使用「預設日期」，選擇 **[!UICONTROL Rolling Dates]**。 請注意以下選項的變更。

   ![](assets/rolldates1.png)

1. 切換為每週、每月、每季或每年滾動。
1. 如需更多自訂選項，請按一下 **[!UICONTROL Show Advanced Options]**。 只要選取頂端區段中的選項，您就可以輕鬆看到自訂日期運算式的語法。

   ![](assets/rolldates2.png)

1. 啟用 **[!UICONTROL Customize Expression]**. 透過選取下方的選 **[!UICONTROL Rolling Dates]**&#x200B;項，您可以輕鬆查看自訂日期運算式的語法。

   ![](assets/rolldates5.png)

   您可以使用「進階選項」來混合和比對自訂日期運算式。 例如，如果您想查看從年初到上個完整月月底的資料，他們可以寫下列：寄件者：cy To:cm-1d 您可在精靈中看到，它會確認這些日期為1/1/2020-1/31/2020。

   例如，如果您將上述日期變更為每月滾動，從三個月前的第一天起至本月的第一天，預先選項部分中的日期會自行更新，以反映：

   ![](assets/rolldates3.png)

