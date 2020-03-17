---
description: 未分類索引鍵在分類報告中會群組為單一行項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。
subtopic: Classifications
title: 未分類索引鍵
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 未分類索引鍵

未分類索引鍵在分類報告中會群組為單一行項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。

## 未分類索引鍵 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分類索引鍵在分類報告中會群組為單一行項目，標籤為 *`None`*。將 *`None`* 重新命名為較具描述性的名稱會很實用。

例如，假設您的追蹤程式碼包含一些資訊，描述追蹤程式碼關聯的行動促銷活動的類型。您使用分類 (行動促銷活動類型) 將這些追蹤程式碼群組為類別，例如行動網頁、iOS 應用程式、Android 應用程式等。有些促銷活動可能不是行動促銷活動，因此不會分類為行動促銷活動類型。所有未分類追蹤程式碼會群組在&#x200B;*`None`*(在「[!UICONTROL 行動促銷活動類型]」報告中)。

## 重新命名無分類索引鍵 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

說明如何重新命名在報表中顯示為 *`none`* 之未分類索引鍵的步驟。

1. 使用匯入工具，將分類匯出至本機檔案。
1. 將一列新增到檔案中，並在「索引鍵」欄中輸入 [!DNL ~~]none。
1. 在您新增的列中，在適當的分類欄裡輸入較清楚描述的名稱。

   若要依照本文件中的範例，您可以在名為「[!UICONTROL 行動促銷活動名稱]」的欄裡輸入 &quot;non-mobile campaign&quot;。

   這個項目會將&#x200B;*`None`* 重新命名為 *`non-mobile campaign`* (在[!UICONTROL 行動促銷活動類型]報表中)。
1. [將資料匯回](/help/components/c-classifications2/c-classifications-importer/import-file.md)系統。
