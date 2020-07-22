---
title: 語言
description: 瀏覽器中偏好的語言設定。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 語言

「語言」維度顯示訪客喜歡在中檢視內容的頂級語言。 當您想要瞭解最常使用的訪客語言，以協助當地語系化時，這個維度很有用。

>[!NOTE]
>
>此維度不會收集您網站的語言。 如果您想要在維度中收集網站的語言，Adobe建議使用自訂變數，例如 [eVar](evar.md)。

## 將資料填入此維度

此維度會參照Adobe內部的查閱表格。 查閱值是以影像請求中 `Accept-Language` 的HTTP標題為基礎。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。

## 維度項目

維度項目包含訪客慣用語言的好記名稱。 Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. 如果影像要求在HTTP標題中不包含有效語言，則維度項目為 `"None"`。
