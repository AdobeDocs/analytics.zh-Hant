---
description: 說明如何刪除或移除分類資料的步驟。
seo-description: 說明如何刪除或移除分類資料的步驟。
seo-title: 刪除分類資料
solution: Analytics
subtopic: 分類
title: 刪除分類資料
topic: 管理工具
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 刪除分類資料

說明如何刪除或移除分類資料的步驟。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. 選取您要移除其中之分類資料的報表套裝和資料集。
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. 這個命令會將分類當成如同從未在指定的索引鍵發生一樣處理。它會從查閱表格完全移除它和任何欄資料。

   **警告**:您只需要一個包含deletekey的 [!DNL ~欄~]。 The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. 這個命令會移除列裡面所有的中繼資料。Adobe 解讀時會當成索引鍵從未分類，並且在[無](/help/components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF)類別中顯示。

1. 儲存檔案，再使用「[!UICONTROL 匯入檔案]」標籤上傳檔案。

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **這個命令的屬性**

* [!DNL ~空白~] ：必須為小寫，不含空格。 下列項目是無效的:

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~空白~]

* 您不能刪除索引鍵欄裡的值。這是直接傳入報告的資料，而且是永久的。
* 如果是移除有子分類的分類值，也會移除子分類。分類不能沒有索引鍵值，而子分類的父級是其索引鍵值。
* 可以移除子分類資料，但保留其父級分類的完整。

