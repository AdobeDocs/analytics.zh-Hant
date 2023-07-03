---
title: 分類設定管理員
description: 在Adobe Analytics中管理「分類設定」。
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 5%

---

# 分類設定管理員

分類設定管理員可讓您建立、編輯或刪除分類設定。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]** > **[!UICONTROL 設定]**

分類集包含 **訂閱** （報表套裝和維度組合）和 **分類名稱** （包含分類資料的維度）。 訂閱的設定位於 [設定](settings.md)，而分類名稱是在 [結構描述](schema.md).

## 篩選分類設定

分類設定管理員的左側會提供篩選設定，以找出所需的分類設定。 按一下篩選圖示切換篩選設定可見度。您可以透過以下方式篩選分類設定 **[!UICONTROL 標籤]**， **[!UICONTROL 報告套裝]**，或 **[!UICONTROL 所有者]**.

![「分類設定」篩選](../../assets/classification-set-filters.png)

## 分類設定管理員欄

分類設定管理員中有以下欄：

* **[!UICONTROL 分類設定]**：分類設定名稱。 按一下分類設定名稱 [編輯設定](settings.md).
* **[!UICONTROL 訂閱]**：套用此分類設定的訂閱數目。
* **[!UICONTROL 所有者]**：分類設定的擁有者。
* **[!UICONTROL 分類]**：分類設定包含的分類維度數。
* **[!UICONTROL 自動化]**：判斷分類設定是否已設定為自動從雲端位置匯入資料。 自動化可在分類設定的 [綱要](schema.md).
* **[!UICONTROL 上次修改時間]**：上次修改「分類設定」的日期和時間。

## 建立或編輯選項

「分類設定管理員」中有以下按鈕：

* **[!UICONTROL 新增]**： [建立](create.md) 分類設定。
* **[!UICONTROL 依標題搜尋]**：依名稱搜尋「分類設定」。
* **[!UICONTROL 載入更多]**：分類設定管理員最初會顯示最多1000個分類設定。 此按鈕可再載入1000個分類設定。
* **顯示/隱藏欄**：切換任何欄的可見度，除了 [!UICONTROL 分類設定].

按一下所要的「分類設定」旁的核取方塊，選取一或多個分類設定。 選取「分類設定」會顯示下列選項：

* **[!UICONTROL 標籤]**：將一個或多個標籤新增到所選的「分類設定」，這讓您可以將「分類設定」進行整理或分組，以便將來更容易找到它們。
* **[!UICONTROL 刪除]**：刪除分類設定。 根據此「分類設定」的「分類」維度已無法使用。 使用已刪除分類集的已排程專案繼續使用相依維度，直到您重新儲存已排程專案為止。
* **[!UICONTROL 合併]**：開始新的 [consolidation](../consolidations/process.md).
* **[!UICONTROL 重新命名]**：重新命名選取的「分類設定」。
