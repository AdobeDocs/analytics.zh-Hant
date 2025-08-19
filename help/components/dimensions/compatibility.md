---
title: Analytics 維度相容性
description: Analytics 維度與報表的參考資料。
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 60%

---

# Analytics 維度相容性

此頁面列出其個別Analytics功能中支援的[維度](overview.md)。

>[!NOTE]
>
>此清單中省略了自訂變數名稱、分類和訪客屬性。這些維度項目是個別報表套裝專用。

## Analysis Workspace支援的維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|---|---|
| 目標分析 | `targetraw` |
| 適用客群 ID | `mcaudiences` |
| [瀏覽器](browser.md) | `browser` |
| [瀏覽器類型](browser-type.md) | `browsertype` |
| [類別](category.md) | `category` |
| [城市](cities.md) | `geocity` |
| [色彩深度](color-depth.md) | `colordepth` |
| [連線類型](connection-type.md) | `connectiontype` |
| [Cookie支援](cookie-support.md) | `cookie` |
| [國家/地區](countries.md) | `geocountry` |
| [客戶忠誠度](customer-loyalty.md) | `customerloyalty` |
| [自訂轉換Var](evar.md) | `evar1`、`evar2` 等 |
| [Custom Insight Vars](prop.md) | `prop1`、`prop2` 等 |
| [自訂連結](custom-link.md) | `customlink` |
| [首次購買間隔天數](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [上次購買間隔天數](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [網域](domain.md) | `filtereddomain` |
| [下載連結](download-link.md) | `downloadlink` |
| [登入頁面](entry-dimensions.md) | `entrypage` |
| [原始登入頁面](entry-dimensions.md) | `entrypageoriginal` |
| [退出連結](exit-link.md) | `exitlink` |
| [首次接觸管道](first-touch-channel.md) | `firsttouchchannel` |
| [首次接觸管道詳細資料](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java 已啟用](java-enabled.md) | `javaenabled` |
| [語言](language.md) | `language` |
| [上次接觸管道](last-touch-channel.md) | `lasttouchchannel` |
| [上次接觸管道詳細資料](last-touch-detail.md) | `lasttouchchanneldetail` |
| 清單變數 | `listvariables` |
| [行銷管道](marketing-channel.md) | `marketingchannel` |
| [行動音訊支援](mobile-dimensions.md) | `mobileaudiosupport` |
| [行動電信業者](mobile-dimensions.md) | `mobilecarrier` |
| [行動色彩深度](mobile-dimensions.md) | `mobilecolordepth` |
| [行動Cookie支援](mobile-dimensions.md) | `mobilecookiesupport` |
| [行動裝置](mobile-dimensions.md) | `mobiledevicename` |
| [行動裝置型別](mobile-dimensions.md) | `mobiledevicetype` |
| [行動電子郵件的最大長度](mobile-dimensions.md) | `mobileemaillength` |
| [行動影像支援](mobile-dimensions.md) | `mobileimagesupport` |
| [行動製造商](mobile-dimensions.md) | `mobilemanufacturer` |
| [行動作業系統（已棄用）](mobile-dimensions.md) | `mobileos` |
| [行動熒幕高度](mobile-dimensions.md) | `mobilescreenheight` |
| [行動熒幕大小](mobile-dimensions.md) | `mobilescreensize` |
| [行動熒幕寬度](mobile-dimensions.md) | `mobilescreenwidth` |
| [行動瀏覽器URL的最大長度](mobile-dimensions.md) | `mobileurllength` |
| [行動視訊支援](mobile-dimensions.md) | `mobilevideosupport` |
| [監視器解析度](monitor-resolution.md) | `monitorresolution` |
| [作業系統](operating-systems.md) | `operatingsystem` |
| [原始反向連結網域](original-referring-domain.md) | `referringdomainoriginal` |
| [頁面](page.md) | `page` |
| [找不到頁面](pages-not-found.md) | `pagesnotfound` |
| [產品](product.md) | `product` |
| [反向連結](referrer.md) | `referrer` |
| [反向連結類型](referrer-type.md) | `referrertype` |
| [反向連結網域](referring-domain.md) | `referringdomain` |
| [地區](regions.md) | `georegion` |
| [回訪頻率](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [搜尋引擎](search-engine.md) | `searchengine` |
| [搜尋關鍵字](search-keyword.md) | `searchenginekeyword` |
| [搜尋引擎 — 免費](search-engine.md) | `searchenginenatural` |
| [搜尋引擎 — 付費](search-engine.md) | `searchenginepaid` |
| [搜尋關鍵字 — 免費](search-keyword.md) | `searchenginenaturalkeyword` |
| [搜尋關鍵字 — 付費](search-keyword.md) | `searchenginepaidkeyword` |
| [所有搜尋頁面排名](all-search-page-rank.md) | `searchenginepagerank` |
| [伺服器](server.md) | `server` |
| [單頁存取次數](single-page-visits.md) | `singlepagevisits` |
| [網站區域](site-section.md) | `sitesections` |
| [每次造訪逗留時間 — 精細](time-spent-per-visit.md) | `sitetime` |
| [追蹤代碼](tracking-code.md) | `campaign` |
| [US DMA](us-dma.md) | `geodma` |
| [美國州](us-states.md) | `state` |
| [事件之前時間](time-prior-to-event.md) | `timeprior` |
| [每次造訪逗留時間 — 分段](time-spent-per-visit.md) | `timespent` |
| [造訪深度](visit-depth.md) | `pathlength` |
| [訪問次數](visit-number.md) | `visitnumber` |
| [郵遞區號](zip-code.md) | `zip` |
| [上午/下午](am-pm.md) | `timepartampm` |
| [瀏覽器高度 — 分段](browser-height.md) | `browserheightbucketed` |
| [瀏覽器寬度 — 分段](browser-width.md) | `browserwidthbucketed` |
| [日](day.md) | `daterangeday` |
| [幾月幾號](day-of-month.md) | `timepartdayofmonth` |
| [星期幾](day-of-week.md) | `dayofweek` |
| [星期幾](day-of-week.md) | `timepartdayofweek` |
| [一年當中的第幾天](day-of-year.md) | `timepartdayofyear` |
| [上次造訪間隔天數](days-since-last-visit.md) | `dayssincelastvisit` |
| [專案自訂分析](entry-dimensions.md) | `entryprops` |
| [專案清單變數](entry-dimensions.md) | `entrylistvariables` |
| [專案伺服器](entry-dimensions.md) | `entryserver` |
| [進入網站區域](entry-dimensions.md) | `entrysitesections` |
| [退出自訂分析](exit-dimensions.md) | `exitprops` |
| [退出清單變數](exit-dimensions.md) | `exitlistvariables` |
| [退出頁面](exit-dimensions.md) | `exitpage` |
| [退出伺服器](exit-dimensions.md) | `exitserver` |
| [退出網站區域](exit-dimensions.md) | `exitsitesections` |
| [點選深度](hit-depth.md) | `hitdepth` |
| [點擊類型](hit-type.md) | `hittype` |
| [小時](hour.md) | `daterangehour` |
| [當天幾點](hour-of-day.md) | `timeparthourofday` |
| [行銷管道詳細資料](marketing-detail.md) | `marketingchanneldetail` |
| [分鐘](minute.md) | `daterangeminute` |
| [行動書籤的最大長度](mobile-dimensions.md) | `mobilebookmarklength` |
| [行動裝置號碼](mobile-dimensions.md) | `mobiledevicenumber` |
| [行動DRM](mobile-dimensions.md) | `mobiledrm` |
| [行動資訊服務](mobile-dimensions.md) | `mobileinformationservices` |
| [行動Java VM](mobile-dimensions.md) | `mobilejavavm` |
| [行動郵件裝飾](mobile-dimensions.md) | `mobilemaildecoration` |
| [行動網路通訊協定](mobile-dimensions.md) | `mobilenetprotocols` |
| [行動即按即說](mobile-dimensions.md) | `mobilepushtotalk` |
| [月](month.md) | `daterangemonth` |
| [一年中的月份](month-of-year.md) | `timepartmonthofyear` |
| [作業系統類型](operating-system-types.md) | `operatingsystemgroup` |
| [付費搜尋](paid-search.md) | `paidsearch` |
| [永久Cookie支援](persistent-cookie-support.md) | `persistentcookie` |
| [季](quarter.md) | `daterangequarter` |
| [一年中的季度](quarter-of-year.md) | `timepartquarterofyear` |
| 調查 | `surveybase` |
| [頁面逗留時間 — 分段](time-spent-on-page.md) | `averagepagetime` |
| [頁面逗留時間 — 精細](time-spent-on-page.md) | `pagetimeseconds` |
| [追蹤選擇退出原因](tracking-opt-out-reason.md) | `optoutreason` |
| [工作日/週末](weekday-weekend.md) | `timepartweekdayweekend` |
| [週](week.md) | `daterangeweek` |
| [年](year.md) | `daterangeyear` |

## 僅於 Analysis Workspace 中支援的內容感知維度

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| 媒體工作階段 ID | `videosessionid` |
| Nielsen 存取方法 | `nielsenaccmethod` |
| Nielsen 應用程式 ID | `nielsenappid` |
| Nielsen 管道資產 | `nielsenchannelasset` |
| Nielsen 內容類型 | `nielsencontenttype` |

## Analysis Workspace支援的內容感知維度

### 視訊（串流媒體服務）

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| [內容](sm-core.md) | `video` |
| [內容區段](sm-core.md) | `videosegment` |
| [內容類型](sm-core.md) | `videocontenttype` |
| [廣告播放器名稱](sm-ads.md) | `videoadplayername` |
| [Pod 位置中的廣告](sm-ads.md) | `videoadinpod` |
| [掉格](sm-quality.md) | `videoqoedroppedframecountevar` |
| [錯誤](sm-quality.md) | `videoqoeerrorcountevar` |
| [平均位元速率](sm-quality.md) | `videoqoebitrateaverageevar` |
| [位元速率變更](sm-quality.md) | `videoqoebitratechangecountevar` |
| [總緩衝期間](sm-quality.md) | `videoqoebuffertimeevar` |
| [緩衝事件](sm-quality.md) | `videoqoebuffercountevar` |
| [開始時間](sm-quality.md) | `videoqoetimetostartevar` |
| [廣告 Pod](sm-ads.md) | `videoadpod` |
| [媒體路徑](sm-core.md) | `videopath` |
| [廣告](sm-ads.md) | `videoad` |
| [內容播放器名稱](sm-core.md) | `videoplayername` |
| [內容頻道](sm-core.md) | `videochannel` |
| [章節](sm-chapters.md) | `videochapter` |
| [內容名稱 (變數)](sm-core.md) | `videoname` |
| [內容長度 (變數)](sm-core.md) | `videolength` |
| [廣告名稱（變數）](sm-ads.md) | `videoadname` |
| [廣告長度（變數）](sm-ads.md) | `videoadlength` |
| [Show](sm-video-metadata.md) | `videoshow` |
| [季數](sm-video-metadata.md) | `videoseason` |
| [集數](sm-video-metadata.md) | `videoepisode` |
| [網路](sm-video-metadata.md) | `videonetwork` |
| [節目類型](sm-video-metadata.md) | `videoshowtype` |
| [個廣告載入](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [時段](sm-video-metadata.md) | `videodaypart` |
| [廣告商](sm-ads.md) | `videoadadvertiser` |
| [行銷活動 ID](sm-ads.md) | `videoadcampaign` |
| [類型](sm-video-metadata.md) | `videogenre` |
| [資料流類型](sm-core.md) | `videostreamtype` |
| [播放器 SDK 錯誤 ID](sm-quality.md) | `videoqoeplayersdkerrors` |
| [外部錯誤 ID](sm-quality.md) | `videoqoeextneralerrors` |
| [媒體摘要類型](sm-video-metadata.md) | `videofeedtype` |
| [進入媒體路徑](entry-dimensions.md) | `entryvideopath` |
| [退出媒體路徑](exit-dimensions.md) | `exitvideopath` |
| [專案型別](entry-dimensions.md) | `entryvideogenre` |
| [退出型別](exit-dimensions.md) | `exitvideogenre` |
| [進入播放器SDK錯誤ID](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [退出播放器SDK錯誤ID](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [專案外部錯誤ID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [退出外部錯誤ID](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social已淘汰。

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 詞彙 | `socialterm` |
| 社交平台/屬性 | `socialcontentprovider` |
| 作者 | `socialauthor` |
| 語言 | `sociallanguage` |
| 緯度/經度 | `sociallatlong` |
| 資產追蹤代碼 | `socialassettrackingcode` |
| 擁有的社交屬性 | `socialaccountandappids` |
| 擁有的貼文 ID | `socialownedpostids` |
| 擁有的社交定義 | `socialinteractiontype` |
| 擁有的屬性 ID | `socialownedpropertyid` |
| 擁有的屬性與應用程式 | `socialownedpropertypropertyvsapp` |
| 擁有的屬性名稱 | `socialownedpropertyname` |
| 擁有的定義屬性與貼文 | `socialowneddefinitionpropertyvspost` |
| 擁有的定義分析類型 | `socialowneddefinitioninsighttype` |
| 擁有的定義分析值 | `socialowneddefinitioninsightvalue` |
| 擁有的定義量度 | `socialowneddefinitionmetric` |
| 資產 | `socialmediaid` |

### Mobile SDK

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| [首次啟動日期](lifecycle-dimensions.md) | `mobileinstalldate` |
| [應用程式ID](lifecycle-dimensions.md) | `mobileappid` |
| [啟動次數](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [首次使用後間隔天數](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [上次使用後間隔天數](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [小時(SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [星期(SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [作業系統(SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [上次升級後間隔天數](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [上次升級後啟動次數](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [裝置名稱(SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [作業系統版本(SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [主要信標](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [次要信標](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [信標UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [鄰近地區信標](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [位置 (10 公里以內)](lifecycle-dimensions.md) | `latlon1` |
| [位置 (100 公尺以內)](lifecycle-dimensions.md) | `latlon23` |
| [位置 (1 公尺以內)](lifecycle-dimensions.md) | `latlon45` |
| [興趣點名稱](lifecycle-dimensions.md) | `pointofinterest` |
| [至興趣點中心的距離](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [位置準確度](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [放置類別](lifecycle-dimensions.md) | `mobileplacecategory` |
| [地標ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [主要進入信標](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [主要退出信標](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [次要進入信標](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [次要退出信標](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [進入信標UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [退出信標UUID](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [鄰近地區進入信標](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [鄰近地區退出信標](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| AMO ID | `amo_cid` |

### Activity Map

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| [各地區的Activity Map連結](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Activity Map地區](activity-map-region.md) | `clickmapregion` |
| [Activity Map連結](activity-map-link.md) | `clickmaplink` |
| [Activity Map頁面](activity-map-page.md) | `clickmappage` |

### Nielsen 整合

如需有關如何實作此整合的詳細資訊，請參閱Adobe Exchange上的[Nielsen擴充功能](https://exchange.adobe.com/apps/ec/101361)。

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Nielsen 廣告模型 | `nielsenadmodel` |
| Nielsen 區段 C | `nielsensegmentc` |
| Nielsen 區段 B | `nielsensegmentb` |
| Nielsen 區段 A | `nielsensegmenta` |
| Nielsen 內容 ID | `nielsencontentid` |
| Nielsen資產/計畫 | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Nielsen 選擇退出 | `nielsenoptout` |
| Nielsen 用戶端 ID + VCID | `nielsenclientidvcid` |
| Nielsen 用戶端 ID | `nielsenclientid` |
| 進入 Nielsen 選擇退出 | `entrynielsenoptout` |
| 退出 Nielsen 選擇退出 | `exitnielsenoptout` |
| 進入 Nielsen 用戶端 ID + VCID | `entrynielsenclientidvcid` |
| 退出 Nielsen 用戶端 ID + VCID | `exitnielsenclientidvcid` |
| 進入 Nielsen 用戶端 ID | `entrynielsenclientid` |
| 退出 Nielsen 用戶端 ID | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| 資產 ID | `aemassetid` |
| 資產來源 | `aemassetsource` |
| 已點按資產 ID | `aemclickedassetid` |
| 進入資產 ID | `entryaemassetid` |
| 退出資產 ID | `exitaemassetid` |

### Adobe Campaign

| 維度名稱 (顯示在 Analytics UI 中) | 維度 ID (用於 API 請求) |
|--- |--- |
| Adobe Campaign 執行的傳送 ID | `ac_delivery_internal_name` |
