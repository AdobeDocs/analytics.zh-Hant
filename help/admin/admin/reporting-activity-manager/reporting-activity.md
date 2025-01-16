---
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
title: 報告活動管理器
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 14%

---

# 在報告活動管理器中檢視報告活動

[!UICONTROL 報告活動管理員]可讓管理員在尖峰報告期間快速診斷和修正報告容量問題。

如需報告活動管理員的詳細資訊，包括主要權益和許可權要求，請參閱[報告活動管理員概觀](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)。

## 檢視所有報表套裝的報表活動 {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="連線"
>abstract="此表顯示您有權管理報告活動的連線。表格的每一欄中都提供了有關每個連線的資訊。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="連線"
>abstract="此表顯示您有權管理報告活動的連線。表格的每一欄中都提供了有關每個連線的資訊。"

<!-- markdownlint-enable MD034 -->

1. 在Adobe Analytics中，移至&#x200B;**[!UICONTROL 管理員]** > **[!UICONTROL 報告活動管理員]**。

   系統會顯示已啟用基本報表套裝的清單。

   ![報告佇列](assets/reporting-activity1.png)

1. （可選）您可以搜尋或篩選報表套裝清單：

   * 使用搜尋欄位來搜尋特定報表套裝。 開始輸入報表套裝名稱或ID，並依照您輸入的內容輸入報表套裝更新清單。

   * 選取&#x200B;[!UICONTROL **篩選器**]&#x200B;圖示![篩選器圖示](assets/filter-icon.png)以展開篩選器選項清單。 您可以依&#x200B;[!UICONTROL **我的最愛**]&#x200B;或&#x200B;[!UICONTROL **狀態**]&#x200B;篩選。

     若要將報表套裝標示為我的最愛，請選取報表套裝名稱左側的星號圖示。

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. 檢視每個報表套裝的使用率資訊。 表格中顯示的資料代表上次載入頁面時報表套裝的報告活動。

   可使用下列欄:

   | UI 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 報告套裝]** | 您正在監控其報告活動的基本報告套裝。 |
   | **[!UICONTROL 虛擬報表套裝]** | 顯示注入到此基本報告套裝所有虛擬報告套裝。虛擬報告套裝因套用了額外層級的篩選和細分，而增加了報告請求的複雜性。來自虛擬報表套裝的所有請求都會合併至基本報表套裝。 |
   | **[!UICONTROL 容量使用率]** | 報告套裝即時使用的報告容量百分比。 <p>**注意**&#x200B;使用容量為100%並不表示您應該立即開始取消報告要求。 如果平均等待時間合理，則100%使用容量可能狀況良好。 另一方面，如果排入佇列的請求數量也在增加，則100%的使用容量可能會造成問題。</p> |
   | **[!UICONTROL 已排入佇列的請求]** | 等待處理的要求數目。<!-- ??? --> |
   | **[!UICONTROL 佇列等待時間]** | 開始處理要求前的平均等待時間。<!-- ???? --> |
   | **[!UICONTROL 狀態]** | 可能的狀態包括： <ul><li>[!UICONTROL **作用中**] （藍色）：報告已在過去2小時內於報告套裝上執行。 表格中顯示的資料代表上次載入頁面時報表套裝的報告容量。</li><li>[!UICONTROL **非使用中**] （灰色）：過去2小時內未對報表套裝執行任何報表，因此未顯示報表套裝的資料。</li></ul> |

   {style="table-layout:auto"}

## 檢視單一報表套裝的報告活動

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **管理員**] > [!UICONTROL **報告活動管理員**]。

1. 選取您要檢視詳細資料之報表套裝的連結標題。

   系統會顯示您所選報表套裝的報表活動資料。

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. （選用）當連線首次載入報表活動管理器時，顯示的資料代表目前的使用量度。 若要在初始載入後檢視更新的量度，請選取&#x200B;[!UICONTROL **重新整理**]&#x200B;按鈕，以手動重新整理頁面。

