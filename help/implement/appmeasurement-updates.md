---
title: JavaScript 適用的 AppMeasurement 版本注意事項
description: JavaScript 適用的 AppMeasurement 累積版本注意事項。
subtopic: Release notes
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
source-git-commit: 7f27e92b1fc378516423bc971b05e34880897ec9
workflow-type: ht
source-wordcount: '2218'
ht-degree: 100%

---

# JavaScript 適用的 AppMeasurement 版本注意事項

JavaScript 適用的 [!DNL AppMeasurement] 累積版本注意事項。

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

您可以在[代碼管理器](/help/admin/admin/code-manager-admin.md)中下載最新版的 AppMeasurement。

## 2.22.3 版本

發行日期: **2021 年 10 月 11 日**

* 參照說明文件的已更新檔案將指向目前的說明地點。

## 2.22.2 版本

發行日期：**2021 年 9 月 7 日**

* 此更新會讓 `opt.dmp` 和 `opt.sell` 在追蹤連結時一定會被納入。 以下是[同意變數的完整清單](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=zh-Hant)。

## 2.22.1 版本

發行日期：**2021 年 8 月 17 日**

* 使用退出的客戶可能會在追蹤連結時看到伺服器端轉送退出參數不被接受。 這個版本中的修正會使得在追蹤連結時如果有退出標幟存在就會傳送這些標幟。

## 2.22.0 版本

發行日期：**2020 年 8 月 4 日**

* 使用者選擇退出偏好設定而造成第一個點擊未傳送，此時要修復缺少的推薦者。

## 2.21.0 版本

發行日期：**2020 年 6 月 24 日**

* 已修正不一定會為 Firefox 套用 Activity Map linkExclusions 篩選器的問題。

## 2.20.0 版本

發行日期：**2020 年 3 月 5 日**

* 已更新 Internet Explorer 偵測以抑制 JSLint 警告，而修正安全性相關問題。

## 2.19.0 版本

發行日期：**2020 年 2 月 21 日**

* Audience Manager 模組已更新至 DIL 9.4。(AN-209341)

## 2.18.0 版本

發行日期：**2020 年 2 月 13 日**

* AppMeasurement 現在可以藉由設定 [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) 變數強制 Cookie 包含 Secure 屬性。此變數的需求是，必須安全地提供整個用戶端網站的服務 (HTTPS)。(AN-204604)

## 2.17.0 版本

發行日期：**2019 年 8 月 23 日**

* 新增支援百度查詢字串重新排序。(AN-182483)
* 修正造成等候選擇加入時排入佇列的點擊中出現過時訪客值的問題。(AN-184391)

## 2.16.0 版本

發行日期：**2019 年 8 月 15 日**

* 為退出連結實施 `sendBeacon` 支援 (在 [!UICONTROL AppMeasurement] 中)。如果點擊使用 `sendBeacon` 且頁面取消載入，要求仍會完成。這對於退出連結非常有用，因為點擊更有可能到達資料收集伺服器。(AN-175142)
* 現在，第一次點擊時會快取 ECID/fid 值，即使 OptIn 設定有所變更。(AN-175142)
* Audience Manager 模組已更新至 DIL 9.3。(AN-182704)
* 在 `s.ActivityMap.trackScrollReach` 中顯示開關，用於開啟或關閉捲動觸及追蹤。(AN-182754)
* 升級 AppMeasurement 以使用訪客 ID 服務 4.4.0。(AN-182912)

## 2.15.0 版本

發行日期：**2019 年 7 月 15 日**

* 在 Activity Map 擴充功能中新增 ActivityMap 捲動觸及追蹤功能 (AN-172949)
* 將 DIL 9.2 新增至 AppMeasurement (AN-182472)

## 2.14.0 版本

發行日期：**2019 年 5 月 21 日**

* 修正有多個點擊擱置時發生的追蹤器參數狀態問題。(AN-176931、AN-176629、DTM-12758)
* 已更新 AppMeasurement 以納入 Visitor.js 4.3.0 (AN-180049)

## 2.13.0 版本

發行日期：**2019 年 4 月 10 日**

* 修正許多 clearVar 回報的問題。若在追蹤器準備就緒前送出點擊，則會發生問題。當追蹤器準備就緒時，程式庫可設定已經清除或變更的變數。(AN-176931、AN-176629、DTM-12758)。

## 2.12.0 版本

發行日期：**2019 年 2 月 22 日**

