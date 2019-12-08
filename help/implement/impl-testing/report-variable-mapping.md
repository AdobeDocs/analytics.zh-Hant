---
description: 下列表格顯示報表與變數的對映，或是報表和其中使用的變數。
keywords: Analytics Implementation
title: 報表與變數的對應
topic: Developer and implementation
uuid: 4707660c-4be5-425c-a690-7bc6df4cc0fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 報表與變數的對應

下列表格顯示報表與變數的對映，或是報表和其中使用的變數。

**轉換報表** 下表列出用來填入各個報表的轉換變數:

| 購買 |
|---|
| 轉換和平均值 | s.events、s.products、s.purchaseID | 將 s.events 設為購買、產品詳細資料、訂單號碼 |
| 收入 | s.events、s.products、s.purchaseID | 將 s.events 設為購買、產品詳細資料、訂單號碼 |
| 訂購 | s.events、s.products、s.purchaseID | 將 s.events 設為購買、產品詳細資料、訂單號碼 |
| 件數 | s.events、s.products、s.purchaseID | 將 s.events 設為購買、產品詳細資料、訂單號碼 |

| 購物車 |
|---|
| 轉換和平均值 | s.events、s.products、s.purchaseID |  |
| 購物車 | s.events | 將 s.events 設為 scOpen |
| 購物車檢視 | s.events | 將 s.events 設為 scView |
| 購物車新增 | s.events | 將 s.events 設為 scAdd |
| 購物車移除 | s.events | 將 s.events 設為 scRemove |
| 結帳 | s.events | 將 s.events 設為 scCheckout |

| 自訂事件 |
|---|
| 自訂事件 1 | s.events | 以 event1 - event100 填入 |
| ... | ... | 以 event1 - event100 填入 |
| 自訂事件 100 | s.events | 以 event1 - event100 填入 |

| 產品 |
|---|
| 轉換和平均值 | s.events、s.products、s.purchaseID |  |
| 產品 | s.products、s.events | 可能隨右欄的度量而不同 |
| 交叉銷售 | s.products、s.events、s.purchaseID | 可能隨右欄的度量而不同 |
| 類別 | s.products | 可能隨右欄的度量而不同 |

| 促銷活動 |
|---|
| 轉換和平均值 | s.products、s.events、s.campaign |  |
| 追蹤程式碼 | s.campaign |  |
| 創作元素 | 不適用 | 在 [!DNL Analytics] 中定義 |
| 促銷活動 | 不適用 | 在 [!DNL Analytics] 中定義 |

| 客戶忠誠度 |
|---|
| 客戶忠誠度 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |

| 銷售週期 |
|---|
| 首次購買間隔天數 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |
| 上次購買間隔天數 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |
| 訪問次數 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |
| 每日獨特客戶 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |
| 每月獨特客戶 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |
| 每年獨特客戶 | s.products、s.events、s.purchaseID | 訂購確認 (感謝您)頁面上設定的變數 |

| 尋找方法 |
|---|
| 反向連結網域 | 不適用 | 由 .JS 檔案自動設定 |
| 原始反向連結網域 | 不適用 | 由 .JS 檔案自動設定 |
| 搜尋引擎 | 不適用 | 由 .JS 檔案自動設定 |
| 搜尋關鍵字 | 不適用 | 由 .JS 檔案自動設定 |

| 訪客資料 |
|---|
| 頂級網域 | 不適用 | 由 .JS 檔案自動設定 |
| 語言 | 不適用 | 由 .JS 檔案自動設定 |
| 時區 | 不適用 | 由 .JS 檔案自動設定 |
| 州 | s.state | 訂購確認 (感謝您)頁面上設定的變數 |
| 郵遞區號 | s.zip | 訂購確認 (感謝您)頁面上設定的變數 |
| 網域 | 不適用 | 由 .JS 檔案自動設定 |

| 技術 |
|---|
| 瀏覽器 | 不適用 | 由 .JS 檔案自動設定 |
| 作業系統 | 不適用 | 由 .JS 檔案自動設定 |
| 螢幕解析度 | 不適用 | 由 .JS 檔案自動設定 |

| 網站路徑 |
|---|
| 頁面值 | s.pageName、s.products、s.events、s.purchaseID |  |
| 登入頁面 | s.pageName |  |
| 原始登入頁面 | s.pageName |  |
| 每次瀏覽頁面 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 網站逗留時間 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 網站區域 | [!UICONTROL s.channel] | 與[!UICONTROL 「流量」]報表區段中的[!UICONTROL 「管道」]報表相同 |

| 客戶變數 |
|---|
| 自訂 eVar 1 | [!UICONTROL s.eVar] 1 |  |
| 自訂 eVar 2 | [!UICONTROL s.eVar] 2 |  |
| 自訂 eVar 3 | [!UICONTROL s.eVar] 3 |  |
| ... |  |  |
| 自訂 eVar 75 | [!UICONTROL s.eVar] 75 |  |

