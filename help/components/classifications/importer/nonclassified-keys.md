---
description: 未分類索引鍵在分類報告中會群組為單一條列項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。
title: 未分類索引鍵
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# 未分類索引鍵

未分類索引鍵在分類報告中會群組為單一條列項目，標籤為「無」。 將「無」重新命名為其他較清楚描述的名稱會很實用。

## 未分類索引鍵 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分類索引鍵在分類報告中會群組為單一條列項目，標籤為 *`None`*。 將 *`None`* 重新命名為較具描述性的名稱會很實用。

例如，假設您的追蹤代碼包含一些資訊，描述追蹤代碼關聯的行動促銷活動的類型。 您使用分類 (行動促銷活動類型) 將這些追蹤程式碼群組為類別，例如行動網頁、iOS 應用程式、Android 應用程式等。有些促銷活動可能不是行動促銷活動，因此不會分類為行動促銷活動類型。在[!UICONTROL 行動促銷活動型別]報告中，所有未分類的追蹤代碼都會分組到&#x200B;*`None`*&#x200B;下。

## 重新命名無分類索引鍵 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

若要重新命名在報告中顯示為 *`none`* 之未分類索引鍵：

1. 使用匯入工具，將分類匯出至本機檔案。
1. 將一列新增到檔案中，並在「索引鍵」欄中輸入 `~none~`
1. 在您新增的列中，在適當的分類欄裡輸入較清楚描述的名稱。

   若要依照本文件中的範例，您可以在名為「[!UICONTROL 行動裝置行銷活動類型]」的欄裡輸入「non-mobile campaign」。

   此項目會將「[!UICONTROL 行動裝置行銷活動]」報告中的 *`None`* 重新命名為 *`non-mobile campaign`*。

   ![未分類索引鍵範例](/help/components/classifications/importer/assets/non-classified-key.png)

1. [將資料匯回](/help/components/classifications/importer/import-file.md)系統。
