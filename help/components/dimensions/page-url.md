---
title: 頁面 URL
description: 頁面的URL。
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# 頁面 URL

「頁面URL」維度會列出您網站上的URL。

>[!IMPORTANT] 此維度僅適用於資料倉庫。 如果您想在其他Analytics解決方案中使用URL維度，請使用 [eVar](evar.md)。

## 將資料填入此維度

此維度會從影像請求中的 [`g` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會使用變數收集此 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 資料。

## 以URL填入eVar

Adobe建議將eVar設定為串連字串 `window.location.hostname + window.location.pathname`。 此字串的運作方式通常比 `window.location.href` 它更好，因為它省略了通訊協定、查詢字串和錨記。

如果您希望eVar與「資料倉庫」中的「頁面URL」維度完全相符，則可使用動 [態變數](/help/implement/vars/page-vars/dynamic-variables.md) ，並將eVar設 `D=g` 定為每個點擊。 請注意，此方法不適用於自訂連結點擊，因為所有呼叫的頁面URL都會被 [`tl()`](/help/implement/vars/functions/tl-method.md) 移除。

## 維度值

維度值包含您網站上頁面的URL。
