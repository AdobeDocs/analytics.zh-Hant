---
description: 重新導向無須使用者互動便可將瀏覽器指向新位置。重新導向會在網頁瀏覽器 (用戶端重新導向) 或網頁伺服器 (伺服器端重新導向) 上執行。
keywords: Analytics 實作
title: 重新導向與別名
feature: Implementation Basics
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 99%

---

# 重新導向與別名

重新導向無須使用者互動便可將瀏覽器指向新位置。重新導向會在網頁瀏覽器 (用戶端重新導向) 或網頁伺服器 (伺服器端重新導向) 上執行。

## 重新導向與別名 {#aliases}

重新導向無須使用者互動便可將瀏覽器指向新位置。重新導向會在網頁瀏覽器 (用戶端重新導向) 或網頁伺服器 (伺服器端重新導向) 上執行。

由於重新導向不需要任何使用者操作，因此使用者通常不會察覺正在執行重新導向。唯一可指出發生了重新導向的位置，是瀏覽器的網址列。網址列會顯示與瀏覽器最初請求的連結不同的 URL。

重新導向雖然只有兩種類型，但有許多方式可以實施。例如，用戶端重新導向的發生，可能是因為使用者要瀏覽器開啟的網頁中包含將瀏覽器重新導向至其他 URL 的指令碼或特殊 HTML 程式碼。伺服器端重新導向的發生，則可能是因為頁面包含伺服器端指令碼，或網頁伺服器已設為將使用者導向其他 URL。

## Analytics 和重新導向 {#aa-redirects}

[!DNL Analytics] 會從瀏覽器收集一些資料，因此需仰賴特定瀏覽器屬性來運作。其中「反向連結 URL」(或 referrer) 與「目前 URL」兩項屬性可透過伺服器端重新導向來變更。瀏覽器由於會辨識出請求的是某個 URL，但傳回的卻是不同的 URL，因此會清除「反向連結 URL」。結果，反向連結 URL 會空白，而 [!DNL Analytics] 可能會報告該頁面沒有反向連結存在。

## 範例：沒有重新導向的瀏覽 {#browse-without}

假設有下面這種使用者未遇到重新導向的情況:

