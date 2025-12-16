---
title: 建立「分類設定」
description: 瞭解建立分類設定時如何提供欄位和說明。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 3%

---

# 建立和編輯「分類設定」

您從「分類設定」管理員[建立](#create-a-classification-set)和[編輯](#edit-a-classification-set)分類設定。

## 建立分類集

若要建立「分類設定」：

1. 從Adobe Analytics頂端功能表列選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 分類設定]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;中，選取&#x200B;**[!UICONTROL 分類設定]**&#x200B;索引標籤。
1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**。
1. 在&#x200B;**[!UICONTROL 新增分類集]**&#x200B;對話方塊中：

   ![分類設定 — 新增新的分類設定](assets/classifications-sets-new.png)

   1. 輸入&#x200B;**[!UICONTROL 名稱]**。 例如：`Classification Set Example`。
   1. 輸入&#x200B;**[!UICONTROL 描述（選擇性）]**。 例如，`Example classification set`。
   1. 在&#x200B;**[!UICONTROL 通知問題]**&#x200B;中輸入一或多個電子郵件地址（以逗號分隔）。 系統會向這些使用者傳送有關問題的電子郵件通知。
   1. 選取分類集的&#x200B;**[!UICONTROL 型別]**。 可能的型別包括：
      * **[!UICONTROL 主要]**。 主要分類設定適用於在Adobe Analytics中收集的維度。 主要分類是將精細維度值分組（分類）成更有意義之資料層級的方法。 例如，您可能會想要將內部搜尋關鍵字分組為內部搜尋類別，以瞭解搜尋資料中的主題。 或依顏色或類別分類產品SKU。
         * 輸入一或多個&#x200B;**[!UICONTROL 訂閱]**。  您可以定義多個&#x200B;**[!UICONTROL 報告套裝]**&#x200B;和&#x200B;**[!UICONTROL Dimension]**&#x200B;組合至一個分類集。

         * 選取![CrossSize400](/help/assets/icons/CrossSize400.svg)以刪除&#x200B;**[!UICONTROL 報表套裝]**&#x200B;和&#x200B;**[!UICONTROL 金鑰Dimension]**&#x200B;組合。

        如果您新增另一個分類集中已存在的&#x200B;**[!UICONTROL 報告套裝]**&#x200B;和&#x200B;**[!UICONTROL 關鍵Dimension]**組合，則會顯示紅色訊息。
您可以：
         * 選取&#x200B;**[!UICONTROL 新增至現有]**&#x200B;以開啟其他分類集，並選取[新增分類至該其他分類集的結構描述](schema.md)。
         * 將&#x200B;**[!UICONTROL 報告套裝]**&#x200B;和&#x200B;**[!UICONTROL 金鑰Dimension]**&#x200B;變更為尚未訂閱另一個分類集的組合。
      * **[!UICONTROL 查詢]**。 查閱表格通常稱為子分類或子分類，是一種主要分類的分類。 查詢是有關分類值的中繼資料，而非原始維度。 例如，*Product*&#x200B;維度的主要分類可能是&#x200B;*色彩代碼*。 然後可以將&#x200B;*色彩名稱*&#x200B;的查閱表格附加至&#x200B;*色彩代碼*，以說明每個色彩代碼。
1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存分類集。 選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消定義。
1. 若要定義分類集的結構描述，請從&#x200B;**[!UICONTROL 分類集]**&#x200B;管理員中選取您新建立的分類集，以[編輯分類集](#edit-a-classification-set)。


## 編輯分類設定

若要編輯分類設定：

1. 從Adobe Analytics頂端功能表列選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 分類設定]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;中，選取&#x200B;**[!UICONTROL 分類設定]**&#x200B;索引標籤。
1. 選取分類設定的名稱。
1. 在&#x200B;**[!UICONTROL 分類設定： _分類設定名稱_]**對話方塊中，您可以定義分類設定的[設定](settings.md)和[結構描述](schema.md)。
1. 完成後，選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存您的變更。 選取「**[!UICONTROL 取消]**」即可取消。


<!--


### Schema

In the Schema tab 





You can use the Classification set manager to create a classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a classification set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the classification set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the first classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data. You can add more column names after the classification set is created.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification.
  * **[!UICONTROL Primary]**: Apply to dimensions collected in Analytics. They are a way to group (classify) granular dimension values into more meaningful levels of data. For example, you might want to group internal search keywords into internal search categories, to better understand themes in your search data.
  * **[!UICONTROL Lookup]**: Commonly referred to as child or subclassifications, a lookup table is a classification of a primary classification. It is metadata about a classification value, rather than the original dimension. For example, the Product variable might have a primary classification of 'Color code'. A lookup table of 'Color name' could then be attached to 'Color code' to further explain what each code means.
* **[!UICONTROL Subscriptions]** The report suites and dimensions that this classification set applies to. You can add multiple report suite and dimension combinations to a classification set.

![Create a Classification set](../../assets/classification-set-create.png)

If a classification set exists for a given report suite + variable, the classification is added to the schema instead. A given report suite + variable combination cannot belong to multiple classification sets.

-->