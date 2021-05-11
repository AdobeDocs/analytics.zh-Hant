---
description: 未分類索引鍵在分類報表中會分組為標示為「無」的單一行項目。 將「無」重新命名為其他較清楚描述的名稱會很實用。
subtopic: Classifications
title: 未分類索引鍵
feature: 管理工具
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: f52baf97efe20b209f51108995a0620b6c19bec0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 62%

---

# 未分類索引鍵

未分類索引鍵在分類報表中會分組為標示為「無」的單一行項目。 將「無」重新命名為其他較清楚描述的名稱會很實用。

## 未分類索引鍵 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分類索引鍵會在分類報表中分組為標示為&#x200B;*`None`*&#x200B;的單一行項目。 將 *`None`* 重新命名為較具描述性的名稱會很實用。

例如，假設您的追蹤代碼包含描述追蹤代碼所關聯的行動促銷活動類型的資訊。 您使用分類 (行動促銷活動類型) 將這些追蹤程式碼群組為類別，例如行動網頁、iOS 應用程式、Android 應用程式等。有些促銷活動可能不是行動促銷活動，因此不會分類為行動促銷活動類型。所有未分類追蹤程式碼會群組在&#x200B;*`None`*(在「[!UICONTROL 行動促銷活動類型]」報告中)。

## 重新命名無分類索引鍵 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

說明如何重新命名在報表中顯示為 *`none`* 之未分類索引鍵的步驟。

1. 使用匯入工具，將分類匯出至本機檔案。
1. 將一列新增到檔案中，並在「索引鍵」欄中輸入 `~none~`
1. 在您新增的列中，在適當的分類欄裡輸入較清楚描述的名稱。

   若要遵循本檔案中的範例，您可以在名為[!UICONTROL 行動促銷活動類型]的欄中輸入「非行動促銷活動」。

   此項目會將[!UICONTROL 行動促銷活動類型]報表中的&#x200B;*`None`*&#x200B;重新命名為&#x200B;*`non-mobile campaign`*。

   ![未分類索引鍵的範例](/help/components/classifications/importer/assets/non-classified-key.png)

1. [將資料匯回](/help/components/classifications/importer/import-file.md)系統。
