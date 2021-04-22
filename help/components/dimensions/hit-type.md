---
title: 點擊類型
description: 判斷點擊是前景或背景點擊。
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# 點擊類型

「點擊類型」維度會判斷點擊傳送至 Adobe 資料收集伺服器時，行動應用程式在前景或背景。此維度僅與包含行動應用程式資料的報表套裝相關。透過 AppMeasurement 收集的瀏覽器資料一律會將點擊回報為「前景」。

## 將資料填入此維度中

此維度可立即用於 4.13.6 版或更新版本上的所有行動 SDK 實施作業。如果您不使用行動 SDK，所有點擊會列於「前景」維度項目中。如果勾選「停用背景點擊數的舊式報告和歸因」，則背景點擊數僅會顯示在[「虛擬報表套裝」](../vrs/vrs-mobile-visit-processing.md)中。

## 維度項目

維度項目包含 `"Foreground"` 和 `"Background"`未在行動應用程式背景傳送的所有點擊都屬於 `"Foreground"` 維度項目。行動應用程式在背景時傳送的所有點擊都屬於 `"Background"` 維度項目。
