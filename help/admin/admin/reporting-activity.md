---
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
title: 報告活動管理器
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 92%

---

# 報告活動管理器

>[!NOTE]
>
>此功能目前正在進行 Beta 版測試。

[!UICONTROL 報告活動管理器]可讓您查看組織中每個報告套裝的報告容量。它為身為管理員的您提供報告使用量的詳細可見度，並幫助您在尖峰報告期間輕鬆診斷和修正容量問題。

當貴組織達到報告請求容量並遇到報告效能降低時，您現在無需 Adobe 客戶服務或工程部門的介入，就可以自行診斷報告問題。您可以在單一介面中輕鬆管理報告佇列並立即採取行動，以改善使用者體驗。這個工具：

* 可即時通知您跨報告套裝的目前報告容量。
* 提供有關目前報告請求的詳細報告查詢資訊，無論已排入佇列還是進行中。
* 允許您透過優先處理某些報告請求並取消其他報告請求以釋放容量，而最佳化報告佇列。換句話說，您可以即時詢問：這時是否需要這份報告，或者我可以取消它以支持更緊急的報告？

## 存取報告活動管理器

在 Adobe Analytics 中，管理員前往「**[!UICONTROL 管理員]** > **[!UICONTROL 報告活動管理器]**」。

## 權限

若要管理報表活動，您需要Analytics產品管理員權限(位於Adobe Admin Console中)。

![權限](/help/admin/admin/assets/rep-mgr-permission.png)

## 檢視報告佇列

開啟[!UICONTROL 報告活動]管理器總覽頁面時，您將看到已啟用基本報告套裝清單。

![報告佇列](/help/admin/admin/assets/reporting-activity1.png)

| UI 元素 | 說明 |
| --- | --- |
| **[!UICONTROL 報告套裝]** | 您正在監控其報告活動的基本報告套裝。 |
| **[!UICONTROL 虛擬報告套裝]** | 顯示注入到此基本報告套裝所有虛擬報告套裝。虛擬報告套裝因套用了額外層級的篩選和細分，而增加了報告請求的複雜性。來自虛擬報告套裝的所有請求都會合併並歸結為基本報告套裝。<p>例如，如果您有來自 5 個 VRS 的 10 個請求，那麼在基本層級的報告套裝中會有 50 個請求。如此一來，您很快就會達到容量。 |
| **[!UICONTROL 使用容量]** | 以百分比即時顯示使用了多少報告套裝的報告容量。 |
| **[!UICONTROL 狀態]** | 四個可能狀態指標： <ul><li>**紅色 - [!UICONTROL 滿容量]**：報告套裝的報告容量已達上限。(100%) </li><li>**黃色 - [!UICONTROL 接近容量]**：此報告套裝即將達到其容量上限。(90% - 99%)</li><li>**綠色 - [!UICONTROL 良好]**：報告容量仍很多可用。(0% - 89%)</li><li>**灰色 - [!UICONTROL 狀態待定/未啟用]**：報告容量不可用。</li></ul> |

{style=&quot;table-layout:auto&quot;}

### 其他報告活動動作

* 按一下右上角的 **[!UICONTROL 重新整理]** 重新整理結果。
* 按一下報告套裝名稱左側的星號，將此報告套裝加到我的最愛。
* 查看左上角的 **[!UICONTROL 我的最愛]**，顯示您的最愛報告套裝。
* 在搜尋列中按名稱或 ID 搜尋報告套裝。
* 按狀態篩選報告套裝。

## 檢視個別報告套裝的報告活動

按一下要檢視其詳細資料之報告套裝的標題連結。

![報告套裝](/help/admin/admin/assets/indiv-report-ste.png)

### 折線圖

折線圖顯示所選報告套裝在過去 2 小時內的報告活動。

* X 軸顯示過去 2 小時內的報告容量資料。
* Y 軸顯示查詢的平均等待時間，以秒為單位。
* 您可以將滑鼠停留在折線圖上以檢視那一刻的時間點和平均等待時間。

   ![詳細資料](/help/admin/admin/assets/detail.png)

### 篩選器

您可以按應用程式 (參閱下表中的清單)、使用者和專案篩選表格。

![篩選](/help/admin/admin/assets/filter.png)

### 摘要數字

![篩選](/help/admin/admin/assets/summary_numbers.png)

摘要數字顯示以下資訊：

| 摘要數字 | 說明 |
| --- | --- |
| [!UICONTROL 使用者] | 目前傳送報表請求至此報表套裝的使用者人數。 |
| [!UICONTROL 專案] | Workspace 專案、Report Builder 活頁簿等 |
| [!UICONTROL 查詢] | 目前正在執行的查詢數。 |
| [!UICONTROL 平均等待時間] | 所有正在執行之查詢的平均等待時間。 |
| [!UICONTROL 使用容量] | 此報告套裝的目前使用容量。 |

{style=&quot;table-layout:auto&quot;}

### 表格

下方詳細表格顯示報表套裝的詳細資料。

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL 查詢 ID] | 可用於疑難排解。 |
| [!UICONTROL 執行時間] | 查詢已執行多長時間。 |
| [!UICONTROL 等待時間] | 查詢在處理之前已等待多長時間。當有足夠的容量時，一般為「0」。 |
| [!UICONTROL 開始時間] | 查詢開始處理的時間 (管理員的當地時間)。 |
| [!UICONTROL 應用程式] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：區段、計算量度、註解、對象等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>智慧型警報</li></ul> |
| [!UICONTROL 使用者] | 起始查詢的使用者。 |
| [!UICONTROL 專案] | 儲存的 Workspace 專案名稱、API 報告 ID 等。(中繼資料可能因各種應用程式而異。) |
| [!UICONTROL 月邊界] | 請求跨越的每月邊界數。這增加了請求的複雜性。 |
| [!UICONTROL 欄] | Workspace 中的量度和劃分數量，用於測量請求的複雜性。 |
| [!UICONTROL 區段] | 有多少區段套用至此請求。這增加了請求的複雜性。 |
| [!UICONTROL 狀態] | 狀態指示器： <ul><li>**執行中**：請求目前正處理中。</li><li>**擱置中**：請求正等待處理中。</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 取消報告請求

若要取消請求

1. 勾選表格中一個或多個「**[!UICONTROL 查詢 ID]**」左側的方塊，然後按一下底部的「**[!UICONTROL 取消請求]**」。

   您也可以透過檢視詳細資訊來大量取消請求 [!UICONTROL 使用者], [!UICONTROL 專案]，或 [!UICONTROL 應用程式]. 在活動刷新時，對未在隊列中或取消時運行的項目、用戶或應用程式的後續請求仍可能顯示。

1. 在出現的「**[!UICONTROL 取消 x 查詢]**」視窗中，您可以根據需要修改取消訊息。
1. 按一下&#x200B;**[!UICONTROL 「繼續」]**。

   ![取消查詢](/help/admin/admin/assets/cancel-query.png)

例如，Workspace 中的應用程式使用者會在他們的專案中看到以下通知：

![取消使用者通知](/help/admin/admin/assets/cancel-user-facing.png)

## 常見問題集

| 問題 | 回答 |
| --- | --- |
| 我可以購買額外的報告容量嗎？ | 此容量將在不久的未來提供。 |

{style=&quot;table-layout:auto&quot;}