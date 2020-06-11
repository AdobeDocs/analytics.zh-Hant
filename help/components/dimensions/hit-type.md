---
title: 點擊類型
description: 判斷點擊是前景還是背景點擊。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# 點擊類型

「點擊類型」維度會決定當點擊傳送至Adobe資料收集伺服器時，行動應用程式是在前景還是背景。 此維度僅與包含行動應用程式資料的報表套裝相關。 透過AppMeasurement收集的瀏覽器資料一律會將點擊報告為「前景」。

## 將資料填入此維度

此維度適用於4.13.6版或更新版本上的所有行動SDK建置。 如果您不使用行動SDK，則「前景」維度值下的所有點擊清單。 If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## 維度值

維值包括 `"Foreground"` 和 `"Background"`。 未在行動應用程式背景傳送的任何點擊都屬於維 `"Foreground"` 度值。 行動應用程式在背景所傳送的任何點擊都屬於 `"Background"` 維度值。