* Audience Manager 模組已更新至 DIL 9.1。(AN-175255)
* GTM 安全性政策不允許 Activity Map 模組。(AN-174679)
* 改善 AppMeasurement；在 Identity Service 不核准選擇加入時，讓使用者可以選擇退出。(AN-175259)

## 2.11.0 版本

發行日期：**2019 年 2 月 11 日**

* 在 AppMeasurement 中，新增了全新 Adobe 選擇加入服務功能的支援。(AN-163546)
* 新增了在工作階段儲存體上存儲連結追蹤資料的支援。(AN-162272)
* 新增了 Audio Analytics 媒體資料流類型的支援。(AN-173265)

## 2.10.0 版本

發行日期：**2018 年 9 月 20 日**

此版本確保 [!DNL AppMeasurement] 程式庫正確提交所有連接種類的 Cookie。

* [!DNL AppMeasurement] 在 POST 期間會封鎖 Cookie 傳輸。(AN-165538)
* 終止對 XDomainRequest 的支援。(AN-165733)
* 將 [!DNL AppMeasurement] 的預設 Cookie 期限值從五年縮短為兩年。(AN-158572)
* 從代碼管理器中移除媒體模組 ([!DNL AppMeasurement]) (AN-166590)

## 2.9.0 版本

發行日期：**2018 年 5 月 24 日**

>[!NOTE]
>
>使用 [!DNL Experience Cloud] ID 服務的客戶需要具備訪客 API 3.0 或更新版本。Adobe 建議只要更新相關的程式碼程式庫 ([!DNL at.js] 等等)，就要升級至最新的 Visitor API 版本。[!DNL AppMeasurement.js]

* 更新 [!DNL AppMeasurement] 以使用更新後的訪客介面要求 ID。(AN-151483)
* 修正當連結追蹤關閉時持續寫入連結追蹤 Cookie 的問題。(AN-156332)
* 修正多次呼叫時 `registerPreTrackCallback` 和 `registerPostTrackCallback` 會破壞回呼函數簽名的問題。(AN-158566)

## 2.8.2 版本

發行日期：**2018 年 4 月 12 日**

* 更新 [!DNL AppMeasurement] 以使用更新後的訪客介面要求 ID。(AN-151483)
* 當連結追蹤關閉時持續寫入連結追蹤 cookie。(AN-156332)
* 將 [!DNL AppMeasurement] 的預設 Cookie 期限值從五年縮短為兩年。(AN-158572)

## 2.8.1 版本

發行日期：**2018 年 3 月 29 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix：(CORE-11390、CORE-10634)

## 2.8.0 版本

發行日期：**2018 年 3 月 15 日**

重新組合訪客 API 3.1.0 (AN-159524)，並包含 Hotfix：(CORE-11390、CORE-10634)

* 將 VAPI v3.1 與 [!DNL AppMeasurement] v2.8 搭配組合。(AN-158353)
* 重構資料集合端點以便進行分享。(AN-156647)
* 將請求的來回時間量度新增至 [!DNL AppMeasurement]。(AN-158343)

## 2.7.0 版本

發行日期：**2018 年 1 月 18 日**

* 終止支援 IE 6 到 IE 9
* 納入 Visitor API v3.0.0
* 納入 DIL v7.00

## 2.6.0 版本

發行日期：**2017 年 11 月 9 日**

修正呼叫 s_gl 時，[!DNL AppMeasurement] 程式庫無法每次都設為正確帳戶組合的問題。(AN-152153)

## 2.5.0 版本

發行日期：**2017 年 9 月 21 日**

* 納入 [!DNL dil.js 6.12] ([!DNL Audience Manager] 模組)
* 納入訪客 API 2.5.0。

## 2.4.0 版本

發行日期：**2017 年 8 月 17 日**

* 納入 dil.js v6.11
* 納入訪客 API 2.4.0

## 2.3.0 版本

發行日期：**2017 年 7 月 20 日**

* 修正 `s.Util.getQueryParam` 擷取 `#` 的錯誤
* 新增 `dil.js` v6.10 (AN-145701)

## 2.2.0 版本

發行日期：**2017 年 6 月 8 日**

* 新增對多重 [!DNL AppMeasurement] 具現化階層的支援。(AN-138237)
* 納入訪客 API 2.2.0 版本。(AN-144042)

## 2.1.0 版本

發行日期：**2017 年 4 月 20 日**

* 納入最新版本 `dil.js` (AN-140396)
* 新增對 `adobe_mc_ref` 參數的支援，可覆蓋頁面反向連結。(AN-131920)
* 重新納入 Visitor API 2.1.0。(AN-140873)
* 新增 `mcorgid` 參數。(AN-139586)
* 新增 cp (customerPerspective) 參數。(AN-140897)

