---
title: 分類集設定
description: 建立或編輯分類集。
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '286'
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
* **[!UICONTROL 訂閱]**:分類集所應用的報表套件和變數。 給定分類集當前只支援一個報告套件；計畫支援多個報表套件。

## 結構描述

查看當前為此訂閱配置的分類維。 以下按鈕可用：

* **[!UICONTROL 上載]**:手動上載一個或多個分類維的分類資料。 支援JSON、CSV、TSV和TAB檔案。 上載有效檔案顯示要分類的資料的表預覽。
   * **[!UICONTROL 檔案編碼]**:使用此下拉清單選擇正確的檔案編碼。 有效選項包括 [!UICONTROL UTF-8] 和 [!UICONTROL 拉丁語1]。
   * **[!UICONTROL 清單分隔符]**:選擇正確的清單分隔符。 如果使用下載的檔案或模板檔案，請確保 [!UICONTROL 清單分隔符] 這裡匹配 [!UICONTROL 清單分隔符] 檔案下載時。
   * **[!UICONTROL 應用]**:將上載的分類資料保存到分類集。
