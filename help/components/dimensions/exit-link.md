---
title: 退出連結
description: 退出連結的名稱。
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 2%

---


# 退出連結

「退出連結」維度會報告網站上實作的退出連結名稱。 當您想要瞭解哪些連結最常用於指向網站外網域時，這個維度很有用。

## 將資料填入此維度

此維度會從影像請求中 [`pev2` 的查詢字串](/help/implement/validate/query-parameters.md) ，收集具有查詢字串值 `pe` 之點擊的資料 `lnk_e`。 如果查 `pe` 詢字串在點擊中有不同的值，此維度不會收集資料。

如果您想使用AppMeasurement傳送資料至此維度：

* 以所需 [`linkName`](/help/implement/vars/config-vars/linkname.md) 的值填入變數。
* 將 [`linkType`](/help/implement/vars/config-vars/linktype.md) 變數設為 `"e"`.
* 傳送影 [`tl()`](/help/implement/vars/functions/tl-method.md) 像要求。

## 維度值

由於此變數是以實作中的自訂字串為基礎，因此您的組織會決定維度值。 Adobe建議您根據您的報告需求，將連結分組至有意義的類別。
