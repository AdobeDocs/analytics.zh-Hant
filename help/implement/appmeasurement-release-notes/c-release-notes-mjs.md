---
description: JavaScript 適用的 AppMeasurement 累積發行說明。
subtopic: Release notes
title: JavaScript 適用的 AppMeasurement
topic: Developer and implementation
uuid: 1440013d-d266-4dce-9807-8b9adac73315
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 適用的 AppMeasurement{#appmeasurement-for-javascript}

JavaScript 適用的 [!DNL AppMeasurement] 累積發行說明。

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

每個程式庫的最新版本可從 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 代碼管理器]**&#x200B;下載。

## 版本 2.17.0

發行日期: **2019 年 8 月 23 日**

| 功能/修正 | 說明 |
| -----------| ---------- |
| 新增百度支援 | 新增支援百度查詢字串重新排序。 |
| 修正 | 修正造成等候選擇加入時排入佇列的點擊中出現過時訪客值的問題。 |

## 2.16.0 版

發行日期: **2019 年 8 月 15 日**

| 功能 | 說明 |
| -----------| ---------- |
| 適用於退出連結的 `sendBeacon` 支援 | 為退出連結實作 `sendBeacon` 支援 (在 [!UICONTROL AppMeasurement] 中)。這會改善退出連結追蹤，並可能導致流量增加。`SendBeacon` 不會在頁面的背景下執行，但會在瀏覽器的背景下執行。也就是說，如果頁面透過 `sendBeacon` 上傳，要求仍會完成。這非常適合用於退出連結，因為這會讓退出連結要求更有可能完成。 |
| ECID/fid 值 | 現在，第一次點擊時會快取 ECID/fid 值，即使 OptIn 設定有所變更。 |
| DIL 9.3 | Audience Manager 模組已更新至 DIL 9.3 |
| 捲動範圍追蹤 | 在 s.ActivityMap.trackScrollReach 顯示開關，開啓或關閉捲動範圍追蹤。 |
| 訪客 ID 服務 4.4.0 | 升級 AppMeasurement 以使用訪客 ID 服務 4.4.0。 |

## 2.15.0 版

發行日期:**2019 年 7 月 15 日**

* 在 Activity Map 擴充功能中新增 ActivityMap 捲動觸及追蹤功能 (AN-172949)
* 將 DIL 9.2 新增至 AppMeasurement (AN-182472)

## 2.14.0 版

發行日期: **2019 年 5 月 21 日**

* 已修正有多個點擊擱置時所發生的追蹤器參數狀態問題。(AN-176931、AN-176629、DTM-12758)
* 已更新 AppMeasurement 以納入 Visitor.js 4.3.0 (AN-180049)

## 2.13.0 版

發行日期: **2019 年 4 月 10 日**

修正許多 clearVar 回報的問題。若在追蹤器準備就緒前送出點擊，則會發生問題。當追蹤器準備就緒時，程式庫可設定已經清除或變更的變數。(AN-176931、AN-176629、DTM-12758).

## 2.12.0 版

發行日期: **2019 年 2 月 22 日**

* Audience Manager 模組已更新至 DIL 9.1。(AN-175255)
* GTM 安全性政策不允許 Activity Map 模組。(AN-174679)
* 改善 AppMeasurement；在 Identity 服務不核准選擇加入時，讓使用者可以選擇退出。(AN-175259)

## 2.11.0 版

發行日期: **2019 年 2 月 11 日**

* 在 AppMeasurement 中，新增了全新 Adobe 選擇加入服務功能的支援。(AN-163546)
* 新增了在工作階段儲存體上存儲連結追蹤資料的支援。(AN-162272)
* 新增了 Audio Analytics 媒體資料流類型的支援。(AN-173265)

## 版本 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

發行日期: **2018 年 9 月 20 日**

此版本確保 [!DNL AppMeasurement] 程式庫正確提交所有連接種類的 Cookie。

* [!DNL AppMeasurement] 在 POST 期間會封鎖 Cookie 傳輸。(AN-165538)
* 終止對 XDomainRequest 的支援。(AN-165733)
* 將 [!DNL AppMeasurement] 的預設 Cookie 期限值從五年縮短為兩年。(AN-158572)
* 從代碼管理器中移除媒體模組 ([!DNL AppMeasurement]) (AN-166590)

## 版本 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

發行日期: **2018 年 5 月 24 日**

> [!NOTE]使用 [!DNL Experience Cloud] ID 服務的客戶需要具備訪客 API 3.0 或更新版本。Adobe 建議只要更新相關的程式碼程式庫 ([!DNL at.js] 等等)，就要升級至最新的 Visitor API 版本。[!DNL AppMeasurement.js]

