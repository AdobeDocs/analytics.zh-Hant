---
title: 搜尋引擎
description: 訪客用來存取您的網站的搜尋引擎。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 93%

---

# 搜尋引擎

「搜尋引擎」 [維度](overview.md)會報告訪客用來存取您的網站的搜尋引擎。 反向連結必須符合下列兩個條件，才能分類為搜尋引擎：

* 反向連結網域經 Adobe 認可為有效的搜尋引擎；
* 反向連結 URL 中有關鍵字查詢字串參數存在。查詢字串參數可以空白 (基於隱私權實務，數個搜尋引擎也是如此)。

如果您想要區分付費和免費搜尋，必須使用[付費搜尋偵測](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)。搜尋引擎可使用多個維度：

* **搜尋引擎**：用來存取您的網站的搜尋引擎，無論是付費還是免費。
* **搜尋引擎 - 付費**：用來存取您的網站的搜尋引擎 (符合付費搜尋偵測)。
* **搜尋引擎 - 免費**：用來存取您的網站的搜尋引擎 (不符合付費搜尋偵測)。

## 將資料填入此維度中

此維度會參考 Adobe 內部的多個查閱表格。每個值都以點擊的[反向連結](referrer.md)為基礎，而這有賴於[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。請確定反向連結維度和內部 URL 篩選器皆已正確設定。

## 維度項目

維度項目包含用來存取您的網站的搜尋引擎。範例值包括 `"Google"`、`"Microsoft Bing"` 和 `"DuckDuckGo"`。`"Unspecified"` 維度項目是所有非搜尋流量。
