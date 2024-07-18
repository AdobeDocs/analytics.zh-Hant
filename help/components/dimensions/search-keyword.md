---
title: 搜尋關鍵字
description: 訪客用來存取您的網站的搜尋關鍵字。
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# 搜尋關鍵字

「搜尋關鍵字」[維度](overview.md)會報告訪客用來存取您的網站的搜尋關鍵字。

>[!IMPORTANT]
>
>隨著隱私權實務趨於嚴謹，大部分的搜尋引擎不再傳遞搜尋關鍵字。Adobe 已辨識出搜尋引擎但缺少關鍵字的點擊，會歸類到維度項目 `"Keyword unavailable"` 下。

反向連結必須符合下列兩個條件，才能分類為搜尋關鍵字：

* 反向連結網域經 Adobe 認可為有效的[搜尋引擎](search-engine.md)；
* 反向連結 URL 中有關鍵字查詢字串參數存在。如果關鍵字查詢字串存在，但不含任何值，則會歸類到維度項目 `"Keyword unavailable"` 下。

如果您想要區分付費和免費搜尋，必須使用[付費搜尋偵測](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)。搜尋關鍵字可使用多個維度：

* **搜尋關鍵字**：用來存取您的網站的搜尋關鍵字，無論是付費還是免費。
* **搜尋關鍵字 - 付費**：用來存取您的網站的搜尋關鍵字 (符合付費搜尋偵測)。
* **搜尋關鍵字 - 免費**：用來存取您的網站的搜尋關鍵字 (不符合付費搜尋偵測)。

## 將資料填入此維度中

此維度會參考 Adobe 內部的多個查閱表格。每個值都以點擊的[反向連結](referrer.md)為基礎，而這有賴於[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。請確定反向連結維度和內部 URL 篩選器皆已正確設定。

## 維度項目

維度項目包含用來存取您的網站的搜尋關鍵字。`"Unspecified"` 維度項目是所有非搜尋流量。
