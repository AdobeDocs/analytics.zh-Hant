---
title: Analytics 維度相容性
description: Analytics 維度與報表的參考資料。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 維度相容性

本參考文章列出 Reports &amp; Analytics 與 Analysis Workspace 均支援、僅於 Analysis Workspace 中以及僅於 Reports &amp; Analytics 中支援的維度/報表。

請記住，

* 這些並非完整的清單。每個報表套裝可能不一定會有一組指定啟用的產品變數。此外，任何指定的報表套裝可能有任意數量的啟用、停用，或對應至產品變數的自訂變數。我們也已省略訪客屬性和分類，因為它們專屬於各個報表套裝。

* 在一些重疊的案例中，Analytics 工具使用不同的詞彙來描述本質相同的項目，例如：`browserwidth` 和 `browserwidthbucketed`

## Reports &amp; Analytics 與 Analysis Workspace 中同時支援的維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|---|---|
| 目標分析 | targetraw |
| 適用對象 ID | mcaudiences |
| 瀏覽器 | browser |
| 瀏覽器類型 | browsertype |
| 類別 | category |
| 城市 | geocity |
| 色彩深度 | colordepth |
| 連線類型 | connectiontype |
| Cookie 支援 | Cookie |
| 國家 | geocountry |
| 客戶忠誠度 | customerloyalty |
| 自訂轉換 Var | evar1、evar2 等 |
| 自訂分析 Var | prop1、prop2 等 |
| 自訂連結 | customlink |
| 首次購買間隔天數 | daysbeforefirstpurchase |
| 上次購買間隔天數 | dayssincelastpurchase |
| 網域 | filtereddomain |
| 下載連結 | downloadlink |
| 登入頁面 | entrypage |
| 登入頁面原始 | entrypageoriginal |
| 退出連結 | exitlink |
| 首次接觸管道 | firsttouchchannel |
| 首次接觸管道的詳情 | firsttouchchanneldetail |
| Java 已啟用 | javaenabled |
| 語言 | language |
| 上次接觸管道 | lasttouchchannel |
| 上次接觸管道的詳情 | lasttouchchanneldetail |
| 清單變數 | listvariables |
| 行銷管道 | marketingchannel |
| 行動音訊支援 | mobileaudiosupport |
| 行動電信業者 | mobilecarrier |
| 行動色彩深度 | mobilecolordepth |
| 行動 Cookie 支援 | mobilecookiesupport |
| 行動裝置 | mobiledevicename |
| 行動裝置類型 | mobiledevicetype |
| 行動電子郵件的最大長度 | mobileemaillength |
| 行動影像支援 | mobileimagesupport |
| 行動製造商 | mobilemanufacturer |
| 行動作業系統 (已淘汰) | mobileos |
| 行動螢幕高度 | mobilescreenheight |
| 行動螢幕大小 | mobilescreensize |
| 行動螢幕寬度 | mobilescreenwidth |
| 行動瀏覽器 URL 的最大長度 | mobileurllength |
| 行動視訊支援 | mobilevideosupport |
| 監視器解析度 | monitorresolution |
| 作業系統 | operatingsystem |
| 原始反向連結網域 | referringdomainoriginal |
| 頁面 | 頁面 |
| 找不到頁面 | pagesnotfound |
| 產品 | 產品 |
| 反向連結 | referrer |
| 反向連結類型 | referrertype |
| 反向連結網域 | referringdomain |
| 地區 | georegion |
| 回訪頻度 | returnfrequency |
| SC-TnT | tntbase |
| 搜尋引擎 | searchengine |
| 搜尋關鍵字 | searchenginekeyword |
| 搜尋引擎 - 免費 | searchenginenatural |
| 搜尋引擎 - 付費 | searchenginepaid |
| 搜尋關鍵字 - 免費 | searchenginenaturalkeyword |
| 搜尋關鍵字 - 付費 | searchenginepaidkeyword |
| 所有搜尋頁面排名 | searchenginepagerank |
| 伺服器 | server |
| 單頁存取次數 | singlepagevisits |
| 網站區域 | sitesections |
| 每次造訪逗留時間 - 精細 | sitetime |
| 追蹤程式碼 | campaign |
| US DMA | geodma |
| 美國各州 | state |
| 事件之前時間 | timeprior |
| 每次瀏覽逗留時間 - 分段 | timespent |
| 瀏覽深度 | pathlength |
| 訪問次數 | visitnumber |
| 郵遞區號 | zip |

