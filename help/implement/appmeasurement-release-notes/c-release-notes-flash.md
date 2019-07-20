---
description: Flash 的累積發行說明。可在桌面和網路上測量使用 ActionScript 的 Flash 應用程式。
seo-description: Flash 的累積發行說明。可在桌面和網路上測量使用 ActionScript 的 Flash 應用程式。
seo-title: Flash-Flex
solution: Analytics
subtopic: 發行說明
title: Flash-Flex
topic: 開發人員和實施
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764 b7 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Flash-Flex{#flash-flex}

Flash 的累積發行說明。可在桌面和網路上測量使用 ActionScript 的 Flash 應用程式。

>[!NOTE]
>
>若要尋找目前的程式庫版本，請開啓偵錯記錄。

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**4.0.3 版 **

* 已納入 Visitor API 1.6.1。

## August 18, 2016 {#section_D72EF20672174249B864997905D7552A}

**4.0.2-更新**

已納入 Visitor API 1.6.0。

## 2016 年 5 月 19 日 {#section_061305CFC1E040E69E3CDF4078C17AE4}

**4.0.1-更新**

納入 Visitor API 1.5.6

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe 已發行[安全性更新 APSB16-13](https://helpx.adobe.com/security/products/analytics/apsb16-13.html)，針對 [!DNL AppMeasurement]Flash 適用的   資料庫。此更新解決資料庫中重大漏洞，但僅限於啟用 `debugTracking` 時，此時可能會遭濫用而進行 [DOM 型 XSS 攻擊](https://www.owasp.org/index.php/DOM_Based_XSS)。

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **如果受影響，我們強烈建議立即停用`debugTracking`。**&#x200B;下列為部分範例程式碼:

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 
```

受影響的版本為所有平台上[!DNL AppMeasurement] 適用於Flash4.0版及更早版本。

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. 不過，我們仍將持續支援現有 AS2 專案的資料收集功能。僅管如此，我們強烈建議客戶將實作升級至 AS3，且導入 [!DNL AppMeasurement]Flash 適用的   的最新安全性功能。

[!DNL AppMeasurement] 對於受此問題影響的Flash客戶，必須使用可從 [!DNL Analytics] 主控台 [下載的更新程式庫來重建專案…](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

4.0版-更新：

* 納入 Visitor API 1.5.3.

## 2015 年 9 月 17 日 {#section_319911C0F080452981F8C8BEA2880463}

4.0版-更新：

* 納入 Visitor API 1.5.2.

## 2015 年 8 月 20 日 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

4.0版-更新：

* 納入 Visitor API 1.5.1.

## 2015 年 6 月 18 日 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

4.0版-更新

* 納入 Visitor API 1.5.
* 使用 Visitor API 1.5+ getCustomerID 方法來收集客戶 ID 和驗證狀態，並將其與資料收集請求一同傳送 (AN-102131)

## May 21, 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

3.9.2版-更新：

* 納入 Visitor API 1.4

## February 19, 2015 {#section_95ADF1725CE7415D956944A28182E69B}

3.9.2 版:

* 納入 Visitor API 1.3.5.
* 已變更為第一個追蹤呼叫後不再執行自動反向連結追蹤，以在第一個追蹤呼叫前手動設定 *`s.referrer`*&#x200B;時，以免第二個、第三個...追蹤呼叫 (通常是連結追蹤) 重複計算反向連結。(AN-92647)
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

3.9.1 版:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access).
* 支援訪客 ID 服務 1.3.2 的新功能。

## 2014 年 8 月 21 日 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

3.9 版:

* 已新增經緯度變數。
* 支援訪客 ID 服務 1.3.1 的新功能。

## 第 3.8.1 版 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

發行日期: **2014 年 6 月 19 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 支援訪客 ID 服務 1.3 的新功能。

## 版本 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

發行日期: **2014 年 4 月 17 日**

* 支援 [Marketing Cloud 訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 版本 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

發行日期: **2014 年 3 月 13 日**

* [!UICONTROL 「心率] 」視訊追蹤的多個錯誤修正。

## 版本 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

發行日期: **2014 年 2 月 6 日**

* [!UICONTROL 「心率] 」視訊追蹤的多個錯誤修正。

## 版本 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

發行日期: **2013 年 11 月 14 日**

* [!UICONTROL 「心率] 」視訊追蹤的多個錯誤修正。

## 版本 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

發行日期: **2013 年 10 月 17 日**

* 支援[心率視訊追蹤](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)。
* 已納入 VisitorAPI.swc 以支援[訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)。
* ActionScript 3 已不支援 Flash player 9。ActionScript 3 適用的 Flash Player 最低版本為 10。

## 第 3.6.2 版 {#section_57FB21568BDD48F7882F00AD630E6CE8}

發行日期: **2013 年 9 月 18 日**

* 進行內部變更，以支援即將推出的試用版。

## 第 3.5.5 版 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

發行日期: **2013 年 8 月 15 日**

* 已停用啟用離線追蹤後重新佇列失敗的請求。

## 第 3.5.4 版 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

發行日期: **2013 年 2 月 21 日**

* 修正 ActionScript 2 的 URL 編碼/解碼問題。

## 第 3.5.3 版 {#section_5192BC1C8BF547D1A5A92863686601DD}

發行日期: **2013 年 1 月 31 日**

* 新增傳送長度超過 255 個位元組之 URL 的支援，進而在 Adobe Data Collection 伺服器中支援「頁面 URL」欄位的擴充。Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. 這麼一來，在瀏覽器切截字串的情況下，可以避免長 URL 佔據其他資料，但仍可擷取長 URL。

* 新增後援訪客識別方法。請參閱[識別獨特訪客](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)。
* Added a new `abort` flag that can be set inside `doPlugins`. 若將此標幟設為 true，會使得 [!DNL AppMeasurement] 庫不再繼續使用該追蹤呼叫。中止標幟皆會隨每個追蹤呼叫重設，因此若後續的追蹤呼叫也需要被中止，就必須在 `doPlugins` 中再次設定此標幟。

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   這讓您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。

## 版本 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

發行日期: **2012 年 11 月 8 日**

* [!DNL Audience Manager] 整合的內部更新。

## 版本 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

發行日期: **2012 年 10 月 22 日**

* 變更 ActionScript 3 組建，忽略 `s.charSet` 的任何設定，因為我們一律使用 UTF-8。

## 版本 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012**
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. 使用大括號的變數捆綁主要用於使用 XML 標記設定 OSMF 視訊播放器時:

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

有一個名稱為 `autoBind` 的新屬性可供覆蓋 XML 標記中的預設行為:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

將 `autoBind` 設定為 `false` 會導致此值被視為常值字串，而不使用變數捆綁。此屬性若未設定為 `false`，則 XML 標記中的行維持不變。

**對於 ActionScript 程式碼的影響**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. 例如:

```
s.eVar1 = "{source}";
```

如果您正使用變數綑綁，則必須將此程式碼變更為使用新的 `bindVariable` 方法:

```
s.bindVariable("eVar1","source");
```

您可以視需要選擇將 `autoBindVariablesByValue` 設定為 true，回復到 3.5 版以前的行為，而不變更每個位置:

```
s.autoBindVariablesByValue = true;
```

**其他修正功能:**

* 修正當使用自訂 `media.monitor` 方法來追蹤媒體關閉事件時，可能無法傳送視訊結束事件的問題。

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## 版本 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

發行日期: **2012 年 7 月 19 日**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## 版本 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

發行日期: **2012 年 6 月 21 日**

* 變更成在 AS3 組建中一律使用 UTF-8。這麼做可預防某些多位元組語言的字串問題。

## 版本 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

發行日期: **2012 年 4 月 26 日**

視訊測量: 修正 Brightcove 播放程式 API 中偏移值不一致的問題。現在如果該偏移量報告為零，完成時會使用長度做為偏移量。這可修正使用偏移值來追蹤完成的新方法問題。

## 版本 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

發行日期: **2012 年 1 月 19 日**

* 以新方式更新視訊追蹤，現可追蹤完整的視訊檢視次數。

## 版本 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

發行日期: **2011 年 9 月 8 日**

* 讓屬性可以包含常值零值 "0"。先前無法傳送包含零值的屬性。

## 版本 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

發行日期: **2011 年 5 月**

* 在 OSMF 中，修正使用 Proxy 外掛程式追蹤 OSMF 視訊播放器的問題。此修正功能讓 OSMF ProxyElements 能在未追蹤其所代理的元素時進行追蹤。
* 修正會導致在 Flash Player 9.0.16 上測量視訊時出錯的問題。

