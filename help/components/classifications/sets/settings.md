---
title: 分類集設定
description: 建立或編輯分類集。
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: c849f216f8dda83070fc3f8d8b1c25fba4d2786a
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# 分類集設定

配置分類集、上載資料或下載資料。

**[!UICONTROL 元件]** > **[!UICONTROL 分類集]** > **[!UICONTROL 集]** >按一下所需的分類集名稱

編輯分類集時，有兩個頁籤可用； **[!UICONTROL 架構]** 和 **[!UICONTROL 設定]**。

## 設定

以下欄位可在 [!UICONTROL 設定] 的子菜單。

* **[!UICONTROL 名稱]**:分類集名稱。
* **[!UICONTROL 說明]**:分類集的說明。
* **[!UICONTROL 所有者名稱]**:所有者名稱。
* **[!UICONTROL 所有者電子郵件]**:所有者的電子郵件地址。
* **[!UICONTROL 通知問題]**:以逗號分隔的電子郵件地址清單，該清單將通知此分類集的問題。
* **[!UICONTROL 標籤]**:將一個或多個標籤添加到選定的分類集中，這樣您就可以組織或分組分類集，以便將來更容易找到它們。

其他欄位僅供參考，無法編輯：

* **[!UICONTROL 類型]**:分類的類型 [!UICONTROL 主要] 和 [!UICONTROL 查找]。 通常使用主要分類。
* **[!UICONTROL 訂閱]**:分類集所應用的報表套件和變數。 此時，給定分類集僅支援一個報告套件；計畫支援多個報表套件。

## 結構描述

查看當前為此訂閱配置的分類維。 以下按鈕可用：

* **[!UICONTROL 上載]**:手動上載一個或多個分類維的分類資料。 支援JSON、CSV、TSV和TAB檔案。 上載有效檔案顯示要分類的資料的表預覽。
   * **[!UICONTROL 檔案編碼]**:使用此下拉清單選擇正確的檔案編碼。 有效選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL 拉丁語1]。
   * **[!UICONTROL 清單分隔符]**:選擇正確的清單分隔符。 如果使用下載的檔案或模板檔案，請確保 [!UICONTROL 清單分隔符] 這裡匹配 [!UICONTROL 清單分隔符] 檔案下載時。
   * **[!UICONTROL 應用]**:將上載的分類資料保存到分類集。

   ![分類集上載](../assets/classification-set-upload.png)

* **[!UICONTROL 下載]**:下載鍵值及其分類列。
   * **[!UICONTROL 行]**:要包含在下載檔案中的最大行數。
   * **[!UICONTROL 下載在以下時間之間接收的行]**:日曆日期選取器，允許您按鍵值在報告中出現時進行篩選。 如果在此日期範圍內未收集密鑰值，則它不會顯示在下載的檔案中。
   * **[!UICONTROL 返回的資料]**:一個下拉清單，用於根據下載的檔案的相關分類資料篩選包含在其中的鍵值。
      * **[!UICONTROL 所有分類值]**:包括其中分類資料包含在至少一個列中的行。
      * **[!UICONTROL 所有未分類的值]**:包括至少一列中缺少分類資料的行。
   * **[!UICONTROL 檔案格式]**:確定下載檔案所在的檔案格式的下拉清單。 選項包括 [!UICONTROL JSON]。 [!UICONTROL 逗號分隔值], [!UICONTROL Excel頁籤分隔的值]。
   * **[!UICONTROL 檔案編碼]**:確定檔案編碼的下拉清單。 選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL 拉丁語1]。 建議使用UTF-8。
   * **[!UICONTROL 列出分隔符]**:確定在每行上分隔分類列的清單分隔符的下拉清單。

   ![分類集下載](../assets/classification-set-download.png)

* **[!UICONTROL 模板]**:下載模板檔案。 此檔案與 [!UICONTROL 下載] 按鈕，但它不包含任何分類資料或鍵值。
   * **[!UICONTROL 檔案格式]**:確定模板檔案所在的檔案格式的下拉清單。 選項包括 [!UICONTROL 逗號分隔值], [!UICONTROL Excel頁籤分隔的值]。
   * **[!UICONTROL 檔案編碼]**:確定檔案編碼的下拉清單。 選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL 拉丁語1]。 建議使用UTF-8。
   * **[!UICONTROL 列出分隔符]**:確定在每行上分隔分類列的清單分隔符的下拉清單。
* **[!UICONTROL 作業歷史記錄]**:將您帶到 [作業管理器](job-manager.md)，僅顯示此分類集的作業。

   ![分類集模板](../assets/classification-set-template.png)