## 僅於 Analysis Workspace 中支援的維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 上午/下午 | timepartampm |
| 瀏覽器高度 - 範圍化 | browserheightbucketed |
| 瀏覽器寬度 - 範圍化 | browserwidthbucketed |
| 日 | daterangeday |
| 日期 | timepartdayofmonth |
| 星期 | dayofweek |
| 星期 | timepartdayofweek |
| 一年當中的第幾天 | timepartdayofyear |
| 上次造訪間隔天數 | dayssincelastvisit |
| 進入自訂分析 | entryprops |
| 進入清單變數 | entrylistvariables |
| 進入伺服器 | entryserver |
| 進入網站區域 | entrysitesections |
| 退出自訂分析 | exitprops |
| 退出清單變數 | exitlistvariables |
| 退出頁面 | exitpage |
| 退出伺服器 | exitserver |
| 退出網站區域 | exitsitesections |
| 點擊深度 | hitdepth |
| 點擊類型 | hittype |
| 小時 | daterangehour |
| 小時 | timeparthourofday |
| 行銷管道詳細資料 | marketingchanneldetail |
| 分鐘 | daterangeminute |
| 行動書籤 的最大長度 | mobilebookmarklength |
| 行動裝置號碼 | mobiledevicenumber |
| 行動 DRM | mobiledrm |
| 行動資訊服務 | mobileinformationservices |
| 行動 Java VM | mobilejavavm |
| 行動郵件裝飾 | mobilemaildecoration |
| 行動網路通訊協定 | mobilenetprotocols |
| 行動即按即說 (Push To Talk) | mobilepushtotalk |
| 月 | daterangemonth |
| 月份 | timepartmonthofyear |
| 作業系統類型 | operatingsystemgroup |
| 付費搜尋 | paidsearch |
| 永久性 Cookie 支援 | persistentcookie |
| 季度 | daterangequarter |
| 季別 | timepartquarterofyear |
| 調查 | surveybase |
| 頁面逗留時間 - 分組 | averagepagetime |
| 頁面逗留時間 - 精細 | pagetimeseconds |
| 追蹤選擇退出原因 | optoutreason |
| 平日/週末 | timepartweekdayweekend |
| 週 | daterangeweek |
| 年 | daterangeyear |

## 僅於 Analysis Workspace 中支援的內容感知維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Activity Map XY | clickmapxy |
| 媒體工作階段 ID | videosessionid |
| Nielsen 存取方法 | nielsenaccmethod |
| Nielsen 應用程式 ID | nielsenappid |
| Nielsen 管道資產 | nielsenchannelasset |
| Nielsen 內容類型 | nielsencontenttype |

## 僅於 Reports &amp; Analytics 中支援的維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 瀏覽器高度 | browserheight |
| 瀏覽器寬度 | browserwidth |
| 每日獨特客戶 | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| JavaScript 版本 | javascriptversion |
| 每月獨特客戶 | monthlyuniquecustomers |
| 每季獨特客戶 | quarterlyuniquecustomers |
| 時區 | timezone |
| 頂級網域 | topleveldomain |
| 訪客所在州 | legacystate |
| 每週獨特客戶 | weeklyuniquecustomers |
| 每年獨特客戶 | yearlyuniquecustomers |

## Reports &amp; Analytics 中預先設定的報表

Reports &amp; Analytics 包含多個預先設定的報表，這些報表不對應至特定維度，或使用維度類別。此處列出這些報表：

