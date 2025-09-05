---
title: Data Warehouse的元件支援
description: 了解 Data Warehouse 中有哪些額外維度和量度可用，以及不支援哪些維度和量度。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 45%

---

# Data Warehouse 中的元件支援

Data Warehouse架構中的獨特處理可允許使用某些在Adobe Analytics其他功能中通常無法使用的元件。 由於其獨特的架構，某些元件無法用於報表或區段。請參閱本頁內容，了解可以使用以及無法使用的項目。

## Data Warehouse 的獨有元件

在Adobe Analytics中使用其他功能時，無法在Data Warehouse中使用某些維度和量度。

### 專門支援的維度

* **Experience Cloud ID**：針對使用Experience Cloud ID服務(ECID)的實作，128位元數字由兩個串連的64位元數字組成，兩個數字皆補至19位數。
* **頁面URL**：點選發生的頁面URL。
* **購買ID**：購買的唯一識別碼，請使用purchaseID變數設定。
* **訪客識別碼**：提供訪客的唯一識別碼。 此值與資料摘要中 `visid_high` 和 `visid_low` 欄的串連值相同。如需詳細資訊，請參閱「資料摘要」下的[資料欄參考](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 專門支援的量度

* **瀏覽次數**：在Data Warehouse內容中，此量度會排除非永久性Cookie瀏覽次數。
* **瀏覽次數 — 所有訪客**：在Data Warehouse中，此量度與Adobe Analytics內其他工具中的瀏覽量度更接近。

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
   * 回訪頻率
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
* 參與率量度（如[建立「參與率」量度](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)中所述）

### 以不同方式支援的維度（非標準日期格式）

支援下列以時間為基礎的維度：

* 年
* 季
* 月
* 週
* 日
* 小時
* 分鐘

但是，使用這些維度時，日期的輸出是非標準值。

在Data Warehouse中計算日期輸出時，請考慮下列事項：

* 日期維度會以下列格式顯示： `1YYMMDDHHMM`

* 年(YY)由1900抵銷。 這表示您將`1900`新增至日期欄位的前3個值。

  例如，如果Data Warehouse中日期範圍周欄位的值為`1250901`，您會新增1900到125，這會產生2025年。

* 所有月份都是以零為基準，1月則以00表示，2月則以01表示，依此類推，如下所示：

   * 00：一月
   * 01:2月
   * 02:3月
   * 03:4月
   * 04： 5月
   * 05:6月
   * 06:7月
   * 07:8月
   * 08:9月
   * 09:10月
   * 10:11月
   * 11:12月

  例如，如果Data Warehouse中「日期範圍週」欄位的值為`1250901`，則月份會顯示為09，表示10月。




## Data Warehouse中作為維度的區段

當您在 Data Warehouse 中使用區段作為維度時，報告會傳回一欄含有 `"0"` 或 `"1"`：

* **`"0"`**：該維度項目不符合區段標準。
* **`"1"`**：該維度項目符合區段標準。
