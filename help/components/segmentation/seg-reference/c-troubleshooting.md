---
description: 區段相關問題的疑難排解與修正。
title: 區段疑難排解
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 50%

---

# 區段疑難排解

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## 為什麼我的區段完全沒有傳回資料？ {#no-data}

可能的原因包括：

* 反向巢狀 — 例如，在![造訪](/help/assets/icons/Visit.svg) **[!UICONTROL 造訪]**&#x200B;容器下巢狀![使用者](/help/assets/icons/User.svg) **[!UICONTROL 訪客]**&#x200B;容器。
* 報表不支援分段。
* 沒有與分段標準相符的資料。

## 為什麼我在區段管理員中看不到我建立的區段？ {#invisible}

可能的原因包括：

* 部分維度僅可在Data Warehouse中使用，不可在「區段管理器」中使用。
* 區段只為特定報表套裝而勾選。
* 共用區段已由其他使用者刪除。
* 由於資料中心或瀏覽器快取問題，無法載入區段。
* 區段未儲存。
* 可能在使用者端封鎖了 IP 位址。

## 為什麼在套用區段後顯示的資料不正確？ {#page-data}

可能的原因包括：

* 規則或運運算元對所需結果而言不正確。
* 區段內容器的使用不正確。
* 用於區段的流量變數未正確設定或已過期。
