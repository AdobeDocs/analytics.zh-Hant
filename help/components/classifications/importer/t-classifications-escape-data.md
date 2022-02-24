---
description: 說明如何在分類檔案中逸出分類資料的步驟。
title: 逸出分類資料
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '104'
ht-degree: 100%

---

# 逸出分類資料

說明如何在分類檔案中逸出分類資料的步驟。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 確定分類檔案格式是 v2.1。

   如果已啟用 v2.1，您會看到如下所示的一行：

   >[!NOTE]
   >
   >若要指定 v2.1 格式，請在&#x200B;**[!UICONTROL 分類匯入工具]**&#x200B;頁面上匯出檔案時 ([!UICONTROL 瀏覽器匯出]或 [!UICONTROL FTP 匯出])，啟用[!UICONTROL 佇列的輸出]。

1. 以雙引號 (`"`) 括住包含特殊字元的欄位。

雙引號字元在逸出的儲存格中會顯示為兩個雙引號字元 (`" "`)。例如：

```
My String "of data"
```

逸出後變成：

```
"My String ""of data"""
```