* 書籤 URL 長度
* 瀏覽器
* 瀏覽器類型
* 促銷活動轉換漏斗
* 購物車轉換漏斗
* 城市
* 頁面點按次數
* 國家
* 交叉銷售
* 自訂事件漏斗
* 裝飾郵件支援
* 裝置號碼傳輸（開/關）
* 網域
* DRM
* 登入頁面
* 退出頁面
* 流失
* 完整路徑
* ICities
* 資訊服務
* Java 版本
* 語言
* 最長路徑
* 媒體同時觀看者
* 媒體播出時段
* 媒體詳細資料
* 媒體概述
* 螢幕解析度
* 網路通訊協定
* Netscape 外掛程式
* 下一頁
* 下一頁流量
* 作業系統
* 作業系統類型
* 頁面深度
* 頁面摘要
* PathFinder
* 上一頁流量
* 上一頁
* PTT
* 產品轉換漏斗
* 購買轉換漏斗
* 反向連結網域
* 地區
* 重新載入
* 搜尋引擎 - 所有
* 搜尋引擎 - 免費
* 搜尋引擎 - 付費
* 搜尋關鍵字 - 所有
* 搜尋關鍵字 - 免費
* 搜尋關鍵字 - 付費
* 目標活動詳細資料
* 頁面逗留時間
* 時區
* 頂級網域
* 美國 DMA
* 美國州
* 訪問次數
* 訪客首頁

## Reports &amp; Analytics 與 Analysis Workspace 同時支援的內容感知維度

### 影片 (Media Analytics)

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 內容 | video |
| 內容區段 | videosegment |
| 內容類型 | videocontenttype |
| 廣告播放器名稱 | videoadplayername |
| Pod 位置中的廣告 | videoadinpod |
| 掉格 | videoqoedroppedframecountevar |
| 錯誤 | videoqoeerrorcountevar |
| 平均位元速率 | videoqoebitrateaverageevar |
| 位元速率變更 | videoqoebitratechangecountevar |
| 總緩衝期間 | videoqoebuffertimeevar |
| 緩衝事件 | videoqoebuffercountevar |
| 開始時間 | videoqoetimetostartevar |
| 廣告 Pod | videoadpod |
| 媒體路徑 | videopath |
| 廣告 | videoad |
| 內容播放器名稱 | videoplayername |
| 內容頻道 | videochannel |
| 章節 | videochapter |
| 內容名稱 (變數) | videoname |
| 內容長度 (變數) | videolength |
| 廣告名稱 (變數) | videoadname |
| 廣告長度 (變數) | videoadlength |
| 節目 | videoshow |
| 季數 | videoseason |
| 集數 | videoepisode |
| 網路 | videonetwork |
| 節目類型 | videoshowtype |
| 廣告載入 | videoadload |
| MVPD | videomvpd |
| 時段 | videodaypart |
| 廣告商 | videoadadvertiser |
| 行銷活動 ID | videoadcampaign |
| 類型 | videogenre |
| 資料流類型 | videostreamtype |
| 播放器 SDK 錯誤 ID | videoqoeplayersdkerrors |
| 外部錯誤 ID | videoqoeextneralerrors |
| 媒體摘要類型 | videofeedtype |
| 進入媒體路徑 | entryvideopath |
| 退出媒體路徑 | exitvideopath |
| 進入類型 | entryvideogenre |
| 退出類型 | exitvideogenre |
| 進入播放器 SDK 錯誤 ID | entryvideoqoeplayersdkerrors |
| 退出播放器 SDK 錯誤 ID | exitvideoqoeplayersdkerrors |
| 進入外部錯誤 ID | entryvideoqoeextneralerrors |
| 退出外部錯誤 ID | exitvideoqoeextneralerrors |

### Adobe Social

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 詞彙 | socialterm |
| 社交平台/屬性 | socialcontentprovider |
| 作者 | socialauthor |
| 語言 | sociallanguage |
| 緯度/經度 | sociallatlong |
| 資產追蹤代碼 | socialassettrackingcode |
| 擁有的社交屬性 | socialaccountandappids |
| 擁有的貼文 ID | socialownedpostids |
| 擁有的社交定義 | socialinteractiontype |
| 擁有的屬性 ID | socialownedpropertyid |
| 擁有的屬性與應用程式 | socialownedpropertypropertyvsapp |
| 擁有的屬性名稱 | socialownedpropertyname |
| 擁有的定義屬性與貼文 | socialowneddefinitionpropertyvspost |
| 擁有的定義分析類型 | socialowneddefinitioninsighttype |
| 擁有的定義分析值 | socialowneddefinitioninsightvalue |
| 擁有的定義量度 | socialowneddefinitionmetric |
| 資產 | socialmediaid |

