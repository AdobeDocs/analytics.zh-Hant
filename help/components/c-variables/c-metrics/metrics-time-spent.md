---
description: Adobe Analytics提供各種「逗留時間」度量和維度。 瞭解它們是什麼以及如何計算。
title: 逗留時間
topic: Metrics
translation-type: tm+mt
source-git-commit: 8df1fdfb048dd69b4926b7b812ec5dfea4a97b89

---


# [!UICONTROL Time spent]

Various [!UICONTROL 'time spent'] metrics and dimensions are offered across Adobe Analytics products.

## [!UICONTROL 'Time spent'] 公制字

| 量度 | 定義 | 提供於 |
|---|---|---|
| [!UICONTROL Total seconds spent] | 代表訪客與特定維度項目互動的總時間量。包括值的例項和在所有後續點擊中持續的項目。如果是 prop，則會對後續連結事件一併計算逗留時間。 | Analysis Workspace、Reports &amp; Analytics、Report Builder (稱為「總逗留時間」)、Data Warehouse、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit] (秒) | *總逗留秒數/(造訪彈回數)*<br>代表訪客每次造訪時與特定維度項目互動的平均時間量。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Time spent per visitor] (秒) | *總逗留秒數/不重複訪客&#x200B;*<br>代表訪客在訪客期限內 (Cookie 的存留時間長度內期間) 與特定維度項目互動的平均時間量。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Average time spent on site] (秒) | 代表訪客與特定維度項目互動的總時間量，每個序列與維度項目互動。 它不僅僅限於「網站」平均值（如名稱所示）。 如需有關序列的詳細資訊，請參閱「逗留時間計算方式」一節。<br>**注意&#x200B;**：因為在計算中使用不同的分母，此量度與維度項目層級的「每次造訪逗留時間」可能有所差異。 | Analysis Workspace、Reports &amp; Analytics (以分鐘數顯示)、Report Builder (以分鐘數顯示)、Ad Hoc Analysis |
| [!UICONTROL Average time spent on page] | 已停用的量度。<br>反之，我們建議您在需要維度項目的平均時間量時，使用「網站平均逗留時間」。 | Report Builder (請求中包含維度時) |
| [!UICONTROL Total session length]，亦即。 [!UICONTROL Previous session length] | 僅限於行動應用程式 SDK。<br>針對前一個作業，在下一次應用程式啟動時決定。計算量度（以秒為單位）不會在應用程式在背景時計算此量度，只有在使用中時才計算。 這是作業層級量度。<br>範例：我們安裝了應用程式 ABC，啟動後使用了 2 分鐘，然後關閉應用程式。在此工作階段中，系統不會傳送任何相關資料。The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace、Reports &amp; Analytics、Report Builder、Mobile Services UI |
| [!UICONTROL Average session length] (mobile) | *工作階段長度總計/(啟動次數 - 首次啟動)*<br>僅限行動應用程式 SDK。這是作業層級量度。 | Report Builder、Mobile Services UI、Ad Hoc Analysis |

## 「逗留時間」維度

| 維度 | 定義 | 提供於 |
|---|---|---|
| [!UICONTROL Time spent per visit - granular] | 將瀏覽時的總逗留時間去除尾數後的為最接近的秒數，適用於可套用至屬於瀏覽一部分的每一次點擊。這是造訪層級維度。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit - bucketed] | 粒度維度分成9個不同範圍。 這是造訪層級維度。這些範圍包括：<ul><li>少於1分鐘</li><li>1-5 分鐘</li><li>5-10 分鐘</li><li>10-30 分鐘</li><li>30-60 分鐘</li><li>1-2 小時</li><li>2-5 小時</li><li>5-10 小時</li><li>10-15 小時</li></ul>**注意**：時間區間不可高於此設定，因為一次造訪在經過 12 小時的活動後就會到期。 | Analysis Workspace、Reports &amp; Analytics、Report Builder、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - granular] | 每次點擊的總逗留時間，去除尾數後為最接近的秒數。這個項目是點擊層級維度，且包含頁面檢視和連結事件。不同於名稱，此維度並不限於「頁面」。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - bucketed] | 粒度維度分成10個不同範圍；但是，分組維度僅計算頁面檢視（並排除連結事件）。 這是點擊層級維度。 這些範圍包括：<ul><li>少於 15 秒</li><li>15 至 29 秒</li><li>30 至 59 秒</li><li>1到3分鐘</li><li>3至5分鐘</li><li>5至10分鐘</li><li>10到15分鐘</li><li>15到20分鐘</li><li>20到30分鐘</li><li>超過30分鐘</li></ul> | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |

## 「逗留時間」的計算方式

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a &#39;time spent&#39; associated with it.

計算逗留時間時所使用的&#x200B;**分子**&#x200B;均為總逗留秒數。

**分母**&#x200B;在 Adobe Analytics 中不是獨立量度。如果是點擊層級的逗留時間量度，分母則為序列。序列是一組連續點擊，其中的指定變數會包含相同的值 (不論是透過設定、擴散或持續)。「擴散」是指計算逗留時間時，Prop 在個別頁面檢視之間持續沿用的情形 (亦即後續連結事件中使用)。

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* 彈回和退出點擊也會從分母中移除，因為無法得知逗留時間。

