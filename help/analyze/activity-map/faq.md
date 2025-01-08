---
title: Activity Map 常見問題
description: 與Activity Map相關的常見問題。
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 15%

---

# Activity Map 常見問題

與Activity Map相關的常見問題。

+++如何授與Activity Map許可權？

在[Adobe Admin Console](/help/admin/admin-console/home.md)中處理使用Activity Map及其相關維度的許可權。

Activity Map所需的[許可權專案](/help/admin/admin-console/permissions/product-profile.md)包括：

* **[!UICONTROL Analytics工具]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL 分析工具]** > **[!UICONTROL 區段發佈]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map捲動範圍]**
* **[!UICONTROL Dimension]** > **[!UICONTROL 各地區的Activity Map連結]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map地區]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map連結]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map頁面]**

如需詳細資訊，請參閱[Analytics工具的產品設定檔許可權](/help/admin/admin-console/permissions/analytics-tools.md)。

+++

+++所有Analytics客戶都可以存取Activity Map嗎？

凡是擁有Adobe Analytics Standard、Premium和Ultimate合約的組織皆可存取Activity Map。 這些合約型別代表大多數Adobe Analytics客戶。

+++

+++Activity Map如何支援單頁應用程式(SPA)？

每隔幾秒，Activity Map會掃描網頁以尋找變更。 Activity Map會在頁面上尋找新內容而不需要重新載入，但此新內容一律會歸因於第一個頁面維度值。

* Activity Map 會查看它所知道的連結的可見度是否已變更。如果發現可見度有變更，則該連結的「頁面上連結」表格的「存在」欄會以[!UICONTROL 已顯示]或[!UICONTROL 已隱藏]來更新。

* 當使用者互動建立新內容時，AppMeasurement判定為連結的任何新元素都會新增到頁面]上的[!UICONTROL 連結表格中。 Activity Map 會傳送包含這些新連結的新資料要求。傳回資料要求時，新連結會出現在[!UICONTROL 頁面]上的連結表格中。

+++

+++Activity Map是否提供已檢視但未點按之連結的資料？

否，Adobe不會自動追蹤僅供檢視的連結。

+++

+++Activity Map支援哪些瀏覽器和版本？

Activity Map 支援最新版本的最新瀏覽器。

+++

+++Activity Map是否會增加伺服器呼叫？

Activity Map 本身不會傳送伺服器呼叫。反之，Activity Map內容資料變數會包含在後續頁面上的Analytics頁面檢視呼叫中。 不過，網路SDK上某些舊版的Activity Map會針對Activity Map資料傳送個別呼叫。 如果您使用最新版的Web SDK，Activity Map資料將會與以下事件合併。

+++

+++為何覆蓋圖中遺漏了某些排名數字？

某些連結（例如功能表內的連結）會隱藏在頁面中。 因此，其對應的連結覆蓋圖不會顯示。 排名會計算頁面上所有連結，包括隱藏的連結。

+++

+++「全部連結」報表中的連結排名是如何決定的？

* **在「漸層」和「氣泡」模式中**：量度資料行決定等級。 對於具有相同量度值的連結，再進一步根據連結ID的字母順序來排名。
* **在「獲益者和損失者」模式中**：獲益的百分比欄決定排名。 對於具有相同獲益的連結，再進一步根據連結 ID 的字母順序來排名。

+++

+++Activity Map如何處理使用多個報表套裝的頁面？

依預設，Activity Map會使用與頁面第一個標籤相關聯的報表套裝。 您可以透過&#x200B;**[!UICONTROL Activity Map設定]** > **[!UICONTROL 其他]**&#x200B;索引標籤選取其他報表套裝。

+++

+++Activity Map在頁面上掃描Adobe Analytics多久了？

在頁面完成事件後，Activity Map 會掃描長達 20 秒以查看 Adobe Analytics 是否存在。

+++

+++Activity Map如何處理動態內容？

Activity Map 每 2 秒檢查一次，查看是否有如下所示的網頁狀態變更：

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容為隱藏或顯示，擴充功能會自動將受影響的連結狀態（以及覆蓋圖），從隱藏變更為顯示，或從顯示變更為隱藏。 如果插入新內容，應用程式會擷取關聯的連結、提取分析資料，並新增這些連結的覆蓋圖。

+++

+++頁面流量報表是根據哪個量度？

所有顯示的資料都是以頁面檢視次數為準。

+++

+++我是否可透過資料摘要匯出Activity Map資料？

是。Activity Map使用的[資料摘要資料行](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)為：

* Activity Map連結： `clickmaplink`
* Activity Map頁面： `clickmappage`
* Activity Map區域： `clickmapregion`
* 依地區Activity Map連結： `clickmaplinkbyregion`

+++

+++區段是否適用於即時模式？

否，區段不適用於即時模式。

+++

+++Activity Map是否可與虛擬報表套裝相容？

是。不過，由於虛擬報表套裝本身限制，Activity Map的即時模式與虛擬報表套裝不相容。

+++

+++如何停用Activity Map？

停用Activity Map的方法取決於您的實作型別：

* **Web SDK擴充功能**：在擴充功能組態設定中，取消勾選&#x200B;**[!UICONTROL 收集內部連結點按次數]**、**[!UICONTROL 收集外部連結點按次數]**&#x200B;和&#x200B;**[!UICONTROL 收集下載連結點按次數]**&#x200B;方塊。
* **Web SDK JavaScript資料庫**：將[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)設為`false`。
* **Analytics擴充功能**：在擴充功能組態設定中，取消勾選標示為&#x200B;**[!UICONTROL 使用Activity Map]**&#x200B;的方塊。
* **AppMeasurement**：移除或註解`AppMeasurement.js`中的Activity Map模組，或使用空白內文覆寫模組函式呼叫：

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++使用Activity Map覆蓋的系統需求為何？

您可以將最新版本的Chrome、Edge或Firefox搭配Activity Map擴充功能使用。

+++

+++將Activity Map用於個人識別資訊時，必須考量哪些事項？

考慮以下可使用Activity Map收集個人識別資料的情況：

* **電子郵件連結**：如果可以按一下電子郵件地址來開啟使用者的郵件使用者端，則Activity Map可以收集被按下的電子郵件地址。
* **使用者ID連結**：訪客登入後，Activity Map可以記錄任何包含訪客使用者ID的連結。
* **敏感資訊連結**：若為金融機構，若為連結，且訪客點按該連結，則可追蹤帳號等敏感資訊。
* **包含個人資訊的連結**：對於醫療保健網站，連結可以包含個人資訊。 如果訪客按一下這些連結，Activity Map會收集該連結文字。

+++

+++Activity Map預設會追蹤哪些資料？

Activity Map會追蹤下列元素：

* 具有`href`屬性的`<a>`或`<area>`標籤。 預設不會追蹤錨點標籤連結(`#`)。
* 設定`s_objectID`變數的`onclick`屬性
* 含有值或子文字的`<input>`標籤或`submit`按鈕
* 具有型別`image`和`src`屬性的`<input>`標籤
* 沒有屬性`type="button"`的`<button>`標籤。 若要追蹤`<button>`標籤，請考慮改用`role="button"`或`submit="button"`等屬性。

+++

+++Activity Map自動追蹤的連結有哪些範例？

以下範例說明Activity Map擁有追蹤連結所需的所有資訊。

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Activity Map不會自動追蹤的連結有哪些範例？

* 錨點標籤沒有有效的`href`
* [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md)或[`tl()`](/help/implement/vars/functions/tl-method.md)方法皆不存在
* 表單輸入元素上缺少`src`屬性

以下是Activity Map不會追蹤點按的一些範例：

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