### Mobile SDK

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 首次發行日期 | mobileinstalldate |
| 應用程式 ID | mobileappid |
| 啟動次數 | mobilelaunchnumber |
| 首次使用後間隔天數 | mobiledayssincefirstuse |
| 上次使用後間隔天數 | mobiledayssincelastuse |
| 小時 (SDK) | mobilehourofday |
| 星期 (SDK) | mobiledayofweek |
| 作業系統 (SDK) | mobileosenvironment |
| 上次升級後間隔天數 | mobiledayssincelastupgrade |
| 上次升級後啟動次數 | mobilelaunchessincelastupgrade |
| 裝置名稱 (SDK) | mobiledevice |
| 作業系統版本 (SDK) | mobileosversion |
| 主要信標 | mobilebeaconmajor |
| 次要信標 | mobilebeaconminor |
| UUID 信標 | mobilebeaconuuid |
| 鄰近地區信標 | mobilebeaconproximity |
| 位置 (10 公里以內) | latlon1 |
| 位置 (100 公尺以內) | latlon23 |
| 位置 (1 公尺以內) | latlon45 |
| 興趣點名稱 | pointofinterest |
| 至興趣點中心的距離 | pointofinterestdistance |
| 位置準確度 | mobileplaceaccuracy |
| 位置類別 | mobileplacecategory |
| 位置 ID | mobileplaceid |
| 主要進入信標 | entrymobilebeaconmajor |
| 主要退出信標 | exitmobilebeaconmajor |
| 次要進入信標 | entrymobilebeaconminor |
| 次要退出信標 | exitmobilebeaconminor |
| UUID 進入信標 | entrymobilebeaconuuid |
| UUID 退出信標 | exitmobilebeaconuuid |
| 鄰近地區進入信標 | entrymobilebeaconproximity |
| 鄰近地區退出信標 | exitmobilebeaconproximity |

### Adobe Advertising Cloud (AMO)

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| AMO EF ID | amo_ef_id |
| AMO ID | amo_cid |

### Activity Map

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Activity Map 連結 (依地區) | clickmaplinkbyregion |
| Activity Map 地區 | clickmapregion |
| Activity Map 連結 | clickmaplink |
| Activity Map 頁面 | clickmappage |

### Nielsen 整合

如需有關如何實作此整合的詳細資訊，請參閱 [Nielsen 合作關係](https://marketing.adobe.com/resources/help/zh_TW/sc/appmeasurement/hbvideo/nielsen-partnership.html)。

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Nielsen 廣告模型 | nielsenadmodel |
| Nielsen 區段 C | nielsensegmentc |
| Nielsen 區段 B | nielsensegmentb |
| Nielsen 區段 A | nielsensegmenta |
| Nielsen 內容 ID | nielsencontentid |
| Nielsen 資產/節目 | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Nielsen 選擇退出 | nielsenoptout |
| Nielsen 用戶端 ID + VCID | nielsenclientidvcid |
| Nielsen 用戶端 ID | nielsenclientid |
| 進入 Nielsen 選擇退出 | entrynielsenoptout |
| 退出 Nielsen 選擇退出 | exitnielsenoptout |
| 進入 Nielsen 用戶端 ID + VCID | entrynielsenclientidvcid |
| 退出 Nielsen 用戶端 ID + VCID | exitnielsenclientidvcid |
| 進入 Nielsen 用戶端 ID | entrynielsenclientid |
| 退出 Nielsen 用戶端 ID | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 資產 ID | aemassetid |
| 資產來源 | aemassetsource |
| 已點按資產 ID | aemclickedassetid |
| 進入資產 ID | entryaemassetid |
| 退出資產 ID | exitaemassetid |

### Adobe Campaign

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Adobe Campaign 執行的傳送 ID | ac_delivery_internal_name |
