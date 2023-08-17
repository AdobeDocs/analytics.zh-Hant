---
description: Adobe Analytics的一般概觀資訊
title: Adobe Analytics概觀
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: d5a7dfe720cc84b67208e7d30434295caf1e2aac
workflow-type: tm+mt
source-wordcount: '3111'
ht-degree: 32%

---

# Adobe Analytics概觀

Adobe Analytics可讓組織收集資料，並從任何數位客戶互動中獲得可行的深入分析。 透過深入分析、多樣化報表和預測性智慧，組織可獲得所需的深入基礎，為客戶打造更好的體驗。

## 主要優點

以下是Adobe Analytics協助組織獲得重要見解，以便更好地為客戶服務的部分主要方式。

如需Adobe Analytics所提供權益的詳細資訊，請參閱 [Adobe Analytics產品頁面](https://business.adobe.com/products/analytics/adobe-analytics.html).

### 網站分析

Adobe Analytics提供下列複雜的分段和預測性工具，用於分析網站流量：

* [Analysis Workspace中的Ad hoc analysis](/help/analyze/analysis-workspace/home.md)

* [流量分析](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [進階分段](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### 行銷分析

Adobe Analytics可協助組織瞭解客戶與其品牌互動的位置、客戶偏好的管道，以及哪些體驗會引起他們的共鳴。

Adobe Analytics中的下列主要功能提供下列行銷功能：

* 多頻道資料收集

* [離線資料整合](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Analysis Workspace中的Ad hoc analysis](/help/analyze/analysis-workspace/home.md)

### 歸因

歸因可讓組織檢視整個客戶歷程中的不同互動如何影響轉換。 除了提供更傳統的歸因選項（例如線性或首次接觸模型），Adobe Analytics中的Attribution也使用機器學習和進階統計模型來瞭解每次接觸的精確影響。

如需詳細資訊，請參閱 [歸因模型與回顧期間](/help/analyze/analysis-workspace/attribution/models.md).


### 預測性分析

預測性分析使用機器學習和進階統計模型來分析客戶資料、尋找模式，以及預測未來行為，例如流失或轉換的可能性。 它可讓資料分析師運用原本可能被浪費的龐大資料集。

Adobe Analytics中的下列主要功能提供下列預測功能：

* [異常偵測](#anomaly-detection)

* [貢獻分析](#contribution-analysis)

* [智慧型警報](#intelligent-alerts)

## 使用Adobe Analytics的必要條件

使用Adobe Analytics前，您必須具備以下條件：

* 有效的Adobe Analytics授權

  Adobe Analytics需要網站授權。 如需詳細資訊，請聯絡您的Adobe客戶代表。 <!--is this phrased correctly? Is this important? -->

* 支援的瀏覽器

  每個存取Adobe Analytics的使用者必須使用支援的瀏覽器。 如需詳細資訊，請參閱 [Adobe Analytics系統需求](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## 瞭解Analytics介面

Adobe Analytics介麵包含下列主要區域：

### 工作區索引標籤

此 [!UICONTROL 工作區] 索引標籤會顯示Analysis Workspace專案清單。

1. 在Adobe Analytics中，選取 [!UICONTROL **工作區**] 標籤。

   ![工作區索引標籤](assets/landing-all2.png)

如需「 」上可用功能的詳細資訊， [!UICONTROL 工作區] 標籤，請參閱 [Adobe Analytics登陸頁面](/help/analyze/landing.md).

### 「報告」標籤

自 2023 年 12 月 31 日起生效，Adobe 計畫停止支援 Reports &amp; Analytics 及其隨附的報告和功能。 

請改用 [!UICONTROL **報表**] 左側邊欄中的區域 [!UICONTROL **工作區**] 標籤。 如需詳細資訊，請參閱 *瀏覽至「報表」標籤。* 在 [Adobe Analytics登陸頁面](/help/analyze/landing.md).

### 元件標籤

此 [!UICONTROL 元件] 索引標籤包含可幫助您微調和啟用資料分析的功能。

1. 在Adobe Analytics中，選取 [!UICONTROL **元件**] 索引標籤，然後選取 [!UICONTROL **所有元件**].

   ![工作區索引標籤](assets/components-tab.png)

2. 選取下列任何產品功能以進行設定： （視您的許可權而定，可能不會顯示所有功能。）


   | 產品功能 | 功能 | 詳細資訊 |
   |---------|----------|----------|
   | 區段 | Adobe Analytics 可讓您建立、管理、共用功能強大且對象更明確的區段，以及將其套用到使用 Analytics 功能、Adobe Experience Cloud、Adobe Target 和其他整合式 Adobe 產品的報表。 | [Analytics 區段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=zh-Hant) |
   | 計算量度 | 計算量度和進階計算（或衍生）量度是自訂量度，您可以從現有量度建立。  無論行銷人員、產品經理或分析人員，不需變更Analytics實作就能詢問資料相關問題。 | [計算與進階計算 (衍生) 量度](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=en) |
   | 日期範圍 | Analysis Workspace包含使用者在建置分析時可使用的預設日期範圍清單。 此外，您可以建立自訂日期範圍，並供Analysis Workspace中的使用者使用。 | [建立自訂日期範圍](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hant) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | 虛擬報表套裝 |  |  |
   | 警報 | 智慧型警報可提供更細微的警報控制能力，並整合警報系統與異常偵測功能。 | [智慧型警報](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | 目標 | 目標可讓您測量網站績效並追蹤預設目標的進度。建立目標時，您可以選擇希望測量的屬性度量或 eVar，或選擇參照所選度量測量整個網站。 <p>目標是Reports &amp; Analytics的一部分。 進一步了解 Reports &amp; Analytics [生命週期結束通知](https://express.adobe.com/page/6WnF8JK6IRDhf/)。</p> | [目標](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | 行事曆事件 | 對於特定時段的趨勢報表，行事曆事件可讓您以圖形方式顯示事件，並檢視行銷活動或其他事件是否已對您的網站流量、收入或任何其他量度產生影響。 | [日曆事件](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | 附註 | 工作區中的註解讓您能夠有效地將內容相關的資料細微差別和深入解析傳達給您的組織。註解可讓您將行事曆事件和特定的維度和量度連結起來。 | [管理註解](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | 分類集 | 分類設定提供管理分類和規則的單一介面。 <p>分類是將 Analytics 變數資料分類，然後在您產生報表時以不同方式顯示資料的方式。您可以在變數值和與該值相關的中繼資料之間建立關係。 分類可用於大部分的自訂維度，例如追蹤程式碼、prop和eVar。</p> | [分類集概觀](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=zh-Hant) |
   | 位置 | 若要從雲端目的地匯入Adobe Analytics分類資料，您必須先新增並設定要收集分類資料的位置。 您可以建立、編輯或刪除位置。 | [地點管理員](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | 計劃的專案 | 管理已排程專案時，您可以編輯和刪除週期性專案排程；在搜尋列中或使用左側邊欄中的篩選選項搜尋排程；以及依標籤、已核准的排程、擁有者等條件進行篩選。 | [計劃的專案](/help/components/scheduled-projects-manager.md) |
   | 書籤 | 書籤可讓您存取自己最常用的報告。您建立的書籤會新增到 Experience Cloud，並可在 Data Connectors 之類的整合式功能中使用。 <p>書籤是Reports &amp; Analytics的一部分。 進一步了解 Reports &amp; Analytics [生命週期結束通知](https://express.adobe.com/page/6WnF8JK6IRDhf/)。 | [書籤管理器](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | 儀表板 | 控制面板的建立可將度量視覺化，並提供包含資料的互動式分析功能。 按一下控制面板中的專案，可以快速輕鬆地劃分資料區段，以從分析中衍生資訊。 <p>控制面板是Data Workbench的一部分。 深入瞭解Data Workbench [生命週期結束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [控制面板管理員](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | 排程報告 | 管理員層級的使用者可以檢視和管理整個組織的排程報表。 | [排程報表佇列](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | 報表設定 | 這些設定指的舊版Adobe Analytics產品不包括Analysis Workspace及其相關元件。 若要調整Analysis Workspace設定，請前往「元件>偏好設定」。 |  |
   | 偏好設定 | 管理您建立的所有新專案或面板的Analysis Workspace設定及其相關元件。 現有專案和面板不受影響。 | [偏好設定](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### 「工具」索引標籤

「工具」標籤……

1. 在Adobe Analytics中，選取 [!UICONTROL **工具**] 索引標籤，然後選取 [!UICONTROL **所有工具**].

   ![工作區索引標籤](assets/tools-tab.png)

2. 選取下列任一產品功能以進行設定：

   | 產品功能 | 功能 | 詳細資訊 |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse 是指儲存和自訂報表所使用的 Analytics 資料複本，可供您透過篩選資料的方式來執行。  <p>「請求管理員」可讓您檢視或複製請求，以及重新排列請求的優先順序。</p> | [管理 Data Warehouse 請求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map的設計目的，是使用視覺化覆蓋圖為連結活動進行排名，並提供即時分析控制面板，用來監控您網頁的觀眾參與情形。 它可讓您設定不同的檢視，以視覺方式識別客戶活動加速、量化行銷活動，以及就對象需求和行為採取行動。 | [Activity Map 概觀](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=zh-TW) |
   | Recommendations Classic  |  |  |
   | Search&amp;Promote |  |  |
   | 行動服務 |  |  |
   | Analytics儀表板（行動應用程式） |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### 「管理員」標籤

「管理員」標籤……

1. 在Adobe Analytics中，選取 [!UICONTROL **管理員**] 索引標籤，然後選取 [!UICONTROL **所有管理員**].

   ![工作區索引標籤](assets/admin-tab.png)

## 管理員、分析人員和使用者快速入門

典型組織中有3種Adobe Analytics使用者：管理員、分析師和一般使用者。

管理員實作並設定Adobe Analytics；分析師使用Analysis Workspace設定專案並建立分析，而一般使用者則透過建立自己的分析或與分析師合作建立分析，獲得有關其客戶的可操作性深入分析。

展開下列章節，瞭解每位使用者如何開始使用Adobe Analytics。

### 管理員快速入門

Analytics管理員負責選擇最適合其組織的實作方法。

實作Adobe Analytics後，管理員需要執行各種設定工作，以確保分析師和使用者能從Adobe Analytics中獲得完整價值。

#### 決定應收集的資料型別

Adobe Analytics可讓您從多種管道型別收集資料，並將這些資料整合在一起，以提供有意義的即時客戶分析。

以下是一些可收集資料的支援管道：

* 行動電話

* 物聯網

* TV

* 語音助理

* 連線汽車

* 及更多內容（定期新增支援的新管道）

此 [實作方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hant) 您選擇的選項會決定可收集的資料型別。

#### 實施 Adobe Analytics

在您的網站或行動應用程式上實施Adobe Analytics時，有多種實施方法可供使用。

如需各種可用方法的詳細資訊，請參閱 [實作Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hant).

| | 實作方法 |
|---------|---------|
| **網站** | <ul><li>Web SDK擴充功能（建議使用）</li><li>Web SDK</li><li>Analytics 擴充功能</li><li>舊版JavaScript</li></ul> |
| **行動應用程式** | <ul><li>行動SDK擴充功能（建議使用）</li><li>Analytics 擴充功能</li></ul> |

{style="table-layout:auto"}

#### 設定Adobe Analytics

Analytics管理員必須先完成下列工作，才能讓組織中的使用者使用Adobe Analytics：

| 任務 | 預期用途 | 詳細資訊 |
|---------|----------|---------|
| 定義管理員角色 | Adobe Analytics支援各種型別的管理員 | [Adobe Analytics 中的管理員角色](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| 定義許可權 | Analytics管理員需要在Admin Console中指派Adobe Analytics、報表套裝工具和Analytics工具的產品設定檔。 | [Admin Console 中的 Analytics 權限](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=zh-Hant) |
| 設定報表套裝並定義公司的設定 | 報表套裝是Adobe Analytics用來產生報表的獨立資料單位。<p>管理員也可以設定 [虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant) 以進一步劃分資料。</p> | <ul><li>[建立報表套裝](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[公司設定概觀](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| 匯入資料 | Adobe Analytics資料來源可讓您匯入更多重要的線上或離線資料以用於報表。 | [資料來源概觀](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| 使用「分類」將資料分類 | 分類可讓您分類資料，以便更妥善地使用變數，讓您在單一變數中包含更多內容。 | |
| 管理元件 | 使用資料字典和每種元件型別的管理區域，定義您的Analytics實作中可用的元件，以及組織核准的元件。<p>這應是持續活動，以確保您的組織有效使用元件。 </p> | <ul><li>[資料字典概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=zh-Hant)</li><li>[計算量度管理器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[管理區段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hant)</li><li>[建立自訂日期範圍](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hant)</li></ul> |
| 異常偵測和貢獻分析 | | |
| 進階分段 | | |
| 將對象發佈到Audience Manager | | |
| 歸因 | | |
| 報告活動管理員 | | |
| 整合 | 您可以在Adobe Analytics中顯示其他應用程式的資訊。 <p>以下是一些常見的整合：</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">目標分析</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=en">媒體分析</a></li> | |

{style="table-layout:auto"}

### 分析師快速入門

雖然組織中的任何人都能使用Adobe Analytics來獲得關於跨網站和應用程式客戶行為的可操作深入分析，但Adobe Analytics的設計卻是考慮資料分析師。

為了充分利用Adobe Analytics和Analysis Workspace的強大功能，分析師應該熟悉以下主要任務和功能。

| 功能 | 預期用途 | 詳細資訊 |
|---------|----------|---------|
| 在Analysis Workspace中建置和共用專案 | Analysis Workspace 是彈性的瀏覽器工具，可協助您快速建立分析及分享見解。您可以使用拖放式操作介面建立分析、新增視覺效果以生動呈現資料、組織資料集、與組織中的任何人共用及排程專案。<p>資料分析師通常負責在組織內為使用者在Analysis Workspace中建立專案。</p><p>建立專案後，分析人員會將這些專案與 [一般使用者](#end-users)（非分析人員）在其組織中請求資料並幫助他們瞭解如何解譯該資料。</p> | <ul><li>[建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| 歸因 | 分析人員可以在Analysis Workspace中使用各種歸因模型和回顧期間，自訂維度專案獲得成功事件評分的方式。<p>線性歸因模型會將相等的評分歸給每個帶來轉換的接觸點，而「首次接觸」則會將完全的評分歸給第一個接觸點。 有許多其他歸因模型可供使用，包括演演算法模型，此模型會使用統計技術以動態方式決定最佳評分配置。 </p> | [歸因模型與回顧期間](/help/analyze/analysis-workspace/attribution/models.md) |
| 異常偵測 | Analysis Workspace中的統計模型會藉由分析量度並決定上下界限和值的預期範圍，自動尋找資料中的意外趨勢。 當發生意外的尖峰或下降時，系統會在報表中警報。 | [異常偵測概觀](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 貢獻分析 | 使用Analysis Workspace來探索資料中的隱藏模式，說明統計異常並識別跨受眾區段的非預期客戶動作、界外值、量度突升或突降背後的關聯。 | [貢獻分析概觀](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| 智慧型警報 | 根據資料異常和以單一警報擷取多個量度的「棧疊」警報，建立和管理警報。 | [智慧型警報概觀](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| 資料匯出 | Data Warehouse和資料摘要可讓您將資料匯出至各種雲端目的地，例如Google Cloud Platform、Azure RBAC、Azure SAS和Amazon S3。 | [Analytics 轉存指南](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=zh-Hant) |
| Activity Map | Activity Map 是一種 Adobe Analytics 應用程式，專門設計來使用視覺化覆蓋圖為連結活動進行排名，並提供即時分析儀表板來監控網頁的觀眾參與情形。<p>Activity Map 可讓您設定不同的檢視，以視覺方式識別客戶活動加速、量化行銷活動，以及就觀眾需求和行為採取行動。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html) |
| Report Builder |  Report Builder 是 Microsoft Excel 的增益集。Report Builder 能讓您根據插入 Excel 工作表中的 Adobe Analytics 資料，建置自訂請求。這些請求可動態參考工作表中的儲存格，而您可以更新及自訂 Report Builder 展示資料的方式。 | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### 使用者快速入門

不是專業分析師的一般使用者可以與組織內的分析師合作，以運用Adobe Analytics和Analysis Workspace的完整功能，也可以學習Analysis Workspace的基本知識，以開始獲得關於其客戶的可操作見解。

#### 與分析人員合作

通常，組織中有興趣進一步瞭解不同網站上的客戶行為的使用者不是專業的分析師。

理想情況下，這些使用者應該使用 [分析人員](#analysts) 在組織內執行下列作業：

1. 向分析人員說明他們希望瞭解的客戶資訊，以定義分析需求。

1. 檢閱分析以確保其符合目標。

1. 討論從分析中取得的資料。

1. 視需要在一段時間內修改分析。

#### 在Analysis Workspace中建立分析

您不需要是資料分析人員，就能從Adobe Analytics獲得可操作的深入分析。

有些使用者可能會發現與資料分析人員合作來在Analysis Workspace中設定專案及說明如何解譯資料會很有幫助，如中所述 [與分析人員合作](#work-with-analysts)；其他使用者可能樂於建立專案及自行解譯資料。

Analysis Workspace 可讓您快速建置分析以收集深入見解，然後與其他人分享這些深入見解。透過拖放瀏覽器介面，您可以建立分析、新增視覺效果以生動呈現資料、組織資料集，以及與組織中您選擇的任何人共用和排程專案。

如需如何在Analysis Workspace中建立分析的相關資訊，請參閱 [Analysis Workspace概觀](/help/analyze/analysis-workspace/home.md).

### 開發人員快速入門

[使用 Analytics API 就能直接呼叫 Adobe 的伺服器，執行幾乎所有使用者介面中可以執行的動作。](https://developer.adobe.com/analytics-apis/docs/2.0/)

您可以建立報告來探索、取得深入分析，或是回答資料相關的重要問題。您也可以管理 Adobe Analytics 的元件，例如建立區段或計算量度。

## 影片概述

若要瞭解Adobe Analytics基本概念，請參閱此 *Adobe Analytics簡介 — 技能培養網路研討會* 視訊。 影片中介紹了如何擷取資料、如何將資料發送到 Adobe Analytics，以及您可以在 Adobe Analytics 中使用哪些視覺化功能的基礎知識。影片為您建立、部署、收集和解譯資料奠定基礎，好讓您根據收集的資料提供可操作的深入分析和建議。

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

若要了解關於使用哪種工具的問題，請參閱「[我應該使用哪種 Adobe Analytics 工具？](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html)」。

## 進一步進行Customer Journey Analytics

Customer Journey Analytics 是 Adobe 的新一代 Analytics 解決方案，讓您可搭配 Adobe Experience Platform 的資料運用 Analysis Workspace 的強大功能。這能協助您劃分、篩選、查詢及視覺化多年累積的資料，並結合 Platform 掌握各種資料綱要和類型的能力。

以下是Customer Journey Analytics優於Adobe Analytics之處：

* **不限數量的變數和事件**：eVar、prop 和事件的概念已不存在。資料主要聚焦於維度和量度。資料集可以有不限數量的不重複維度和量度。

* **不限數量的唯一值**：Adobe Experience Platform 不受任何獨特限制。

* **變更歷史資料**：您可以使用 Adobe Experience Platform 移除或修正資料。

* **跨報告套裝資料**：可在 Platform 中結合來自多個資料集的現有實作。

如需詳細資訊，請參閱 [Customer Journey Analytics概觀](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant).

