---
title: 其他平台常用的量度轉譯指南
description: 瞭解如何使用Google Analytics使用者更熟悉的術語提取許多常見報表的量度資料。
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# 其他平台常用的量度轉譯指南

在Google Analytics等其他平台上，許多報表會共用相同數目的量度。 使用此頁可瞭解如何重新建立許多報表中使用的量度。

若要新增多個量度至工作區自由表格，請從工作區中量度標題旁的元件區拖曳量度：

![其他量度](/help/technotes/ga-to-aa/assets/new_metric.png)

## 贏取量度

**使用者** ，大約等於工 **作區中的獨特訪客** 。 如需詳細 [資訊，請參閱元件使用指南中的](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) 「獨特訪客」量度。

**新用戶** :

1. 將「獨 **特訪客** 」量度拖曳至工作區。
2. 將「首次 **瀏覽」區段拖曳至** 「獨特訪客」量度標題上方：

   ![首次瀏覽次數](../assets/first_time_visits.png)

**工作階段** ，大致等於「分析 **工作區** 」中的「瀏覽」。 如需詳細 [資訊，請參閱](/help/components/c-variables/c-metrics/metrics-visit.md) 「元件」使用指南中的「瀏覽」度量。

![贏取量度](../assets/acquisition_metrics.png)

## 行為度量

**反彈率** (Bounce Rate)可在分析工作區中以量度形式提供。 如需詳細 [資訊，請參閱](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) 「元件」使用指南中的「反彈率」量度。

**頁面／工作階段** (Pages/Session)是計算度量。 它可以通過以下方式獲得：

1. 如果您已建立此計算量度，請在「量度」下找到該量度，並將其拖曳至工作區。
2. 如果您尚未建立此計算量度，請按一下量度清單 **旁的** +圖示，以開啟計算量度產生器。
3. 請為其提供「每次瀏覽頁面檢視次數」標題，並視需要提供說明。
4. 將格式設定為「小數」，並將小數位數設定為2。
5. 將「頁 **面檢視** 」量度和「 **瀏覽** 」量度拖曳至定義區。
6. 排列定義，使公式為「頁 **面檢視」除以「瀏覽」**。

   ![每次瀏覽的頁面檢視次數](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. 按一下「儲存」，返回您的工作區。
8. 將新定義的計算量度拖曳至工作區。

   進一步瞭解「 [元件」使用指南](/help/components/c-variables/c-metrics/calculated-metric.md) 中的「計算量度」。

**平均「作業持續時間** 」大約等 **於「每次瀏覽逗留時間」（秒）**。 進一步瞭解「 [元件」使用指南中](/help/components/c-variables/c-metrics/metrics-time-spent.md) 「逗留時間」量度。

## 轉換度量

**目標轉換率**、目 **標完成**，以及目標 **** 值需要在這兩個平台上進行額外實作。 如果您的實作已納入產品維度和購買事件，請考慮下列步驟：

1. 將「訂 **購** 」量度、 **收入量度** 和「瀏覽 **** 」量度拖曳至工作區。
1. 建立每次瀏覽訂 **購的計算量度**。 在兩個度量標題上使用ctrl+click(Windows)或cmd+click(Mac)來反白顯示。 以滑鼠右鍵按一下其中一個標題，選取「從選 **取範圍建立量度**」，然後按 **一下「除」**。 此新度量類似於目標轉換率。
1. 如果需要小數位數，請編輯計算量度。 按一下量度標題中的「資訊」按鈕，然後是鉛筆圖示。 在「計算量度產生器」視窗中新增1或2個小數位，然後按一下「儲存」。

   ![每次瀏覽的訂購量](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

如果您的實作尚未包含產品或轉換資料，Adobe建議與實作顧問合作，以確保資料品質和完整性。