## 2.0.0 版本

發行日期：**2017 年 3 月 9 日**

* 移到需要到更新版本 2.0.0 新的建立程序。(AN-137878)
* 將「mboxMCSDID」的處理移到追蹤呼叫發出的正確截面位置。(AN-138483)

## 1.8.0 版本

發行日期：**2017 年 1 月 19 日**

* 納入 Visitor API 2.0.0
* 重新排序函數呼叫和檢查，以便在中止檢查完成後使用 SDID。(AN-134364)
* 新增 `s.registerPreTrackCallback` 和 `s.registerPostTrackCallback` 鉤點。(AN-134567)

## 1.7.0 版本

更新日期：**2016 年 11 月 11 日**

* 納入 Visitor API 1.10.1。
* 使用 Demdex Integration Library (DIL) 6.6 更新 [!DNL Audience Manager] 模組。(AN-132065)
* 納入 Visitor API 1.9.0。(AN-132072)
* 使用 DIL 6.5 和其他設定更新 [!DNL AppMeasurement] [!DNL Audience Manager] 模組 (AN-129411)
* 包括 Visitor API 1.8.0 (AN-129887)

## 1.6.4 版本

更新日期: **2016 年 8 月 18 日**

* 更新 [!DNL AppMeasurement]，可讀取和寫入 AMCV Cookie。(AN-127098)
* 納入 Visitor API 1.7.0。

>[!NOTE]
>
>另請參閱下列 [!DNL JavaScript] 1.6.3 版本的版本注意事項中，對 Experience Cloud ID 服務的更新要求。

## 1.6.3 版本

更新日期: **2016 年 8 月 4 日**

* 修正 [!DNL AppMeasurement] 提前終止請求連線的問題。(AN-126448)

>[!IMPORTANT]
>
>1.6.0 版本 [!DNL Experience Cloud] ID 服務「需使用」**[!DNL AppMeasurement] 供 [!DNL JavaScript] 1.6.3 版本或更新版本使用。如果您想要升級為 1.6.0 版本的 Experience Cloud ID Service，請務必使用 [!DNL AppMeasurement] 程式碼 1.6.3 版本或更新版本。

## 1.6.2 版本

發行日期：**2016 年 7 月 21 日**

* 已納入 Visitor API 1.6.0。
* 修正導致 [!DNL AppMeasurement] 在訪客 API 中呼叫了錯誤隱藏方法的問題。(AN-126006)
* 修正引發此 [!DNL JavaScript] 錯誤的問題:「屬性僅在 v:image 上有效」。(AN-124009)

## 1.6.1 版本

發行日期：**2016 年 6 月 16 日**

* 納入 Visitor API 1.5.7。
* 已修正處理 Firefox 中無法引發完成事件的連結點擊追蹤功能。

## 1.6 版本

發行日期：**2016 年 4 月 21 日**

* [!DNL AppMeasurement] Activity Map 模組已整合至 [!DNL AppMeasurement] 標準模組，因此您僅需參考一個 [!DNL .js] 檔案。此外，預設已啟用「Activity Map」追蹤。(AN-112689)
* 修正 [!DNL AppMeasurement] 中查詢字串變數順序的截斷問題，因此 *`pageURLRest`* 會顯示於最後。(AN-114647)

## 1.5.4 版本

發行日期：**2016 年 3 月 17 日**

* 納入 Visitor API 1.5.4
* 支援 Visitor API 1.5.4+ 選擇退出功能

## 1.5.3 版本

發行日期：**2016 年 1 月 21 日**

* 修正使用 POST 來追蹤呼叫時，[!DNL Audience Manager] 模組的處理方式。(AN-115381)
* 已將剩餘的頁面 URL (「-g」) 移至追蹤請求查詢字串的尾端。(AN-114647)

## 1.5.2 版本

發行日期：**2015 年 11 月 5 日**

* 納入 Visitor API 1.5.3。
* 修正 IE 11 對 URL 截斷 2047 的偵測功能 (AN-114914)

## 1.5.1 版本

發行日期：**2015 年 9 月 17 日**

* 納入 Visitor API 1.5.2
* 更新 [!DNL Audience Manager] 模組以使用 AAM DIL 6.2 - 從 Visitor API.js 取得客戶 ID 並在呼叫給 AAM 時將其傳入。(AN-104978)

## 1.5 版本

發行日期：**2015 年 6 月 18 日**