1. 使用者在瀏覽器中前往 `www.google.com`，並在搜尋欄位中輸入「discount airline tickets」，然後按一下&#x200B;**[!UICONTROL 搜尋]**&#x200B;按鈕。
1. 瀏覽器顯示的搜尋結果包含您網站的連結 [!DNL https://www.example.com/] 。顯示搜尋結果後，瀏覽器的網址列顯示了使用者在搜尋欄位中輸入的搜尋詞彙 (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`)。請注意，搜尋詞彙已納入到緊接在 `https://www.google.com/search?`.
1. 使用者按一下您的假設網站的連結 [!DNL https://www.example.com/] 。當使用者點按此連結並開啟了 [!DNL example.com] 網站時，[!DNL Analytics] 會使用 JavaScript 收集反向連結 URL (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) 和目前的 URL (`https://www.example.com/`)。
1. [!DNL Analytics] 會在不同的報表中報告在此互動期間收集到的資訊，例如[!UICONTROL 反向連結網域]、[!UICONTROL 搜尋引擎]和[!DNL Search Keywords]。

## 範例：有重新導向的瀏覽 {#browse-with}

重新導向可能會使瀏覽器忘掉真正的反向連結 URL。假設有下列情況：

1. 使用者在瀏覽器中前往 `https://www.google.com`，並在搜尋欄位中輸入 *discount airline tickets*，然後按一下&#x200B;**[!UICONTROL 搜尋]**&#x200B;按鈕。
1. 瀏覽器視窗的網址列顯示了使用者在搜尋欄位 `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` 中輸入的搜尋詞彙。請注意，搜尋詞彙已納入到緊接在 `https://www.google.com/search?`。瀏覽器也會顯示一個包含搜尋結果的頁面，內含您其中一個網域名稱的連結: [!DNL https://www.flytohawaiiforfree.com/] 。此&#x200B;*虛名*&#x200B;網域已設定成將使用者重新導向至 `https://www.example.com/`。
1. 使用者點按連結 `https://www.flytohawaiiforfree.com/` 後，即會被伺服器重新導向至您的主要網站 `https://www.example.com`。進行重新導向時，對 [!DNL Analytics] 資料收集具有重要性的資料會遺失，因為瀏覽器會清除反向連結 URL。因此，[!DNL Analytics] 報表 (例如[!UICONTROL 反向連結網域]、[!UICONTROL 搜尋引擎]、[!UICONTROL 搜尋關鍵字]) 中所使用的原始搜尋資訊將會遺失。

## 實作重新導向 {#implement}

若要透過重新導向擷取 [!DNL Analytics][!DNL AppMeasurement] 資料，必須對程式碼進行四項小幅度變更，以建立重新導向與「JavaScript 適用的 」檔案。

完成下列步驟，可保留原始反向連結 (例如前述案例中的 `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) 傳至您網站的資訊:

## 設定反向連結覆寫 JavaScript 程式碼 {#override}

下列程式碼片段顯示兩個 JavaScript 變數: *`s_referrer`* 和 *`s_pageURL`*。此程式碼會放置在重新導向的最終登陸頁面上。

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>請僅在頁面上設定 *`s.referrer`* 一次。若設定次數超過一次，且一併設定受追蹤的每個追蹤呼叫或每個連結點擊，則會使反向連結及相關維度 (例如搜尋引擎和關鍵字) 重複計算為兩次。

## 使用 getQueryParam 重新導向 {#getqueryparam}

使用 [!UICONTROL getQueryParam] 雖然可讓您輕鬆在 [!DNL Analytics] 變數中填入查詢字串值，但它必須與暫存變數一起實施，才不會在查詢字串為空時覆寫合法的反向連結。使用 [!UICONTROL getQueryParam] 的最佳方式是以下列假程式碼的方法連結 [!UICONTROL getValue] 外掛程式。

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## 修改重新導向機制 {#modify}

由於瀏覽器會移除反向連結 URL，因此您必須設定可處理重新導向的機制 (例如網站伺服器、伺服器端程式碼、用戶端程式碼)，以傳送原始反向連結資訊。如果您也想記錄別名連結 URL，則這項資訊也必須傳送至最終登陸頁面。使用&#x200B;*`s_pageURL`*&#x200B;變數覆寫目前的URL。

由於有許多方式可實作重新導向，因此您應向網頁營運團隊或線上廣告合作夥伴確認，以找出您網站上執行重新導向的特定機制。

## 擷取原始反向連結 {#original}

在正常情況下，[!DNL Analytics] 將會從瀏覽器的 [!UICONTROL document.referrer] 屬性取得反向連結 URL，並從 [!UICONTROL document.location] 屬性取得目前的 URL。 您可以將值傳遞至 *`referrer`* 和 *`pageURL`* 變數，藉此覆寫預設處理作業。藉由將值傳至反向連結變數，您可以指示 [!DNL Analytics] 應忽略 [!UICONTROL document.referrer] 屬性中的反向連結資訊，而使用您所定義的替代值。

因此，登陸頁面的最終版本將必須包含下列程式碼，以更正「折扣機票」情境所產生的問題。

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaiiforfree.com"
```

## 使用 Adobe Debugger 驗證反向連結 {#verify}

執行測試，以確認正在擷取反向連結、原始 URL (*`s_server`*) 和促銷活動變數。

在 [Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hant) 中，這些變數將以下列參數的形式表示。

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL 或查詢字串值</b> </th> 
   <th class="entry"> <b>DigitalPulse 除錯程式中顯示的值</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>原始反向連結 </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=discount+airline+tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>頁面 URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>若使用 <span class="varname">pageURL</span> 變數，此值將出現在 DigitalPulse Debugger 中。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最終登陸頁面 URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>若使用 <span class="varname">pageURL</span> 變數，此值將「不會」出現在 DigitalPulse Debugger 中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

除錯程式所顯示的文字應對應於下列範例:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/20XX 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

在驗證 Adobe [!UICONTROL Debugger] 顯示了這些變數後，進一步確認搜尋詞彙與原始反向連結網域 (在重新導向之前) 正在報表中註冊流量，必定會很有幫助。
