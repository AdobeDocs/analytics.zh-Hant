---
title: 建立注釋
description: 如何在工作區中建立注釋。
role: User, Admin
source-git-commit: f8a928782b4c4916f5ff2042cb72941d76f57d7d
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---


# 建立注釋

>[!NOTE]
>
>此功能當前正在有限的測試中。

1. 要建立注釋，您有4種入門方法：

   * 轉到 [!UICONTROL 分析] > [!UICONTROL 元件] > [!UICONTROL 注釋]。 將開啟「注釋管理器」(Annotations Manager)頁面。 按一下 [!UICONTROL 建立新注釋] 開啟注釋生成器，或

   * 按一下右鍵表或線形圖上的點。 「注釋生成器」(Annotation builder)開啟，或

   * 在工作區中，轉到 [!UICONTROL 元件] > [!UICONTROL 建立注釋]。

   * 使用此熱鍵開啟注釋生成器：
      * (PC) `ctrl` `shift` +o
      * (Mac) `shift` + `command` +o

1. 填充生成器元素。

   ![](assets/ann-builder.png)

   | 元素 | 說明 |
   | --- | --- |
   | [!UICONTROL 標題] | 命名注釋，例如&quot;紀念日&quot; |
   | [!UICONTROL 說明] | （可選）提供注釋的說明，例如「美國觀察到公共假日」。 |
   | [!UICONTROL 標籤] | （可選）通過建立或應用標籤來組織注釋。 |
   | [!UICONTROL 套用的日期] | 選擇注釋可見所需的日期或日期範圍。 |
   | [!UICONTROL 色彩] | 將顏色應用於注釋。 注釋以選定顏色出現在項目中。 顏色可用於對注釋進行分類，如公共假日、外部事件、跟蹤問題等。 |
   | [!UICONTROL 範圍] | （可選）拖放觸發注釋的度量。 然後拖放用作過濾器（即注釋將隨之可見）的任何尺寸或段。 如果未指定範圍，則注釋將應用於所有資料。<ul><li>**[!UICONTROL 這些指標中的任何一個都存在]**:拖放至多10個度量，這些度量將觸發要顯示的注釋。</li><li>**[!UICONTROL 用所有這些濾鏡]**:拖放最多10個尺寸或段，當注釋顯示時，這些尺寸或段將進行篩選。</li></ul><p>使用案例：eVar已停止收集特定日期範圍的資料。 將eVar拖入 **[!UICONTROL 這些指標中的任何一個都存在]** 對話框。 或 [!UICONTROL 訪問] 度量不報告任何資料 — 請遵循相同的流程。 |
   | [!UICONTROL 適用於所有報表套裝] | 預設情況下，注釋應用於原始報告套件。 通過選中此框，您可以使注釋應用於公司中的所有報表套件。 |
   | [!UICONTROL 適用於所有專案] | 預設情況下，注釋應用於當前項目。 通過選中此框，可以使注釋應用於您擁有的所有項目。 |

1. 按一下「[!UICONTROL 儲存]」。