* 更新 [!DNL AppMeasurement] 以使用更新後的訪客介面要求 ID。(AN-151483)
* 修正當連結追蹤關閉時持續寫入連結追蹤 Cookie 的問題。(AN-156332)
* 修正多次呼叫時 `registerPreTrackCallback` 和 `registerPostTrackCallback` 會破壞回呼函數簽名的問題。(AN-158566)

## 版本 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

發行日期: **2018 年 4 月 12 日**

* 更新 [!DNL AppMeasurement] 以使用更新後的訪客介面要求 ID。(AN-151483)
* 當連結追蹤關閉時持續寫入連結追蹤 cookie。(AN-156332)
* 將 [!DNL AppMeasurement] 的預設 Cookie 期限值從五年縮短為兩年。(AN-158572)

## 版本 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

發行日期: **2018 年 3 月 29 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix: (CORE-11390, CORE-10634)

## 版本 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

發行日期: **2018 年 3 月 15 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix: (CORE-11390, CORE-10634)

* 將 VAPI v3.1 與 [!DNL AppMeasurement] v2.8 搭配組合。(AN-158353)
* 重構資料集合端點以便進行分享。(AN-156647)
* 將請求的來回時間量度新增至 [!DNL AppMeasurement].(AN-158343)

## 版本 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

發行日期: **2018 年 1 月 18 日**

* 終止支援 IE 6 到 IE 9
* 納入 Visitor API v3.0.0
* 納入 DIL v7.00

## 版本 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

發行日期: **2017 年 11 月 9 日**

修正呼叫 s_gl 時，[!DNL AppMeasurement] 程式庫無法每次都設為正確帳戶組合的問題。(AN-152153)

## 版本 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

發行日期: **2017 年 9 月 21 日**

* 納入 [!DNL dil.js 6.12] ([!DNL Audience Manager] 模組)

* 納入訪客 API 2.5.0。

## 版本 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

發行日期: **2017 年 8 月 17 日**

* 納入 dil.js v6.11
* 納入訪客 API 2.4.0

## 版本 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

發行日期: **2017 年 7 月 20 日**

* 修正 [!DNL s.Util.getQueryParam] 擷取 # 時發生的錯誤
* 新增 [!DNL dil.js] v6.10 (AN-145701)

## 版本 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

發行日期: **2017 年 6 月 8 日**

* 新增對多重 [!DNL AppMeasurement] 具現化階層的支援。(AN-138237)
* 納入訪客 API 2.2.0 版。(AN-144042)

## 版本 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* 納入最新版 [!DNL dil.js] (AN-140396)
* 新增對 `adobe_mc_ref` 參數的支援，可覆寫頁面反向連結。(AN-131920)
* 重新納入 Visitor API 2.1.0。(AN-140873)
* 新增 `mcorgid` 參數。(AN-139586)
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

* 使用 Demdex Integration Library (DIL) 6.6 更新 [!DNL Audience Manager] 模組。(AN-132065)
* 納入 Visitor API 1.9.0。(AN-132072)

## 1.7.0 版 {#section_945311938EE2480A9A697BFE1E5B2AA7}

更新日期: **2016 年 9 月 15 日**

* 使用 DIL 6.5 和其他設定更新 [!DNL AppMeasurement] [!DNL Audience Manager] 模組 (AN-129411)

* 包括 Visitor API 1.8.0 (AN-129887)

## 版本 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

更新日期: **2016 年 8 月 18 日**

* 更新 [!DNL AppMeasurement]，可讀取和寫入 AMCV Cookie。(AN-127098)
* 納入 Visitor API 1.7.0。

> [!NOTE]另請參閱下列 [!DNL JavaScript] 1.6.3 版的發行說明中，對 Experience Cloud ID 服務的更新要求。

## 版本 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

更新日期: **2016 年 8 月 4 日**

* 修正 [!DNL AppMeasurement] 提前終止請求連線的問題。(AN-126448)

>[!IMPORTANT]
>
>1.6.0 版 [!DNL Experience Cloud] ID 服務「需使用」**[!DNL AppMeasurement] 供 [!DNL JavaScript] 1.6.3 版或更新版本使用。如果您想要升級為 1.6.0 版的 Experience Cloud ID 服務，請務必使用 [!DNL AppMeasurement] 程式碼 1.6.3 版或更新版本。

## 版本 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

發行日期: **2016 年 7 月 21 日**

