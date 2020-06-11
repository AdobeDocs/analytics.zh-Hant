---
title: 下載連結
description: 下載連結的名稱。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 17%

---


# 下載連結

「下載連結」維度會報告網站上實作的下載連結名稱。 當您想要進一步瞭解下載連結的訪客行為時，此維度很有用，例如：

* 判斷從您網站中下載最頻繁的檔案。
* 瞭解是否在特定時段內某些檔案下載的次數更多。
* 驗證訪客是否下載不同的檔案類型（如果提供）。

## 將資料填入此維度

此維度會從影像請求中 [`pev2` 的查詢字串](/help/implement/validate/query-parameters.md) ，收集具有查詢字串值 `pe` 之點擊的資料 `lnk_d`。 如果查 `pe` 詢字串在點擊中有不同的值，此維度不會收集資料。

如果您想使用AppMeasurement傳送資料至此維度：

* 以所需 [`linkName`](/help/implement/vars/config-vars/linkname.md) 的值填入變數。
* 將 [`linkType`](/help/implement/vars/config-vars/linktype.md) 變數設為 `"d"`.
* 傳送影 [`tl()`](/help/implement/vars/functions/tl-method.md) 像要求。

## 維度值

由於此變數是以實作中的自訂字串為基礎，因此您的組織會決定維度值。 Adobe建議您根據您的報告需求，將連結分組至有意義的類別。
