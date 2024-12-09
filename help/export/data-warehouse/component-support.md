---
title: Data Warehouse中的元件支援
description: 了解 Data Warehouse 中有哪些額外維度和量度可用，以及不支援哪些維度和量度。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 60%

---

# Data Warehouse 中的元件支援

Data Warehouse架構中的獨特處理可允許某些在Adobe Analytics的其他功能中通常無法使用的元件。 由於其獨特的架構，某些元件無法用於報表或區段。請參閱本頁內容，了解可以使用以及無法使用的項目。

## Data Warehouse 的獨有元件

在Adobe Analytics中使用其他功能時，某些可用於Data Warehouse的維度和量度無法使用。

### 專門支援的維度

* **Experience Cloud識別碼**：對於使用Experience Cloud識別碼服務(ECID)的實作，由兩個串連的64位元數字組成的128位元數字補至19位數。
* **頁面URL**：點選發生的頁面URL。
* **購買ID**：購買的唯一識別碼，請使用purchaseID變數設定。
* **訪客識別碼**：提供訪客的唯一識別碼。 此值與資料摘要中 `visid_high` 和 `visid_low` 欄的串連值相同。如需詳細資訊，請參閱「資料摘要」下的[資料欄參考](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 專門支援的量度

* **造訪次數**：在Data Warehouse內容中，此量度會排除非永久性Cookie造訪次數。
* **瀏覽次數 — 所有訪客**：在Data Warehouse內容中，此量度與Adobe Analytics內其他工具中的瀏覽量度更接近。

## Data Warehouse 中不支援的支援元件

Data Warehouse 中不支援某些維度和量度。

>[!NOTE]
>
>如果 Data Warehouse 不支援該維度或量度，則使用這些元件的區段也不受支援。建立或編輯區段時，請務必檢查產品相容性。

### 不支援的維度

* 上午/下午
* 某些以路徑為主的維度，包括：
   * 除「登入頁面」外的所有登入維度
   * 除「退出頁面」和「退出連結」外的所有退出維度
   * 點擊深度
   * 回訪頻度
   * 事件之前時間
   * 頁面逗留時間 - 分段
   * 每次瀏覽逗留時間 - 分段
* 所有搜尋頁面排名
* 階層變數
* 點擊類型
* 找不到頁面 (可作為維度使用；不支援分段)
* 付費搜尋
* 單頁造訪次數
* 追蹤選擇退出原因
* 美國各州

### 不支援的量度

* 某些以路徑為主的量度，包括：
   * 彈回數
   * 登入點
   * 退出點
   * 重新載入
   * 單次存取
   * 「逗留時間」量度
* 參與率量度（如[建立「參與率」量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)中所述）

### 以不同方式支援的Dimension

支援下列以時間為基礎的維度。 但使用這些維度時，日期輸出不是使用標準格式。具體來說，年份會以1900為單位進行偏移，而月份則以零為基準。

* 年
* 季
* 月
* 週
* 日
* 小時
* 分鐘

## Data Warehouse中作為維度的區段

當您在 Data Warehouse 中使用區段作為維度時，報告會傳回一欄含有 `"0"` 或 `"1"`：

* **`"0"`**：該維度項目不符合區段標準。
* **`"1"`**：該維度項目符合區段標準。
