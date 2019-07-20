---
description: 說明如何在分類檔案中逸出分類資料的步驟。
seo-description: 說明如何在分類檔案中逸出分類資料的步驟。
seo-title: 逸出分類資料
solution: Analytics
subtopic: '分類   '
title: 逸出分類資料
topic: 管理工具
uuid: 724edcc5-4990-4f24-afb-9aef301791 a7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 逸出分類資料

說明如何在分類檔案中逸出分類資料的步驟。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 確定分類檔案格式是 v2.1。

   如果已啟用 v2.1，您會看到如下所示的一行:

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). 例如:

```
My String "of data"
```

逸出後變成:

```
"My String ""of data"""
```
