---
description: 瞭解如何排除和修復與網段相關的問題。
title: 疑難排解
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 50e6a09e62db60a765da05fa65089a006f103a2b
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 9%

---

# 疑難排解

本文列出了有關這些段的一些常見問題以及如何解決這些問題。

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## 為什麼我的區段完全沒有傳回資料？ {#no-data}

可能的原因包括：

* 反向嵌套 — 例如，在![訪問](/help/assets/icons/User.svg) **[!UICONTROL 訪問]**&#x200B;容器下嵌套![用戶](/help/assets/icons/Visit.svg) **[!UICONTROL 訪問者]**&#x200B;容器。
* 該報告不支援分段。
* 沒有與分段標準匹配的資料。

## 為什麼我看不到在段管理器中建立的段？ {#invisible}

可能的原因包括：

* 某些維僅在Data Warehouse中可用，在「段」(Segment)管理器中不可用。
* 只為特定報表套件選中段。
* 共用段可能已被其他用戶刪除。
* 由於資料中心或瀏覽器快取問題，無法載入段。
* 尚未保存段。
* IP地址可能在用戶端被阻止。

## 為什麼應用段後顯示的資料似乎不正確？ {#page-data}

可能的原因包括：

* 規則或運算子對於所需結果不正確。
* 段中容器的使用不正確。
* 用於段的流量變數設定不正確或已過期。
