---
title: 上次接觸管道
description: 訪客參與有效期內最近的行銷管道。
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 90%

---

# 上次接觸管道

「上次接觸管道」維度[維度](overview.md)會報告訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。 若要了解哪些行銷管道促進網站流量進而發生轉換，此維度非常有用，讓您可將行銷工作聚焦於最有效的領域。

## 將資料填入此維度中

此維度會直接參照您在[「行銷管道管理員」](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)中定義的管道名稱。

傳送至 Adobe 資料收集伺服器的每個點擊，都會透過報表套裝的行銷管道處理規則執行。它會以數值順序反覆每個規則，直到找到相符項目，而該行銷管道會繫結至點擊。上次接觸管道會持續與訪客同時存在，直到對方超過訪客參與期間 (預設為 30 天) 沒有造訪網站。

如果您要將此維度設為特定值，則需執行下列步驟：

* 在「報表套裝設定」下的「行銷管道管理員」中，將所需的維度項目設為管道。
* 設定包含所需點擊條件的行銷管道處理規則。
* 訪客對您網站的點擊必須符合行銷管道處理規則中列出的條件。

## 維度項目

維度項目包含「行銷管道管理員」中的所有管道名稱。預設情況下，值包括 `"Paid search"`、`"Natural search"`、`"Display"`、`"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"` 和 `"Referring domains"`。您可以在「行銷管道管理員」中新增或刪除管道，而這會影響此維度的值。
