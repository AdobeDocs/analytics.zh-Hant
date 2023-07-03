---
title: 向使用者傳達影響
description: 瞭解傳達組織中事件影響的有效方式。
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Event
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 3%

---

# 向使用者傳達事件影響

如果您有資料 [受事件影響](overview.md)，請務必將該事件傳達給您組織中的使用者。

* 制定可用於通訊的通用免責宣告，以保持一致性
* 在活動期間和之後持續與Analytics使用者和主要利害關係人溝通
* 為後續里程碑（例如下個月或下一年）設定行事曆提醒。 未來的此通訊有助於提醒檢視報表的使用者月對月或年對月報表的影響。

在Adobe Analytics中，以下小節顯示您可以與組織中的使用者溝通的不同方式。 您也可以使用Adobe Analytics以外的其他方法（例如電子郵件）與使用者通訊。

## 透過面板或視覺效果說明溝通

如果您的工作區專案在組織中的使用者之間共用，您可以透過面板或視覺效果說明來傳達事件的影響。 以滑鼠右鍵按一下面板或視覺效果標頭，然後選取 **[!UICONTROL 編輯說明]**.

![面板說明](assets/panel_description.png)

## 透過文字視覺效果溝通

您也可以透過專用的文字視覺效果傳達事件的影響。 另請參閱 [文字視覺效果](/help/analyze/analysis-workspace/visualizations/text.md) 在分析使用手冊中。

![文字視覺效果](assets/text_visualization.png)

## 在Workspace趨勢中新增自訂日曆事件

對於Workspace中的任何趨勢視覺效果，您可以新增一個數列，代表您受影響的日期範圍。

1. 建立包含「受影響天數」區段的計算量度，方法如下 [在分析中排除特定日期](segments.md).
1. 將所需的量度新增至計算量度畫布。

   ![量度](assets/calcmetric_event.png)

1. 新增標題和說明，通知使用者該影響。 您也可以視需要將此量度標示為行事曆附註。

   ![標題和說明](assets/calcmetric_title_description.png)

1. 在自由表格中新增「日」維度。 將「造訪」和計算量度新增為並排欄。

   ![自由表格](assets/calcmetric_freeform.png)

1. 按一下計算量度的欄設定齒輪圖示，然後啟用 **[!UICONTROL 將零解譯為無值]**.

   ![計算量度設定](assets/calcmetric_zero_no_value.png)

1. 新增線條視覺效果。 受影響的天數會以不同顏色表示。 使用者也可以按一下計算量度中的「資訊」圖示以取得詳細資訊。

   ![訊息圖示](assets/calcmetric_infoicon.png)

## 在Reports &amp; Analytics中使用日曆事件

如果您使用Reports &amp; Analytics，可以使用 [日曆事件](/help/components/t-calendar-event.md) 以在任何趨勢報表中反白標示受影響的天數。 此方法不適用於Analysis Workspace。

1. 導覽至 **[!UICONTROL 元件]** > **[!UICONTROL 所有元件]** > **[!UICONTROL 行事曆事件]**.
2. 輸入所需的標題、日期範圍和附註文字。
3. 按一下「**[!UICONTROL 儲存]**」。

![日曆事件](assets/exclude_calendar_event.png)
