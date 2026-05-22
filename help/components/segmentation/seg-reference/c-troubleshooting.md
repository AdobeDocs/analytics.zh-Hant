---
description: 瞭解如何疑難排解及修正與區段相關的問題。
title: 疑難排解
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 9%

---

# 疑難排解

本文列出區段的一些常見問題，以及如何疑難排解這些問題。

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## 為什麼我的區段完全沒有傳回資料？ {#no-data}

可能的原因包括：

* 反向巢狀 — 例如，在![造訪](/help/assets/icons/Visit.svg) **[!UICONTROL 造訪]**&#x200B;容器下巢狀![使用者](/help/assets/icons/User.svg) **[!UICONTROL 訪客]**&#x200B;容器。
* 報表不支援分段。
* 沒有資料符合分段條件。

## 為什麼我在區段管理員中看不到我建立的區段？ {#invisible}

可能的原因包括：

* 部分維度僅可在Data Warehouse中使用，不可在「區段管理器」中使用。
* 系統只會針對特定報表套裝勾選「區段」 。
* 共用區段可能已遭其他使用者刪除。
* 由於資料中心或瀏覽器快取問題，無法載入區段。
* 區段尚未儲存。
* 使用者端可能會封鎖IP位址。

## 為什麼在套用區段後顯示的資料不正確？ {#page-data}

可能的原因包括：

* 規則或運運算元對所需結果而言不正確。
* 區段內容器的使用不正確。
* 用來劃分割槽段的流量變數未正確設定或已過期。
