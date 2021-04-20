---
description: 您可以建立自訂運算式來指定複雜的日期範圍。
title: 自訂日期運算式 - 概觀
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 30%

---


# 自訂日期運算式 - 概觀

您可以建立自訂運算式來指定複雜的日期範圍。

我們建議您在建立運算式時參考日曆，以正確指定周數和天數。 Excel 有數種內建的功能可讓您計算日期間的天數、工作日數、月數及年份數。您可以在公式中使用這些功能來計算其他間隔，如週數和季數。

**啟用自訂運算式**

這是使用&#x200B;**[!UICONTROL 遞延日期]**&#x200B;的範例。

1. 在[!UICONTROL 請求精靈中：步驟1]，而不是使用&#x200B;**[!UICONTROL 預設日期]**，請選擇&#x200B;**[!UICONTROL 遞延日期]**。

   ![](assets/rolldates1.png)

1. 切換為每週、每月、每季或每年滾動。 請注意以下選項的變更。
1. 如需更多自訂選項，請按一下「顯示進階選項」。****

   ![](assets/rolldates2.png)

1. 例如，如果您將上述日期變更為每月滾動，從三個月前的第一天起至本月的第一天，預先選項部分中的日期會自行更新，以反映：

   ![](assets/rolldatesfor3.png)

1. 啟用&#x200B;**[!UICONTROL 自訂運算式]**。 在&#x200B;**[!UICONTROL 滾動日期]**&#x200B;下選擇選項，您就可以輕鬆看到自訂日期運算式的語法。

   ![](assets/rolldatesfor5.png)

   您可以使用「進階選項」來混合和比對自訂日期運算式。 例如，如果您想查看從年初到上個完整月末的資料，可以輸入下列：`From: cy` `To: cm-1d`。 在精靈中，這些日期會顯示為1/1/2020-1/31/2020。
