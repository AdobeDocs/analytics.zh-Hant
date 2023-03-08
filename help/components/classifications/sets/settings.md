---
title: 「分類設定」設定
description: 建立或編輯「分類設定」。
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 100%

---

# 「分類設定」設定

設定「分類設定」、上傳資料或下載資料。

>[!NOTE]
>
>此功能將可供所有將報告套裝移轉到新分類架構的客戶使用。如需詳細資訊，請聯絡 Adobe 客戶服務或您的客戶經理。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]** > **[!UICONTROL 設定]** > 按一下想要的「分類設定」名稱。

編輯「分類設定」時，有兩個定位點可供使用；**[!UICONTROL 結構描述]**&#x200B;和&#x200B;**[!UICONTROL 設定]**。

## 設定

[!UICONTROL 設定]定位點中會有下列欄位並可供編輯。

* **[!UICONTROL 名稱]**：「分類設定」名稱。
* **[!UICONTROL 說明]**：此分類設定的說明。
* **[!UICONTROL 所有者名稱]**：該所有者的名稱。
* **[!UICONTROL 所有者電子郵件]**：該所有者的電子郵件地址。
* **[!UICONTROL 通知問題]**：通知此「分類設定」問題的電子郵件地址清單 (以逗號分隔)。
* **[!UICONTROL 標記]**：將一個或多個標記新增到選定的「分類設定」，這讓您可以將「分類設定」進行整理或分組，以便將來更容易找到它們。

其他欄位則僅供參考，無法進行編輯：

* **[!UICONTROL 類型]**：[!UICONTROL 主要]和[!UICONTROL 查詢]之間的分類類型。 通常會使用主要分類。
* **[!UICONTROL 訂閱]**：套用「分類設定」的報告套裝和變數。目前，特定的「分類設定」僅支援一個報告套裝；已計劃支援多個報告套裝。

## 結構描述

檢視目前為此訂閱設定的分類維度。有以下按鈕可供使用：

* **[!UICONTROL 上傳]**：手動上傳一個或多個分類維度的分類資料。支援 JSON、CSV、TSV 以及 TAB 檔案。上傳有效檔案會顯示要分類的資料的表格預覽。
   * **[!UICONTROL 檔案編碼]**：使用此下拉式選單來選取正確的檔案編碼。有效的選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。
   * **[!UICONTROL 清單分隔符號]**：選取正確的清單分隔符號。若使用已下載的檔案或範本檔案，請確保這裡的[!UICONTROL 清單分隔符號]和下載該檔案時的[!UICONTROL 清單分隔符號]相符。
   * **[!UICONTROL 套用]**：將已上傳的分類資料儲存至「分類設定」。

   ![「分類設定」上傳](../assets/classification-set-upload.png)

* **[!UICONTROL 下載]**：下載索引鍵值及其分類欄。
   * **[!UICONTROL 列]**：下載檔案中可包含的最多列數。
   * **[!UICONTROL 下載之間收到的列]**：一個日曆日期選擇器，可讓您依據索引鍵值出現在報表中的時間進行篩選。如果在此日期範圍內未收集到索引鍵值，則它不會出現在已下載的檔案中。
   * **[!UICONTROL 傳回的資料]**：可讓您根據索引鍵值相關聯的分類資料對包含在已下載檔案中的索引鍵值進行篩選的下拉式選單。
      * **[!UICONTROL 所有已分類值]**：包含了在至少一欄中有分類資料的列。
      * **[!UICONTROL 所有未分類值]**：包含了在至少一欄中缺少分類資料的列。
   * **[!UICONTROL 檔案格式]**：確定已下載檔案所使用檔案格式的下拉式選單。選項包括 [!UICONTROL JSON]、[!UICONTROL 逗號分隔值]和 [!UICONTROL Excel 索引鍵分隔值]。
   * **[!UICONTROL 檔案編碼]**：確定檔案編碼的下拉式選單。選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。建議使用 UTF-8。
   * **[!UICONTROL 清單分隔符號]**：確定分隔每列分類欄的清單分隔符號的下拉式選單。

   ![「分類設定」下載](../assets/classification-set-download.png)

* **[!UICONTROL 範本]**：下載範本檔案。這個檔案會和[!UICONTROL 下載]按鈕類似，但不包括任何分類資料或索引鍵值。
   * **[!UICONTROL 檔案格式]**：確定範本檔案所使用檔案格式的下拉式選單。選項包括[!UICONTROL 逗號分隔值]和 [!UICONTROL Excel 索引鍵分隔值]。
   * **[!UICONTROL 檔案編碼]**：確定檔案編碼的下拉式選單。選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。建議使用 UTF-8。
   * **[!UICONTROL 清單分隔符號]**：確定分隔每列分類欄的清單分隔符號的下拉式選單。
* **[!UICONTROL 作業歷史記錄]**：將您帶往[作業管理員](job-manager.md)的快速鍵連結，僅顯示適用於此「分類設定」的作業。

   ![分類設定範本](../assets/classification-set-template.png)
