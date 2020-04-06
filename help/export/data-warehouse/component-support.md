---
title: Data Warehouse 中的元件支援
description: 了解 Data Warehouse 中有哪些額外維度和量度可用，以及不支援哪些維度和量度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Warehouse 中的元件支援

Data Warehouse 的獨特處理架構允許使用某些在 Adobe Analytics 其他功能中通常無法使用的元件。由於其獨特的架構，某些元件無法用於報表或區段。請參閱本頁內容，了解可以使用以及無法使用的項目。

## Data Warehouse 的獨有元件

有些維度和量度可用於 Data Warehouse，但若使用 Adobe Analytics 中的其他功能則無法使用。

### 專門支援的維度

* Experience Cloud ID：用在使用 Experience Cloud ID 服務 (ECID) 的實施，128 位元數字由兩個串連的 64 位元數字組成，兩個數字皆補至 19 位數。
* 頁面 URL：點擊發生的頁面 URL。
* 購買 ID：購買的唯一識別碼，請使用 purchaseID 變數來設定。
* 訪客 ID：提供訪客的唯一識別碼。此值與資料摘要中 `visid_high` 和 `visid_low` 欄的串連值相同。如需詳細資訊，請參閱「資料摘要」下的[資料欄參考](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 專門支援的量度

* 瀏覽次數：在 Data Warehouse 中，此度量會排除非永久性 Cookie 造訪。
* 瀏覽次數 - 所有訪客：在 Data Warehouse 中，此量度與 Adobe Analytics 中其他工具的造訪量度更接近。

## Data Warehouse 中不支援的支援元件

Data Warehouse 中不支援某些維度和量度。

>[!NOTE] 如果 Data Warehouse 不支援該維度或量度，則使用這些元件的區段也不受支援。建立或編輯區段時，請務必檢查產品相容性。

### 不支援的維度

* 某些以時間為主的維度，包括：
   * 上午/下午
   * 每個月的第幾天
   * 星期
   * 一年中的第幾天
   * 小時
   * 分鐘
   * 月份
   * 季別
   * 平日/週末
   * 年
* 某些以路徑為主的維度，包括：
   * 除「登入頁面」外的所有登入維度
   * 除「退出頁面」和「退出連結」外的所有退出維度
   * 點擊深度
   * 回訪頻度
   * 事件之前時間
   * 頁面逗留時間——分組
   * 每次瀏覽逗留時間——分組
   * 瀏覽深度
* 所有搜尋頁面排名
* 階層變數
* 點擊類型
* 找不到頁面 (可作為維度使用；不支援分段)
* 付費搜尋
* 單頁存取次數
* 追蹤退出理由
* 美國州

### 不支援的量度

* 某些以路徑為主的量度，包括：
   * 彈回數
   * 登入點
   * 退出點
   * 重新載入
   * 單次存取
   * 「逗留時間」量度