## 流量報表 {#section_76A74C3D7B60461D9ADE0E5E183DD777}

下表列出用來填入各個報表的[!UICONTROL 流量]變數: 

| 計算量度 |
|---|
| 不適用 | 不適用 | 不適用 |

| 網站流量 |
|---|
| 頁面檢視 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 每小時獨特訪客 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 每日不重複訪客 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 每月不重複訪客 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 每年不重複訪客 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 瀏覽 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 檔案下載 | 不適用 | 由 .JS 檔案自動追蹤 (根據 .JS 變數設定) |

| 尋找方法 |
|---|
| 反向連結網域 | 不適用 | 由 .JS 檔案自動設定 |
| 反向連結 | 不適用 | 由 .JS 檔案自動設定 |
| 搜尋引擎 | 不適用 | 由 .JS 檔案自動設定 |
| 搜尋關鍵字 | 不適用 | 由 .JS 檔案自動設定 |
| 回訪頻度 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 每日回訪 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 回訪 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 存取編號 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |

| 訪客資料 |
|---|
| 網域 | 不適用 | 由 .JS 檔案自動設定 |
| 頂級網域 | 不適用 | 由 .JS 檔案自動設定 |
| 語言 | 不適用 | 由 .JS 檔案自動設定 |
| 時區 | 不適用 | 由 .JS 檔案自動設定 |
| 訪客詳細資料 | 不適用 | 由 .JS 檔案自動設定 |
| 最近 100 位訪客 | 不適用 | 依 [!DNL Analytics] 中的商業規則計算 |
| 使用者首頁 | 不適用 | 由 .JS 檔案自動設定 |
| 關鍵訪客 | 不適用 | 根據訪客的 IP 位址 |
| 關鍵訪客檢視的頁面 | 不適用 | 根據訪客的 IP 位址 |

| 地域劃分 |
|---|
| 國家 | 不適用 | 根據訪客的 IP 位址 |
| 美國州 | 不適用 | 根據訪客的 IP 位址 |
| DMA | 不適用 | 根據訪客的 IP 位址 |
| 國際城市 | 不適用 | 根據訪客的 IP 位址 |
| 美國城市 | 不適用 | 根據訪客的 IP 位址 |

| 技術 |
|---|
| 瀏覽器類型 | 不適用 | 由 .JS 檔案自動設定 |
| 瀏覽器 | 不適用 | 由 .JS 檔案自動設定 |
| 行動裝置 | 不適用 | 由 .JS 檔案自動設定 |
| 瀏覽器寬度 | 不適用 | 由 .JS 檔案自動設定 |
| 瀏覽器高度 | 不適用 | 由 .JS 檔案自動設定 |
| 作業系統 | 不適用 | 由 .JS 檔案自動設定 |
| 監視器色彩深度 | 不適用 | 由 .JS 檔案自動設定 |
| 螢幕解析度 | 不適用 | 由 .JS 檔案自動設定 |
| Netscape 外掛程式 | 不適用 | 由 .JS 檔案自動設定 |
| Java | 不適用 | 由 .JS 檔案自動設定 |
| JavaScript | 不適用 | 由 .JS 檔案自動設定 |
| JavaScript 版本 | 不適用 | 由 .JS 檔案自動設定 |
| Cookie | 不適用 | 由 .JS 檔案自動設定 |
| 連線類型 | 不適用 | 由 .JS 檔案自動設定 |
| 區段 |

| 區段 |
|---|
| 最受歡迎頁面 | s.pageName |  |
| 最受歡迎網站區域 | s.channel |  |
| 最受歡迎伺服器 | s.server |  |

| 自訂分析 |
|---|
| 自訂連結 | s.linkName | 需要自訂實施 |
| 自訂分析 1 | s.prop1 |  |
| ... | ... |  |
| 自訂分析 75 | s.prop75 |  |

| 階層 |
|---|
| 階層 1 | s.hier1 |  |
| ... | ... |  |
| 階層 5 | s.hier5 |  |

## 路徑分析報表 {#section_85E0A2396B894659A6BE572819263E95}

下表列出用來填入 [!DNL Analytics] 內各個報表的路徑分析變數: 

| 頁面 |
|---|
| 頁面摘要 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 頁面值 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 最受歡迎頁面 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 重新載入 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 頁面點按次數 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 頁面逗留時間 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 找不到頁面 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |

| 登入與退出 |
|---|
| 登入頁面 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 退出頁面 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 退出連結 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |

| 完整路徑 |
|---|
| 完整路徑 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 最長路徑 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 路徑長度 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 每次瀏覽逗留時間 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 單頁存取 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |

| 進階分析 |
|---|
| 上一頁 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 下一頁 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 上一頁流量 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 下一頁流量 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| PathFinder | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
| 流失 | s.pageName (或其他路徑變數) | 也根據內部商業規則 |
