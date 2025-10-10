---
title: Report Builder 概觀
description: 說明 Report Builder 功能
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 100%

---

# Report Builder 概觀

最初僅在 Customer Journey Analytics 中可用的新 Javascript Report Builder 增益集，現在也已引入 Adobe Analytics 中。此新版本具有下列幾個優點：

- 透過用於資料區塊建立和管理之改善的工作流程 (包括更大的資料區塊靈活性)，更快且更輕鬆地在 Excel 中找到深入分析
- 跨平台：無需登入 VM，即可使用 Report Builder，因為我們現在支援個人電腦、Mac 及 Excel Online
- 由於採用 API 2.0 升級，等待資料區塊傳回的時間更少
- 強化速度

舊版 Report Builder 工具的使用者可以[將舊版活頁簿](/help/analyze/report-builder/convert-workbooks.md) 轉換至新版 Report Builder。

Report Builder 可讓您使用 Adobe Analytics 資料輕鬆建立、編輯和重新整理自訂報告。透過 Report Builder 簡單靈活拖放 UI，即可在 Excel 中從 Adobe Analytics 資料建立複雜的資料查詢和自訂報告。

使用 Report Builder，您可以：

- 參照現有的工作表儲存格，以取得完美的列順序、日期範圍或篩選器
- 使用行事曆、儲存格參照或日期數學，建立自訂日期
- 使用熟悉的 Excel 格式化工具設計您的表格和視覺效果

## 同時使用舊版 Report Builder 和新版 Report Builder

您仍然可以使用兩個版本的 Report Builder，但請注意下列事項：

- 請勿同時對同一檔案使用兩個版本的 Report Builder。兩個版本之間互相排斥。
- 您仍然可以在舊版活頁簿上使用舊版 Report Builder，並在新活頁簿上使用新版 Report Builder。
- 此外，您也可以自動將[舊版活頁簿](/help/analyze/report-builder/convert-workbooks.md)轉換至新版 Report Builder 格式。在此之前，請複製並重新命名此檔案。

## 新版 Report Builder 不支援舊版 Report Builder 功能

將舊版 Report Builder 的功能與新版 Report Builder 增益集的功能進行比較時，部分舊版功能不再可用：

- 即時請求

- 路徑/流失報告

- 排程報告的 FTP 選項

- 訪客量度。下列量度都將轉換至「不重複訪客」，即使報告結果可能不完全符合：`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` 以及 `visitorsyearly`。這也適用於 `mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` 以及 `mobilevisitorsyearly`。

## 常見使用案例

- **資料擷取**：Adobe Report Builder 可讓您將 Adobe Analytics 中的資料擷取至 Excel 中。您可以建立自訂報告和查詢，以擷取與您的分析相關的特定資料點。

- **自訂報告**：您可以在 Excel 中設計和格式化自訂報告，以滿足您的特定報告需求。為不同利害關係人量身訂做報告時，此功能特別實用。

- **臨時分析**：使用者可以快速產生臨時報告來回答特定問題或探索資料趨勢，無需經歷冗長的報告建立過程。

- **儀表板**：從 CJA 擷取的資料可用來建立以 Excel 為基礎的儀表板和視覺效果，以取得關鍵績效指標 (KPI) 的高階概觀。

- **共用深入分析**：您可以與可能無法直接存取 CJA 的團隊成員或利害關係人共用 Excel 報告和深入分析。

## 概觀影片

>[!IMPORTANT]
>
>此概觀影片顯示 Customer Journey Analytics 的 Report Builder 使用者介面。部分使用者介面和術語有所不同。否則，使用者體驗相同。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builder 概觀](https://video.tv.adobe.com/v/3452591?quality=12&learn=on&captions=chi_hant){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

您可以從 [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview) 下載 Report Builder。