* 已納入 Visitor API 1.6.0。
* 修正導致 [!DNL AppMeasurement] 在訪客 API 中呼叫了錯誤隱藏方法的問題。(AN-126006)
* 修正引發此 [!DNL JavaScript] 錯誤的問題:「屬性僅在 v:image 上有效」。(AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa.
</note>

 -->

## 版本 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

發行日期: **2016 年 6 月 16 日**

納入 Visitor API 1.5.7。

## 版本 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

發行日期: **2016 年 5 月 19 日**

[!DNL JavaScript] 1.5.6 版

* 納入 Visitor API 1.5.6
* 已修正處理 Firefox 中無法引發完成事件的連結點擊追蹤功能。

## 版本 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

發行日期: **2016 年 4 月 21 日**

* The [!DNL AppMeasurement] Activity Map module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. 此外，預設已啟用「Activity Map」追蹤。(AN-112689)

* 修正 [!DNL AppMeasurement] 中查詢字串變數順序的截斷問題，因此 *`pageURLRest`* 會顯示於最後。(AN-114647)

## 版本 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

發行日期: **2016 年 3 月 17 日**

* 已納入 Visitor API 1.5.4
* 支援 Visitor API 1.5.4+ 選擇退出功能

## 1.5.3 版 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

發行日期: **2016 年 1 月 21 日**

* 修正使用 POST 來追蹤呼叫時，[!DNL Audience Manager] 模組的處理方式。(AN-115381)
* 已將剩餘的頁面 URL (「-g」) 移至追蹤請求查詢字串的尾端。(AN-114647)

## 版本 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

發行日期: **2015 年 11 月 5 日**

* 納入 Visitor API 1.5.3。
* 已修正 IE 11 對 URL 截斷 2047 的偵測功能 (AN-114914)

## 版本 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

發行日期: **2015 年 9 月 17 日**

* 納入 Visitor API 1.5.2

## 版本 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

發行日期: **2015 年 8 月 29 日**

* 納入 Visitor API 1.5.1。

## 版本 1.5.1 {#section_3C9637EDB058479184731067897E857C}

發行日期: **2015 年 7 月 16 日**

* 更新 [!DNL Audience Manager] 模組以使用 AAM DIL 6.2 - 從 VisitorAPI.js 取得客戶 ID 並在呼叫給 AAM 時將其傳入。(AN-104978)

## 版本 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

發行日期: **2015 年 6 月 18 日**

* Visitor API 1.5 的支援 (使用 *`getCustomerIDs`* 方法收集客戶 ID 及已驗證狀態，並針對資料收集要求傳送 ID)。
* 修正 **[!UICONTROL AudienceManagement]** 模組 (DIL 6.1) 中重複目的地 iframe 的建立
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
   <td colname="col2"> <p> 在 <span class="keyword">iOS</span> SDK 4.5 版中啟動新的 <span class="keyword">iOS</span> 擴充功能，可讓您從 Apple Watch 應用程式、Today Widget、Photo Editing Widget 和所有其他 <span class="keyword">iOS</span> 擴充應用程式上收集使用資料。 </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/ios_ext.html">iOS 延伸功能實施</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android 穿戴式延伸功能</span> </p> </td> 
   <td colname="col2"> <p> 在 <span class="keyword">Android</span> SDK 4.5 版中啟動新的 <span class="keyword">Android</span> 擴充功能可讓您透過 <span class="keyword">Android</span> 穿戴式應用程式中收集資料。 </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/android_wearable.html">Android 穿戴式延伸功能</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

* 納入 Visitor API 1.4.
* 已更新 AudienceManagement 模組以使用 DIL 6.0 版。

**已知問題**

在訪客 API / [!DNL AppMeasurement] [!DNL Audience Manager] 模組整合中，將有可發佈在 IE6-9 中提出之 iFrame 要求的兩個目的地: `//fast.<subdomain>.demdex.net/dest5.html` 和 `//fast.<subdomain>.demdex.net/dest4.html`。如同其他瀏覽器的情況，正確的行為是只載入 `//fast.<subdomain>.demdex.net/dest5.html`.

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
   <td colname="1"> <p><span class="keyword">PhoneGap</span> 支援信標追蹤功能 </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

已進行微幅修正，以在 `trackLight` 呼叫後清除小型伺服器呼叫設定檔 ID。

## 版本 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

發行日期: **2015 年 2 月 19 日**

* 將所有延遲追蹤呼叫的處理改為一致，以修正延遲期間的備份變數問題，例如已點按物件。
* 第一個追蹤呼叫後不再進行自動反向連結追蹤，以在第一個追蹤呼叫前手動設定  *`s.referrer`*&#x200B;時，以免第二個、第三個...追蹤呼叫 (通常是連結追蹤) 重複計算反向連結。
* 已更新分送 Zip 檔，現在包含 Visitor API 1.3.5。

## 版本 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

發行日期: **2015 年 1 月 15 日**

* 修正 WebKit 轉譯前處理，防止追蹤未檢視的轉譯前頁面。
* 更新分送 Zip 檔，以包含 Visitor API 1.3.4 以及 **[!UICONTROL AudienceManagement]** 模組 (包含 DIL 5.5 版)。

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
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_implement.html) implementation for Experience Cloud.

