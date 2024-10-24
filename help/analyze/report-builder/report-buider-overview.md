---
title: Adobe Report Builder有哪些新功能？
description: 說明新的Report Builder功能
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 7e8a25381f2eadafc5dc22a0991060ea475b5d43
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 27%

---

# 關於新的Adobe Report Builder

原本只能在Customer Journey Analytics中使用的新JavascriptReport Builder增益集，現在也在Adobe Analytics中推出。 這個新版本有幾個優點：

- 透過改善的資料區塊建立和管理工作流程（包括更高的資料區塊彈性），更快且更輕鬆地在Excel中尋找深入分析
- 跨平台：不再登入您的虛擬機器器以使用Report Builder，因為我們現在支援PC、Mac和Excel Online
- 藉由API 2.0升級，減少等待資料區塊回訪的時間
- 強化速度

>[!NOTE]
>
>Adobe Analytics上此版本Report Builder的活頁簿排程功能尚未發行，但將於2025年初推出。 您可以立即開始使用不需要排程的活頁簿。

舊版Report Builder工具的使用者可以[將舊版活頁簿](/help/analyze/report-builder/convert-workbooks.md)轉換為新Report Builder。

Report Builder可讓您使用Adobe Analytics資料輕鬆建立、編輯和重新整理自訂報表。 透過Report Builder簡單彈性的拖放UI，您可以在Excel中從Adobe Analytics資料建立複雜的資料查詢和自訂報表。

透過Report Builder，您可以：

- 參照現有的工作表儲存格，以取得完美的列順序、日期範圍或篩選器
- 使用行事曆、儲存格參照或日期數學，建立自訂日期
- 使用熟悉的 Excel 格式化工具設計您的表格和視覺效果

## 並排使用舊版Report Builder和新Report Builder

您仍可使用兩個版本的Report Builder，但需注意下列事項：

- 請勿在同一個檔案上同時使用兩個Report Builder版本。 兩者互斥。
- 您仍然可以在舊版活頁簿上使用舊版Report Builder，並在新活頁簿上使用新Report Builder。
- 此外，您可以自動[將舊版活頁簿](/help/analyze/report-builder/convert-workbooks.md)轉換為新的Report Builder格式。 在執行此操作之前，請複製並重新命名檔案。

## 新Report Builder中不支援舊版Report Builder功能

將舊版Report Builder的功能與新Report Builder增益集比較時，有些舊版功能已無法使用：

- 即時請求

- 路徑/流失報告

- 排程報表的FTP選項

- 訪客量度。 下列量度將全部轉換為「不重複訪客」，即使報表結果可能不是完全相符： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`以及`visitorsyearly`。 這也適用於`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。

## 常見使用案例

- **資料擷取**： Adobe Report Builder可讓您將資料從Adobe Analytics擷取至Excel。 您可以建立自訂報告和查詢，以擷取與您的分析相關的特定資料點。

- **自訂報告**：您可以在 Excel 中設計和格式化自訂報告，以滿足您的特定報告需求。為不同利害關係人量身訂做報告時，此功能特別實用。

- **臨時分析**：使用者可以快速產生臨時報告來回答特定問題或探索資料趨勢，無需經歷冗長的報告建立過程。

- **儀表板**：從 CJA 擷取的資料可用來建立以 Excel 為基礎的儀表板和視覺效果，以取得關鍵績效指標 (KPI) 的高階概觀。

- **共用深入分析**：您可以與可能無法直接存取 CJA 的團隊成員或利害關係人共用 Excel 報告和深入分析。

## 概觀影片

>[!IMPORTANT]
>
>此概觀影片以Customer Journey Analytics顯示Report Builder使用者介面。 部分使用者介面和術語有所不同。 否則，使用者體驗會相同。

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

您可以從[Microsoft市集](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview)下載Report Builder。
