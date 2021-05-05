---
description: 說明如何在分類檔案中逸出分類資料的步驟。
subtopic: Classifications
title: 逸出分類資料
feature: 管理工具
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
translation-type: ht
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: ht
source-wordcount: '106'
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