* Visitor API 1.5 的支援 (使用 *`getCustomerIDs`* 方法收集客戶 ID 及已驗證狀態，並針對資料彙集要求傳送 ID)。
* 修正 **[!UICONTROL AudienceManagement]** 模組 (DIL 6.1) 中重複目的地 iframe 的建立
* 已修正 1.4.5 版本中說明的已知問題。

## 1.4.5 版本

發行日期：**2015 年 5 月 21 日**

* 從 iOS SDK 4.5 版本開始，新的 iOS 擴充功能可讓您從 Apple Watch 應用程式、「今天」小工具、「照片編輯」小工具和所有其他 iOS 擴充應用程式中收集用量資料。請參閱行動服務使用手冊中的 [iOS 擴充功能實作](https://experienceleague.adobe.com/docs/mobile-services/ios/ios-ext/ios-ext.html?lang=zh-Hant)。
* 從 Android SDK 4.5 版本開始，新的 Android 擴充功能可讓您透過 Android 穿戴式裝置應用程式中收集資料。請參閱行動服務使用手冊中的 [Android 穿戴式裝置](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/android-wearable.html?lang=zh-Hant)。
* 納入 Visitor API 1.4.
* 已更新 AudienceManagement 模組以使用 DIL 6.0 版本。

>[!NOTE]
>
>**已知問題**：在訪客 API / [!DNL AppMeasurement] [!DNL Audience Manager] 模組整合中，有可發佈在 IE6-9 中提出之 iFrame 要求的兩個目的地：`//fast.<subdomain>.demdex.net/dest5.html` 和 `//fast.<subdomain>.demdex.net/dest4.html`。如同其他瀏覽器的情況，正確的行為是只載入 `//fast.<subdomain>.demdex.net/dest5.html`。

## 1.4.4 版本

發行日期：**2015 年 4 月 16 日**

* 您現在可使用生命週期量度來納入自訂內容資料的變數。
* 您現在可在 PhoneGap 中使用 `trackBeacon` 和 `clearCurrentBeacon` 呼叫。
* 進行微幅修正，以在 `trackLight` 呼叫後清除小型伺服器呼叫設定檔 ID。

## 1.4.3 版本

發行日期：**2015 年 2 月 19 日**

* 將所有延遲追蹤呼叫的處理改為一致，以修正延遲期間的備份變數問題，例如已點按物件。
* 第一個追蹤呼叫後不再進行自動反向連結追蹤，以在第一個追蹤呼叫前手動設定&#x200B;*`s.referrer`*&#x200B;時，以免第二個、第三個...追蹤呼叫 (通常是連結追蹤) 重複計算反向連結。
* 已更新分送 Zip 檔，現在包含 Visitor API 1.3.5。

## 1.4.2 版本

發行日期：**2015 年 1 月 15 日**

* 修正 WebKit 轉譯前處理，防止追蹤未檢視的轉譯前頁面。
* 更新分送 Zip 檔，以包含 Visitor API 1.3.4 以及 **[!UICONTROL AudienceManagement]** 模組 (包含 DIL 5.5 版本)。

## 1.4.1 版本

發行日期：**2014 年 9 月 18 日**

* 新增 `tagContainerMarker` 變數，讓實作可指定最多 4 個字元附加至版本字串與其他破折號分隔字元。此功能可用於動態標籤管理。

   ```js
   // JavaScript
   s.tagContainerMarker = "D1.0";
   
   // Data Collection request
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   這 4 個字元僅限使用 URL 檔案路徑允許的字元，例如英數字元和句號。

* 在利用 H 程式碼加上雙標籤的頁面中，啟用強制連結追蹤 (Webkit 瀏覽器的預設) 時，在自動連結追蹤 (下載和退出) 期間可能會發生重複循環，這個問題已經修正。此外，在自動連結追蹤周圍新增一般防護以避免類似的重複循環。此防護可限制自動連結追蹤每 10 秒重複點擊&#x200B;*相同*&#x200B;物件一次。此防護僅適用於自動連結追蹤，因此，手動連結追蹤 (s.tl) 呼叫不在此限。此外，點擊不同物件也不受此防護影響，並且將進行追蹤。
* 已修正需要延遲時點擊物件的處理。
* 如果訪客 API 尚未取得需要的值，從連結 onclick 功能呼叫 s.t 時，會導致頁面檢視計數倍增，這個問題已經修正。
* HTTP POST 支援。

   >[!IMPORTANT]
   >
   >若要讓 [!DNL Analytics] 呼叫使用 POST 方法，而不是 [!DNL AppMeasurement] 中的 GET 方法 (解決 [IE 中的截斷 URL](https://helpx.adobe.com/tw/analytics/kb/shortening-image-request-urls.html) 的方法)，您至少必須將訪客 ID 服務的實作用於 Experience Cloud。

## 1.4 版本

發行日期：**2014 年 8 月 21 日**

*  15 版本中不再針對移除追蹤瀏覽器外掛程式 (`p` 查詢參數) 做為外掛程式進行報告。
* 在下載 Zip 中新增 **[!UICONTROL AudienceManagement]** 模組。
* 已新增對其他 eVar (76 - 250) 和事件 (101-1000) 的支援。

>[!NOTE]
>
>H-Code 不支援其他 eVar 和事件。

## 1.3.2 版本

發行日期：**2014 年 6 月 19 日**

* 修正處理訪客 API 欄位 (如舊版 [!DNL Analytics] 訪客 ID) 的完成和等待標幟時會發生錯誤的問題。
* 支援訪客 ID 服務 1.3 的新功能。

## 1.3.1 版本

發行日期：**2014 年 5 月 22 日**

* [!DNL JavaScript] `s_gi` 適用的 [!DNL AppMeasurement] 功能無法正確地找到使用 H-Code `s_gi` 所建立的例項。請注意，此問題只有影響到某些雙重標籤實作，意即 [!DNL JavaScript] 適用的 [!DNL AppMeasurement] 和 H-Code 出現在具備個別例項的相同頁面，而報表套裝也使用 `s_gi` 尋找例項。

## 1.3 版本

發行日期：**2014 年 4 月 17 日**

* 支援 [Experience Cloud 訪客 ID 服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)。

## 1.2.4 版本

發行日期：**2014 年 3 月 13 日**

* 已修正心率視訊的錯誤。

## 1.2.3 版本

發行日期：**2014 年 2 月 20 日**

* 已修正心率視訊的錯誤。

## 1.2.2 版本

發行日期：**2014 年 2 月 6 日**

* 修正 [!DNL Audience Manager] DIL 模組的相容性問題。[!DNL Audience Manager] 客戶也必須更新至 DIL 模組的 4.8 版本。

## 1.2.1 版本

發行日期：**2013 年 11 月 15 日**

* 修正用於心率視訊測量的頁面事件。

## 1.2 版本

發行日期：**2013 年 11 月 14 日**

* 新增對[心率視訊測量](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hant)的支援。
* 已新增 `VisitorAPI.js` 以支援[訪客 ID 服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)。

## 1.1.1 版本

* 防止 Opera 瀏覽器針對開頭為 &quot;opera:&quot; 的連結 (&quot;opera:&quot; 類似於其他瀏覽器中的 &quot;about:&quot; 和 &quot;chrome:&quot;)，傳送連結追蹤呼叫。
* 新增 `alt=""` 至所有影像物件，以遵循「視訊與通訊無障礙法」(Accessible Video and Communications Act)。

## 1.1 版本

發行日期：**2013 年 9 月 18 日**

* 修正在 `head` 標籤中放置庫和頁面程式碼的支援。
* 已新增遺漏模組 `onLoad` 支援。

## 1.0.3 版本

發行日期：**2013 年 8 月 15 日**

* 新增支援透過 Adobe 標籤管理進行部署。
* 修正 [!DNL AppMeasurement] 物件上無法設定階層變數的問題。

## 1.0.2 版本

發行日期：**2013 年 7 月 18 日**

* 自動連結追蹤現在會忽略雜湊/片段。以前由於下列 URL 的整個 `.pdf` 結尾為 `href`，所以會自動加以追蹤：

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   現在會忽略雜湊/片段，所以只在檔案名稱結尾為符合的副檔名時才會追蹤連結。

## 1.0.1 版本

發行日期：**2013 年 5 月 23 日**

代碼管理器現在提供新版 [!DNL JavaScript] [!DNL AppMeasurement] 程式庫。本程式庫提供與 [!DNL s_code.js] 相同的核心功能，但可更加輕鬆快速地在行動版與桌面版網頁上使用。

* 執行速度較 H.25 程式碼快 3 到 7 倍。
* 未壓縮大小僅為 21k，而採用 gzipped 壓縮的大小為 8k (H.25 程式碼的未壓縮大小為 33k，而採用 gzipped 的大小為 13 k)。
* 原生支援，以便取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。
* 輕便快速且功能強大，無論在行動版網頁或桌面完整版網頁皆可輕鬆使用，可讓您在所有的網站環境中使用單一程式庫。
