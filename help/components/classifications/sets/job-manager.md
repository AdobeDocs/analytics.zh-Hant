---
title: 分類設定作業管理員
description: 檢視從「分類設定」產生的最新和已完成的分類作業。
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 100%

---

# 分類設定作業管理員

分類設定作業管理員可讓您查看從「分類設定」產生的最新和已完成的分類作業。您還可以利用此介面下載特定作業的分類資料或範本，或將更多資料上傳至某一項作業。

>[!NOTE]
>
>此功能目前在有限版本中提供。如果您想存取此功能，請和 Adobe 客戶服務或您的客戶經理聯絡，他們可以將您的請求轉寄給分類團隊進行佈建。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]** > **[!UICONTROL 作業]**

請注意，您無法從這個介面建立作業。反之，您可以上傳資料到某一個「分類設定」來建立作業、要求已下載的檔案或是要求範本檔案。

## 篩選「分類設定」

分類設定作業管理員的左側會提供篩選設定，以找出所需的作業。按一下篩選圖示切換篩選設定可見度。您可以按&#x200B;**[!UICONTROL 分類設定]**、**[!UICONTROL 完成時間]**&#x200B;或&#x200B;**[!UICONTROL 狀態]**&#x200B;來篩選「分類設定」。

![分類設定作業篩選](../assets/classification-set-job-filters.png)

「分類設定作業管理員」欄的上方有更多篩選選項：

* **[!UICONTROL 依標題搜尋]**：按檔案名稱搜尋作業。 
* **[!UICONTROL 載入更多]**：分類設定作業管理員最初會顯示最多 1000 個作業。按一下此按紐即可再載入 1000 個作業。
* **顯示/隱藏欄**：除了[!UICONTROL 檔案名稱]和[!UICONTROL 完成時間]之外，還切換任何欄的可見度。

## 「分類設定作業管理員」欄

分類設定作業管理員中有以下欄：

* **[!UICONTROL 檔案名稱]**: 上傳或下載的檔案的名稱。
* **[!UICONTROL 分類設定]**：套用此「分類設定」的檔案名稱。您可以按一下「分類設定」名稱，即可存取該「分類設定」的[設定](settings.md)。
* **[!UICONTROL 大小]**：檔案的大小。
* **[!UICONTROL 狀態]**: 處理檔案的作業狀態。
   * **[!UICONTROL 已建立]**：已提交作業。
   * **[!UICONTROL 已排入佇列]**：檔案已準備就緒可供處理，並正等候分類伺服器處理該檔案。
   * **[!UICONTROL 已驗證]**：檔案為有效狀態並正等候處理。
   * **[!UICONTROL 已失敗的驗證]**：檔案已格式化或在其他方面無效。檔案未經過處理。
   * **[!UICONTROL 處理中]**：檔案正由 Adobe 積極地處理。
   * **[!UICONTROL 已失敗的處理]**：檔案處理已失敗。
   * **[!UICONTROL 完成]**：處理完成。分類資料會顯示在報表中。
   * **[!UICONTROL 已失敗]**：和驗證或處理無關的一般性失敗。
* **[!UICONTROL 類型]**：作業的類型。
* **[!UICONTROL 檔案下載]**：僅適用於下載作業，例如下載分類資料或下載範本。若下載已可供使用，此欄會提供下載連結。
* **[!UICONTROL 完成時間]**: 作業已完成 (或已失敗) 的日期和時間。