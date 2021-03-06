---
title: 在分析中排除特定日期
description: 如果不想將日期或日期範圍包括在報表中，則提供的提示。
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
source-git-commit: d03206b127e16cbb98d1318b0acc6c304f91ca48
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 2%

---

# 在分析中排除特定日期

如果您有資料 [受事件影響](overview.md)，您可以使用段來排除您不希望在報表中包括的任何日期範圍。 劃分事件影響的日期有助於防止您的組織對部分資料做出決策。

## 隔離受影響的天數 {#isolate}

建立隔離受影響日期或日期範圍的段。 如果您只想關注問題日，以瞭解有關其影響的更多資訊，則此段非常有用。

1. 通過轉到 **[!UICONTROL 元件]** > **[!UICONTROL 段]**，然後按一下 **[!UICONTROL 添加]**。
2. 將「Day」維拖到定義畫布上，並將其設定為與要隔離的日期相等。
3. 對要在報告中隔離的每天重複上述步驟。

![受影響天數段](assets/affected_days.jpg)

>[!TIP]
>
>要將OR語句更改為AND語句，請按一下OR旁邊的向下箭頭，然後選擇AND。

Adobe建議使用橙色尺寸尺寸元件，而不是紫色日期範圍元件。 如果使用紫色日期範圍元件，則它們將覆蓋項目的日曆範圍：

![排除段日類型](assets/exclude_segment_day_type.jpg)

## 排除受影響天數 {#exclude}

建立不包括受影響日期或日期範圍的段。 如果您希望排除遇到問題的天數，以盡量減少對整體報告的影響，則此分部非常有用。

1. 通過轉到 **[!UICONTROL 元件]** > **[!UICONTROL 段]**，然後按一下 **[!UICONTROL 添加]**。
2. 在段定義畫布的右上角，按一下 **[!UICONTROL 選項]** > **[!UICONTROL 排除]**。
3. 將「Day」維拖到定義畫布上，並將其設定為等於要刪除的日。
4. 對要在報告中刪除的每天重複上述步驟。

![排除受影響天數](assets/exclude_affected_days.jpg)

## 在報告中使用這些段

一旦建立了排除段，就可以像使用其它段一樣使用它。

### 比較趨勢報告中的段 {#compare}

您可以在報表中同時應用「受影響的天數」段和「排除受影響的天數」段，以將它們並排進行比較。 將兩個段拖動到度量上方或下方以比較它們：

![兩段](assets/affected_and_exclude.png)

如果不想在表或可視化中顯示零（導致下沈），請啟用 **[!UICONTROL 將零解釋為無值]** 的子菜單。

![解釋零](assets/interpret_zero.png)

如果不想在表或可視化中顯示零（導致下沈），請啟用 **[!UICONTROL 將零解釋為無值]** 的子菜單。

![解釋零](assets/interpret_zero.png)

### 將排除段應用於項目 {#apply}

可以將「排除受影響的天數」段應用於Workspace項目。 將排除段拖動到標有「工作區」畫布節 *將段放在此處*。

>[!TIP]
>
>在面板說明中包括有關排除資料的注釋，以幫助查看報告的用戶。 按一下右鍵面板的標題，然後按一下 **[!UICONTROL 編輯說明]**。

![應用於面板的段](assets/exclude_segment_panel.jpg)

### 在虛擬報表套件中使用排除段 {#use-vrs}

可在 [虛擬報告套件](/help/components/vrs/vrs-about.md) 以便更方便地排除資料。 此選項非常理想，因為您不必記得為包括受影響日期範圍的每個報表應用段。 如果已將虛擬報表套件用作主要資料源，則可以將段添加到現有VRS。

1. 導航到 **[!UICONTROL 元件]** > **[!UICONTROL 虛擬報告套件]**。
2. 按一下&#x200B;**[!UICONTROL 「新增」]**。
3. 輸入虛擬報告套件的所需名稱和說明。
4. 將排除段拖到標有 **[!UICONTROL 添加段]**。
5. 按一下 **[!UICONTROL 繼續]** 在右上角，然後按一下 **[!UICONTROL 保存]**。

![應用於VRS的段](assets/exclude_segment_vrs.png)
