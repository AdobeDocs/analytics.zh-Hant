---
title: 事件之前時間
description: 量度與造訪的首次點擊之間相隔的時間量。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 78%

---


# 事件之前時間

「事件之前時間」維度會報告造訪的首次點擊與所需量度之間經過的時間量。此維度可用來判斷點擊成功事件 (例如表單提交或購買) 所花費的時間量。

## 將資料填入此維度中

雖然此維度在技術上可立即用於所有實作，但對於自訂和購買事件最能發揮效用。Adobe 建議在您的網站上實作自訂事件。如果您實作自訂事件，即無須對此維度進行額外的實作。

## 維度項目

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item.
