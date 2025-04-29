---
title: 下載連結
description: 下載連結的名稱。
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 74%

---

# 下載連結

「下載連結」[維度](overview.md)會報告您的網站上實作的下載連結名稱。 如果您想要進一步瞭解下載連結的訪客行為，此維度就十分實用，例如：

* 判斷從您網站中下載最頻繁的檔案。
* 瞭解是否在特定時段內某些檔案下載的次數更多。
* 驗證訪客是否下載不同的檔案類型 (如果提供)。

## 將資料填入此維度中

此維度會針對同時具有 `pe` 查詢字串且字串值為 `lnk_d` 的點擊，從影像要求中的 [`pev2` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。如果`pe`查詢字串在點選中有不同的值，則此維度不會收集資料。 此維度的長度上限為100個位元組。

如果您想使用 AppMeasurement 將資料傳送至此維度，請傳送連結類型引數為 `"d"` 的 [`tl()`](/help/implement/vars/functions/tl-method.md) 影像要求。將所需的值填入連結名稱引數中：

```js
s.tl(true,"d","Example download link");
```

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。Adobe 建議您根據報告需求，將連結分組成有意義的類別。