## 常見問題解答

**問題 1：所有「逗留時間」量度都能套用至任何維度嗎？**

答：可套用至任何維度的「逗留時間」量度為：

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (秒)

* [!UICONTROL Time spent per visitor] (秒)

* [!UICONTROL Average time spent on site] (秒)

**問題 2：哪一個逗留時間維度最適合搭配其他維度項目來進行劃分？**

答：維 [!UICONTROL Time Spent on Page – granular] 度是點擊層級維度。 使用由其他維度來劃分這個項目會告訴您當劃分維度也存在時點擊持續的秒數。在以下範例中，搜尋詞彙「已分類」與 54 秒、59 秒等點擊時間相關聯，可能表示訪客正在花時間閱讀該詞彙傳回的內容。

![](assets/time-spent1.png)

**第3季：哪些量度適合用於維度[!UICONTROL Time Spent on Page – granular]?**

答：任何量度皆可。此維度會顯示事件發生時確切點擊的逗留時間。較長的逗留時間表示訪客在事件發生的頁面 (點擊) 上停留較長時間。

![](assets/time-spent2.png)

**第4季：與之有[!UICONTROL Average Time Spent on Site]何不同[!UICONTROL Time Spent per Visit]?**

答：差異在於量度中的分母：

* [!UICONTROL Average time spent on site] 使用包含維度項目的序列。

* [!UICONTROL Time spent per visit] 使用瀏覽計數

因此，這些量度可能會在造訪層級產生類似的結果，但是在點擊層級就會有所差異。

**第5季：為什麼劃分總計與[!UICONTROL Average Time Spent on Site]父行項目不符？**

答：因為 [!UICONTROL Average Time Spent on Site] 這取決於維度的未中斷序列，而內部報表在計算這些執行時並不依賴外部報表。

例如，請考慮下列瀏覽。
|hit#|1|2|3|||—|—|—|—||**逗留秒數**|30|100|10||頁&#x200B;**面名稱**|首頁|產品|首頁||**日期**|Jan 1|Jan 1|Jan 1|Jan 1|

當計算首頁的逗留時間時，會是(30+10)/2=20，但依日劃分則會提供(30+10)/1=40，因為當天的單次執行是1月1日。

因此，這些量度可能會在造訪層級產生類似的結果，但是在點擊層級就會有所差異。

## 計算范 [!UICONTROL Time Spent] 例

假設以下幾組伺服器呼叫是針對一次造訪期間內的單一訪客：

| 造訪點擊編號 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **造訪間隔時間 (以秒計算)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **逗留秒數** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **點擊類型** | 頁面 | 連結 | 頁面 | 頁面 | 頁面 | 頁面 | 頁面 |
| **頁面名稱** | 首頁 | - | 產品 | 首頁 | 首頁 (重新載入) | 購物車 | 訂購確認 |
|  |  |  |  |  |  |  |  |
| **prop1** | A（集） | A (擴散) | 未設定 | B (設定) | B (設定) | A(set) | C（設定） |
| **prop1花費的秒數** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | 紅色 (設定) | 紅色 (持續) | (已過期) | 藍色 (設定) | 藍色 (設定) | 藍色 (持續) | 紅色 (設定) |
| **eVar1 花費秒數** | 30 | 50 | - | 10 | 40 | 60 | - |

根據上表，「逗留時間」量度的計算結果如下：

| prop1 | 花費秒數總計 | 每次造訪逗留時間 | 每位訪客逗留時間 | 序列計數 | 網站平均逗留時間 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 未分配時間 | 100 | - | - | - | - |

| eVar1 | 花費秒數總計 | 每次造訪逗留時間 | 每位訪客逗留時間 | 序列計數 | 網站平均逗留時間 |
|---|---|---|---|---|---|
| 紅色 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| 藍色 | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 未分配時間 | 100 | - | - | - | - |

每次造訪逗留時間 (精細)：290
頁面逗留時間 (精細)：10、30、40、50、60、100

可支持此範例的其他附註：

* 所有逗留時間均係根據造訪間隔時間 (於造訪的首次點擊從零開始) 計算而得。

* 花費秒數是指目前點擊時間戳記與下次點擊時間戳記之間的差距。因此，瀏覽的最後點擊（和彈回數）沒有逗留時間。

* 「序列」是一組連續的點擊，其中指定變數包含相同的值（不論是透過設定、前傳或持續）。 例如，prop1「A」有兩個序列：點擊 1 和 2 以及點擊 6。瀏覽的上次點擊值不會開始新序列，因為上次點擊沒有逗留時間。 網站平均逗留時間使用序列作為分母。

   * 僅為了計算逗留時間的目的，prop 會從頁面點擊擴散至後續的連結點擊 (點擊 2 上的 prop1，如上所示)。這得以讓點擊 1 上的 prop1 所設定的值 (「A」) 將逗留時間累積在點擊 2 上。

   * eVar 會將逗留時間累積在 eVar 已設定或持續存在的點擊上。eVar 持續性是由Analytics > 管理員中的 eVar 設定所定義。

