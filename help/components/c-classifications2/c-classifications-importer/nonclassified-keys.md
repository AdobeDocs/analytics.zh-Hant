---
description: 未分類索引鍵在分類報告中會群組為單一行項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。
seo-description: 未分類索引鍵在分類報告中會群組為單一行項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。
seo-title: 未分類索引鍵
solution: Analytics
subtopic: '分類   '
title: 未分類索引鍵
topic: 管理工具
uuid: b73a916-1c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 未分類索引鍵

未分類索引鍵在分類報告中會群組為單一行項目，標籤為「無」。將「無」重新命名為其他較清楚描述的名稱會很實用。

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分類索引鍵在分類報告中會群組為單一行項目，標籤為 *`None`*. It can be useful to rename *`None`* to something more descriptive.

例如，假設您的追蹤程式碼包含一些資訊，描述追蹤程式碼關聯的行動促銷活動的類型。您使用分類 (行動促銷活動類型) 將這些追蹤程式碼群組為類別，例如行動網頁、iOS 應用程式、Android 應用程式等。有些促銷活動可能不是行動促銷活動，因此不會分類為行動促銷活動類型。所有未分類追蹤程式碼會群組在&#x200B;*`None`*(在「[!UICONTROL 行動促銷活動類型]」報告中)。

## 重新命名無分類索引鍵 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. 使用匯入工具，將分類匯出至本機檔案。
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. 在您新增的列中，在適當的分類欄裡輸入較清楚描述的名稱。

   若要依照本文件中的範例，您可以在名為「[!UICONTROL 行動促銷活動名稱]」的欄裡輸入 "non-mobile campaign"。

   這個項目會將&#x200B;*`None`* 至 *`non-mobile campaign`*[!UICONTROL 「行動促銷活動類型] 」報表中。
1. [將資料匯回](../../../components/c-classifications2/c-classifications-importer/import-file.md#concept_F88785E2BDFD448CB5D1DA3491466B0D)系統。