1. 使用可用的圖表和表格來瞭解報表套裝中的報表活動。

   * [檢檢視表](#view-graphs)

   * [檢視表格](#view-table)

### 檢檢視表

下列圖表可協助您更清楚瞭解報表套裝中發生的活動。

如果看不到圖形，請選取&#x200B;[!UICONTROL **顯示圖形**]&#x200B;按鈕。

#### 使用率圖表 {#utilization}

「使用率」圖表顯示所選報表套裝在過去2小時內的報表使用率。

暫留在圖表上可檢視該分鐘使用容量百分比最高的時間點。

* **X軸**：過去2小時內的報告使用容量。
* **Y軸**：報告使用量百分比（以分鐘計）。

  ![使用率圖表](assets/utilization-graph.png)

#### 不同使用者圖表

「不同使用者」圖表顯示所選報表套裝在過去2小時內的報表活動。

將滑鼠指標暫留在圖表上可檢視該分鐘最大使用者數最高的時間點。

* **X軸**：過去2小時的報告活動。
* **Y軸**：提出報告要求的使用者人數（以分鐘計）。

  ![不同的使用者圖表](assets/distinct-users-graph.png)

#### 請求圖表

請求圖表顯示所選報表套裝在過去2小時內處理和佇列的請求數。

將游標暫留在圖表上可檢視該分鐘最大請求數最高的時間點。

* **X軸**：過去2小時時間範圍內已處理和已完成的要求數目。
* **Y軸**：按分鐘計算的已處理要求（綠色）和已排入佇列的要求（紫色）數目。

  ![不同的使用者圖表](assets/requests-graph.png)

#### 佇列圖表

「佇列」圖表顯示所選報表套裝在過去2小時內報告要求的平均佇列等待時間（以秒為單位）。

將游標停留在圖表上可檢視該分鐘最大平均等待時間最高的時間點。

* **X軸**：過去2小時時間範圍內報告要求的平均佇列等待時間。
* **Y軸**：平均等待時間（秒）。

  ![不同的使用者圖表](assets/queueing-graph.png)

### 檢視表格 {#view-table}

檢視表格時，請考量下列事項：

* 您可以在資料表頂端選擇下列任何索引標籤來檢視資料： [!UICONTROL **要求**]、[!UICONTROL **使用者**]、[!UICONTROL **專案**]&#x200B;或&#x200B;[!UICONTROL **應用程式**]。

* 您可以搜尋或篩選連線清單：

   * 使用搜尋欄位來搜尋特定連線。 開始輸入連線名稱或ID，並在您輸入時輸入連線更新清單。

   * 選取&#x200B;[!UICONTROL **篩選器**]&#x200B;圖示![篩選器圖示](assets/filter-icon.png)以展開篩選器選項清單。 您可以依&#x200B;[!UICONTROL **狀態**]、[!UICONTROL **複雜性**]、[!UICONTROL **應用程式**]、[!UICONTROL **使用者**]&#x200B;或&#x200B;[!UICONTROL **專案**]&#x200B;篩選。

   * 您可以選取&#x200B;[!UICONTROL **隱藏圖形**]&#x200B;以僅顯示表格。

![資料表索引標籤](assets/report-activity-tabs.png)

#### 依請求檢視資料

當您選取&#x200B;[!UICONTROL **要求**]&#x200B;索引標籤時，表格中有下列資料行：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **要求ID**] | 可用於疑難排解的唯一ID。 若要複製識別碼，請選取要求，然後選取&#x200B;[!UICONTROL **複製要求ID**]&#x200B;選項。 |
| [!UICONTROL **時間執行**] | 要求已執行多久。 |
| [!UICONTROL **開始時間**] | 要求開始處理的時間（根據管理員的當地時間）。 |
| [!UICONTROL **等待時間**] | 請求在處理之前已等待多長時間。 當有足夠的容量時，此值通常為「0」。 |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：細分群體、計算量度、註解、客群等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>警報</li><li>與任何人共用連結</li><li>查詢Analytics報表引擎的任何其他應用程式</li></ul> |
| [!UICONTROL **使用者**] | 起始請求的使用者。 <p>**注意：**&#x200B;如果此資料行的值為&#x200B;[!UICONTROL **無法辨識**]，這表示使用者所在的登入公司您沒有系統管理許可權。</p> |
| [!UICONTROL **專案**] | 儲存的 Workspace 專案名稱、API 報告 ID 等。(中繼資料可能因各種應用程式而異。) |
| [!UICONTROL **狀態**] | 狀態指示器： <ul><li>**執行中**：請求目前正處理中。</li><li>**擱置中**：請求正等待處理中。</li></ul> |
| [!UICONTROL **複雜性**] | 並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。 <p>可能的值包括：</p> <ul><li>[!UICONTROL **低**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **高**]</li></ul>此值會受下列欄中的值影響：<ul><li>[!UICONTROL **個月邊界**]</li><li>[!UICONTROL **欄**]</li><li>[!UICONTROL **區段**]</li></ul> |
| [!UICONTROL **個月邊界**] | 請求中包含的月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **欄**] | 請求中的量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **區段**] | 套用至請求的區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依使用者檢視資料

當您選取&#x200B;[!UICONTROL **使用者**]&#x200B;索引標籤時，表格中有下列資料行：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **使用者**] | 起始請求的使用者。 如果此資料行的值為&#x200B;[!UICONTROL **無法辨識**]，這表示使用者所在的登入公司您沒有系統管理許可權。 |
| [!UICONTROL **要求數目**] | 使用者起始的請求數。 |
| [!UICONTROL **專案數目**] | 與使用者相關聯的專案數。<!-- ??? --> |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：細分群體、計算量度、註解、客群等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>警報</li><li>與任何人共用連結</li><li>查詢Analytics報表引擎的任何其他應用程式</li></ul> |
| [!UICONTROL **平均複雜性**] | 使用者起始的要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p><ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均資料行**]</li><li>[!UICONTROL **平均區段**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均資料行**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依專案檢視資料

當您選取&#x200B;[!UICONTROL **專案**]&#x200B;索引標籤時，表格中有下列資料行：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **專案**] | 起始要求的專案。 |
| [!UICONTROL **要求數目**] | 與專案相關聯的請求數。 |
| [!UICONTROL **使用者數目**] | 與專案相關聯的使用者人數。<!-- ??? --> |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：細分群體、計算量度、註解、客群等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>警報</li><li>與任何人共用連結</li><li>查詢Analytics報表引擎的任何其他應用程式</li></ul> |
| [!UICONTROL **平均複雜性**] | 專案中包含之要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p><ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均資料行**]</li><li>[!UICONTROL **平均區段**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均資料行**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依應用程式檢視資料

當您選取&#x200B;[!UICONTROL **應用程式**]&#x200B;索引標籤時，表格中有下列資料行：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **應用程式**] | 起始要求的應用程式。 |
| [!UICONTROL **要求數目**] | 與應用程式相關聯的要求數目。 |
| [!UICONTROL **使用者數目**] | 與應用程式相關聯的使用者數目。<!--???--> |
| [!UICONTROL **專案數目**] | 與應用程式相關聯的專案數目。<!--???--> |
| [!UICONTROL **平均複雜性**] | 與應用程式相關之要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p>此欄中的值以分數為基礎，分數由下列欄中的值決定：<ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均資料行**]</li><li>[!UICONTROL **平均區段**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均資料行**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

<!--

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
|  |  |

{style="table-layout:auto"}

-->