---
description: JavaScript 適用的 AppMeasurement 累積發行說明。
seo-description: JavaScript 適用的 AppMeasurement 累積發行說明。
seo-title: JavaScript 適用的 AppMeasurement
solution: Analytics
subtopic: 發行說明
title: JavaScript 適用的 AppMeasurement
topic: 開發人員和實施
uuid: 1440013d-d266-4dce-9807-1b9 adac73315
translation-type: tm+mt
source-git-commit: d374a4597f4b4a8adec697ba5befa5014d711074

---


# JavaScript 適用的 AppMeasurement{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## 2.16.0 版

發行日期: **2019 年 8 月 8 日**

| 功能 | 說明 |
| -----------| ---------- |
| 適用於退出連結的 `sendBeacon` 支援 | 為退出連結實作 `sendBeacon` 支援 (在 [!UICONTROL AppMeasurement] 中)。這會改善退出連結追蹤，並可能導致流量增加。`SendBeacon` 不會在頁面內容中執行，而是在瀏覽器內容中執行。這就是頁面未載入 `sendBeacon`時，請求仍將完成。這對於退出連結非常有用，因為這樣會更有可能完成退出連結請求。 |
| ECID/fid 值 | 現在，第一次點擊時會快取 ECID/fid 值，即使 OptIn 設定有所變更。 |
| DIL 9.3 | Audience Manager 模組已更新至 DIL 9.3 |
| 捲動範圍追蹤 | 在 s.ActivityMap.trackScrollReach 顯示開關，開啓或關閉捲動範圍追蹤。 |
| 訪客 ID 服務 4.4.0 | 升級 AppMeasurement 以使用訪客 ID 服務 4.4.0。 |

## 2.15.0 版

發行日期:**2019 年 7 月 15 日**

* 新增Activity Map捲動覆蓋至Activity Map擴充功能(AN-172949)
* 已將DIL9.2新增至AppMeasurement(AN-182472)

## 2.14.0 版

發行日期: **2019 年 5 月 21 日**

* 已修正有多個點擊擱置時所發生的追蹤器參數狀態問題。(AN-176931、AN-176629、DTM-12758)
* 已更新 AppMeasurement 以納入 Visitor.js 4.3.0 (AN-180049)

## 2.13.0 版

發行日期: **2019 年 4 月 10 日**

修正許多回報的ClearVars問題。當點擊已在追蹤器準備就緒之前，就會發生問題。當追蹤器就緒時，程式庫可以設定已清除或變更的變數。(AN-176931、AN-176629、DTM-12758).

## 2.12.0 版

Release Date: **02/22/2019**

* Audience Manager 模組已更新至 DIL 9.1。(AN-175255)
* GTM 安全性政策不允許 Activity Map 模組。(AN-174679)
* 改進AppMeasurement以接受「身分服務」未在選擇加入時核准退出。(AN-175259)

## 2.11.0 版

Release Date: **02/11/2019**

* 在 AppMeasurement 中，新增了全新 Adobe  選擇加入服務功能的支援。(AN-163546)
* 新增了在工作階段儲存體上存儲連結追蹤資料的支援。(AN-162272)
* 新增了 Audio Analytics 媒體資料流類型的支援。(AN-173265)