## 版本 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

發行日期: **2014 年 8 月 21 日**

*  15 版中不再針對移除追蹤瀏覽器外掛程式 (`p` 查詢參數) 做為外掛程式進行報告。
* 在下載 Zip 中新增 **[!UICONTROL AudienceManagement]** 模組。

已新增對[其他 eVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/evars_events.html) (76 - 250) 和事件 (101-1000) 的支援。

> [!NOTE]H-Code 不支援其他 eVar 和事件。

[!DNL JavaScript]

## 版本 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

發行日期: **2014 年 6 月 19 日**

* 修正處理訪客 API 欄位 (如舊版 [!DNL Analytics] 訪客 ID) 的完成和等待標幟時會發生錯誤的問題。
* 支援訪客 ID 服務 1.3 的新功能。

## 版本 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

發行日期: **2014 年 5 月 22 日**

* [!DNL JavaScript] `s_gi` 適用的 [!DNL AppMeasurement] 功能無法正確地找到使用 H-Code `s_gi` 所建立的例項。請注意，此問題只有影響到某些雙重標籤實施，意即 [!DNL JavaScript] 適用的 [!DNL AppMeasurement] 和 H-Code 出現在具備個別例項的相同頁面，而報表套裝也使用 `s_gi` 尋找例項。

## 版本 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

發行日期: **2014 年 4 月 17 日**

* 支援 [Experience Cloud訪客ID服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 版本 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

發行日期: **2014 年 3 月 13 日**

* 已修正心率視訊的錯誤。

## 版本 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

發行日期: **2014 年 2 月 20 日**

* 已修正心率視訊的錯誤。

## 版本 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

發行日期: **2014 年 2 月 6 日**

* 修正 [!DNL Audience Manager] DIL 模組的相容性問題。[!DNL Audience Manager] 客戶也必須更新至 DIL 模組的 4.8 版本。

## 版本 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

發行日期: **2013 年 11 月 15 日**

* 已修正用於[心率視訊測量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)的頁面事件。

## 版本 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

發行日期: **2013 年 11 月 14 日**

* 新增支援[心率視訊測量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)。
* [!DNL VisitorAPI.js]已新增 以支援[訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html)。

## 版本 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* 防止 Opera 瀏覽器針對開頭為 "opera:" 的連結 ("opera:" 類似於其他瀏覽器中的 "about:" 和 "chrome:")，傳送連結追蹤呼叫。
* 新增 `alt=""` 至所有影像物件，以遵循「視訊與通訊無障礙法」(Accessible Video and Communications Act)。

## 版本 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

發行日期: **2013 年 9 月 18 日**

* 修正在 `head` 標籤中放置庫和頁面程式碼的支援。
* 已新增遺漏模組 `onLoad` 支援。

## 版本 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

發行日期: **2013 年 8 月 15 日**

* 新增支援透過 Adobe 標籤管理進行部署。
* 修正 [!DNL AppMeasurement] 物件上無法設定階層變數的問題。

## 版本 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

發行日期: **2013 年 7 月 18 日**

* 自動連結追蹤現在會忽略雜湊/片段。以前由於下列 URL 的整個 `.pdf` 結尾為 `href`，所以會自動加以追蹤:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   現在會忽略雜湊/片段，所以只在檔案名稱結尾為符合的副檔名時才會追蹤連結。

## 版本 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

發行日期: **2013 年 5 月 23 日**

代碼管理器現在提供新版 [!DNL JavaScript] [!DNL AppMeasurement] 程式庫。本程式庫提供與 [!DNL s_code.js] 相同的核心功能，但可更加輕鬆快速地在行動版與桌面版網頁上使用。

* 執行速度較 H.25 代碼快 3-7 倍。
* 未壓縮大小僅為 21k，而採用 gzipped 壓縮的大小為 8k (H.25 代碼的未壓縮大小為 33k，而採用 gzipped 的大小為 13 k)。
* 原生支援，以便取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。
* 輕便快速且功能強大，無論在行動版網頁或桌面完整版網頁皆可輕鬆使用，可讓您在所有的網站環境中使用單一程式庫。

請參閱 實施指南中的 [Javascript 適用的 AppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html)。[!DNL Analytics]

> [!NOTE]這個新版本不支援部分的外掛程式。如需詳細資料，請參閱[外掛程式支援](https://marketing.adobe.com/resources/help/en_US/sc/implement/plugins_support.html)。