## 版本 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] 在 POST 期間會封鎖 Cookie 傳輸。(AN-165538)
* 終止對 XDomainRequest 的支援。(AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## 版本 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

發行日期: **2018 年 5 月 24 日**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe 建議只要更新相關的程式碼程式庫 ([!DNL at.js] 等等)，就要升級至最新的 Visitor API 版本。[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* 修正當連結追蹤關閉時持續寫入連結追蹤 Cookie 的問題。(AN-156332)
* 修正多次呼叫時 `registerPreTrackCallback` 和 `registerPostTrackCallback` 會破壞回呼函數簽名的問題。(AN-158566)

## 版本 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

發行日期: **2018 年 4 月 12 日**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* 當連結追蹤關閉時持續寫入連結追蹤 cookie。(AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## 版本 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

發行日期: **2018 年 3 月 29 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix: (CORE-11390, CORE-10634)

## 版本 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

發行日期: **2018 年 3 月 15 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* 重構資料集合端點以便進行分享。(AN-156647)
* 將請求的來回時間量度新增至 [!DNL AppMeasurement]. (AN-158343)

## 版本 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

發行日期: **2018 年 1 月 18 日**

* 終止支援 IE 6 到 IE 9
* 納入 Visitor API v3.0.0
* 納入 DIL v7.00

## 版本 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

發行日期: **2017 年 11 月 9 日**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## 版本 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

發行日期: **2017 年 9 月 21 日**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* 納入訪客 API 2.5.0。

## 版本 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

發行日期: **2017 年 8 月 17 日**

* 納入 dil.js v6.11
* 納入訪客 API 2.4.0

## 版本 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

發行日期: **2017 年 7 月 20 日**

* 修正 [!DNL s.Util.getQueryParam] 擷取 # 時發生的錯誤
* Added v6.10 of [!DNL dil.js] (AN-145701)

## 版本 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

發行日期: **2017 年 6 月 8 日**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* 納入訪客 API 2.2.0 版。(AN-144042)

## 版本 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* 納入最新版 [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* 重新納入 Visitor API 2.1.0。(AN-140873)
* Added `mcorgid` parameter. (AN-139586)
* 新增 cp (customerPerspective) 參數。(AN-140897)

## 版本 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

發行日期: **2017 年 3 月 9 日**

* 移到需要到更新版本 2.0.0 新的建立程序。(AN-137878)
* 將「mboxMCSDID」的處理移到追蹤呼叫發出的正確截面位置。(AN-138483)

## 版本 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

發行日期: **2017 年 1 月 19 日**

* 納入 Visitor API 2.0.0
* 重新排序函數呼叫和檢查，以便在中止檢查完成後使用 SDID。(AN-134364)
* 新增以下追蹤前和追蹤後呼叫鉤點。(AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   這些函數採用參數的形式: callback (函數) 和該函數的參數。例如:

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   在註冊 callback 時，系統會利用 `requestUrl` 和任何傳入的參數叫用 callback。這項作業會發生在追蹤呼叫之前或之後，須視用來註冊 callback 的方法而定。我們無法保證這些 callback 的呼叫順序。在前置函數中註冊的 callback，會在最終的追蹤 URL 建立時叫用。後置 callback 會在追蹤呼叫成功時呼叫 (如果追蹤呼叫失敗，系統不會叫這些函數)。任何以 `registerPreTrackCallback` 註冊的 callback 均不會影響追蹤呼叫。此外，我們不建議在任何已註冊的 callback 中呼叫任何追蹤方法，因為這樣可能會導致無限迴圈。

## 1.7.0 版 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

更新日期: **2016 年 11 月 10 日**

* 納入 Visitor API 1.10.1。

## 1.7.0 版 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

更新日期: **2016 年 10 月 20 日**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* 已納入 Visitor API 1.9.0。(AN-132072)

## 1.7.0 版 {#section_945311938EE2480A9A697BFE1E5B2AA7}

更新日期: **2016 年 9 月 15 日**

* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411)

* 包括 Visitor API 1.8.0 (AN-129887)

## 版本 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

更新日期: **2016 年 8 月 18 日**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* 已納入 Visitor API 1.7.0。

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## 版本 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

更新日期: **2016 年 8 月 4 日**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## 版本 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

發行日期: **2016 年 7 月 21 日**

* 已納入 Visitor API 1.6.0。
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## 版本 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

發行日期: **2016 年 6 月 16 日**

已納入 Visitor API 1.5.7。

## 版本 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

發行日期: **2016 年 5 月 19 日**

[!DNL JavaScript] 1.5.6版

* 納入 Visitor API 1.5.6
* 已修正處理 Firefox 中無法引發完成事件的連結點擊追蹤功能。

## 版本 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

發行日期: **2016 年 4 月 21 日**

* [!DNL AppMeasurement][!DNL Activity Map] 模組已整合在 [!DNL AppMeasurement] 標準模組中，因此您只需要參考一 [!DNL .js] 個檔案即可。Additionally, [!DNL Activity Map] tracking is activated by default. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## 版本 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

發行日期: **2016 年 3 月 17 日**

* 已納入 Visitor API 1.5.4
* 支援 Visitor API 1.5.4+ 選擇退出功能

## 1.5.3 版 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

發行日期: **2016 年 1 月 21 日**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* 已將剩餘的頁面 URL (「-g」) 移至追蹤請求查詢字串的尾端。(AN-114647)

## 版本 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

發行日期: **2015 年 11 月 5 日**

* 納入 Visitor API 1.5.3.
* 已修正 IE 11 對 URL 截斷 2047 的偵測功能 (AN-114914)

## 版本 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

發行日期: **2015 年 9 月 17 日**

* 納入 Visitor API 1.5.2

## 版本 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

發行日期: **2015 年 8 月 29 日**

* 納入 Visitor API 1.5.1.

## 版本 1.5.1 {#section_3C9637EDB058479184731067897E857C}

發行日期: **2015 年 7 月 16 日**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## 版本 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

發行日期: **2015 年 6 月 18 日**

* Visitor API 1.5 的支援 (使用 *`getCustomerIDs`* 方法收集客戶 ID 及已驗證狀態，並針對資料收集要求傳送 ID)。
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* 已修正 1.4.5 版中說明的已知問題。

## 版本 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

發行日期: **2015 年 5 月 21 日**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> iOS 延伸功能</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external">iOS 延伸功能實施</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android 穿戴式延伸功能</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external">Android 穿戴式延伸功能</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

* 納入 Visitor API 1.4.
* 已更新 AudienceManagement 模組以使用 DIL 6.0 版。

**已知問題**

在訪客API/ [!DNL AppMeasurement][!DNL Audience Manager] 模組整合中，將會有兩個目的地發佈IE中的iFrame請求： `//fast.<subdomain>.demdex.net/dest5.html``//fast.<subdomain>.demdex.net/dest4.html`以及如同其他瀏覽器的情況，正確的行為是只載入 `//fast.<subdomain>.demdex.net/dest5.html`.

## 版本 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

發行日期: **2015 年 4 月 16 日**

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 使用生命週期量度的自訂資料 </p> </td> 
   <td colname="2"> <p>您現在可使用生命週期量度來納入自訂內容資料的變數。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap中的信標追蹤支援 </span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

已進行微幅修正，以在 `trackLight` 呼叫後清除小型伺服器呼叫設定檔 ID。

## 版本 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

發行日期: **2015 年 2 月 19 日**

* 將所有延遲追蹤呼叫的處理改為一致，以修正延遲期間的備份變數問題，例如已點按物件。
* 第一個追蹤呼叫後不再進行自動反向連結追蹤，以在第一個追蹤呼叫前手動設定 *`s.referrer`*&#x200B;時，以免第二個、第三個...追蹤呼叫 (通常是連結追蹤) 重複計算反向連結。
* 已更新分送 Zip 檔，現在包含 Visitor API 1.3.5。

## 版本 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

發行日期: **2015 年 1 月 15 日**

* 修正 WebKit 轉譯前處理，防止追蹤未檢視的轉譯前頁面。
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## 版本 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

發行日期: **2014 年 9 月 18 日**

* 新增 `tagContainerMarker` 變數，讓實施可指定最多 4 個字元附加至版本字串與其他破折號分隔字元。此功能可用於動態標籤管理。

   ```js
   // JavaScript 
   s.tagContainerMarker = "D1.0"; 
   
   // Data Collection request 
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   這 4 個字元僅限使用 URL 檔案路徑允許的字元，例如英數字元和句號。

* 在利用 H 代碼加上雙標籤的頁面中，啟用強制連結追蹤 (Webkit 瀏覽器的預設) 時，在自動連結追蹤 (下載和退出) 期間可能會發生重複循環，這個問題已經修正。此外，在自動連結追蹤周圍新增一般防護以避免類似的重複循環。此防護可限制自動連結追蹤每 10 秒重複點擊&#x200B;*相同*&#x200B;物件一次。此防護僅適用於自動連結追蹤，因此，手動連結追蹤 (s.tl) 呼叫不在此限。此外，點擊不同物件也不受此防護影響，並且將進行追蹤。
* 已修正需要延遲時點擊物件的處理。
* 如果訪客 API 尚未取得需要的值，從連結 onclick 功能呼叫 s.t 時，會導致頁面檢視計數倍增，這個問題已經修正。
* HTTP POST 支援。

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## 版本 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

發行日期: **2014 年 8 月 21 日**

*  15 版中不再針對移除追蹤瀏覽器外掛程式 (`p` 查詢參數) 做為外掛程式進行報告。
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

已新增對[其他 eVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) 和事件 (101-1000) 的支援。

>[!NOTE]
>
>H-Code不支援其他eVar和事件。

[!DNL JavaScript]

## 版本 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

發行日期: **2014 年 6 月 19 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 支援訪客 ID 服務 1.3 的新功能。

## 版本 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

發行日期: **2014 年 5 月 22 日**

* [!DNL AppMeasurement][!DNL JavaScript]`s_gi` 函數無法正確找到使用H程式碼建立的例項 `s_gi`。Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## 版本 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

發行日期: **2014 年 4 月 17 日**

* 支援 [Marketing Cloud 訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 版本 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

發行日期: **2014 年 3 月 13 日**

* 已修正心率視訊的錯誤。

## 版本 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

發行日期: **2014 年 2 月 20 日**

* 已修正心率視訊的錯誤。

## 版本 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

發行日期: **2014 年 2 月 6 日**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] 客戶也必須更新至 DIL 模組的 4.8 版本。

## 版本 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

發行日期: **2013 年 11 月 15 日**

* 已修正用於[心率視訊測量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)的頁面事件。

## 版本 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

發行日期: **2013 年 11 月 14 日**

* 新增支援[心率視訊測量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)。
* [!DNL VisitorAPI.js]已新增 以支援[訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)。

## 版本 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* 防止 Opera 瀏覽器針對開頭為 "opera:" 的連結 ("opera:" 類似於其他瀏覽器中的 "about:" 和 "chrome:")，傳送連結追蹤呼叫。
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## 版本 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

發行日期: **2013 年 9 月 18 日**

* 修正在 `head` 標籤中放置庫和頁面代碼的支援。
* Added missing module `onLoad` support.

## 版本 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

發行日期: **2013 年 8 月 15 日**

* 新增支援透過 Adobe 標籤管理進行部署。
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## 版本 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

發行日期: **2013 年 7 月 18 日**

* 自動連結追蹤現在會忽略雜湊/片段。Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   現在會忽略雜湊/片段，所以只在檔案名稱結尾為符合的副檔名時才會追蹤連結。

## 版本 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

發行日期: **2013 年 5 月 23 日**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. 本程式庫提供與 [!DNL s_code.js] 相同的核心功能，但可更加輕鬆快速地在行動版與桌面版網頁上使用。

* 執行速度較 H.25 代碼快 3-7 倍。
* 未壓縮大小僅為 21k，而採用 gzipped 壓縮的大小為 8k (H.25 代碼的未壓縮大小為 33k，而採用 gzipped 的大小為 13 k)。
* 原生支援，以便取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。
* 輕便快速且功能強大，無論在行動版網頁或桌面完整版網頁皆可輕鬆使用，可讓您在所有的網站環境中使用單一程式庫。

請參閱 實施指南中的 [Javascript 適用的 AppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs)。[!DNL Analytics]

>[!NOTE]
>
>此新版本不支援某些外掛程式。如需詳細資料，請參閱[外掛程式支援](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support)。
