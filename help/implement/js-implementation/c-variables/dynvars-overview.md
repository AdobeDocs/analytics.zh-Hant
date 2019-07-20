---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實施
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
seo-title: 動態變數
solution: Analytics
subtopic: 變數
title: 動態變數
topic: 開發人員和實施
uuid: 1c6db083-570e-4bc4-858d-84cf46e7ec8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 動態變數

動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。

同時在多個變數中擷取相同的資料 (例如促銷活動追蹤程式碼) 時，動態變數可派上用場。當不同的報告提供了獨特而重要的度量時，這會是常用的作法。例如，在[!UICONTROL 自訂轉換]變數與[!UICONTROL 自訂流量]變數中擷取內部搜尋關鍵字，可讓您分別檢視與這些關鍵字相關聯的[!UICONTROL 收入]與[!UICONTROL 每週獨特訪客]度量。.

在不同的報告條件下檢視資料時，也可利用動態變數。您可以在多個具有不同配置與 Cookie 有效期設定的 eVar 中，擷取某個促銷活動追蹤程式碼。這可讓使用者自行選擇適當方式來歸納這些促銷活動的轉換度量。

>[!NOTE]
>
>動態變數不受Cookie(s_ cc、s_ sq、s_ fid、s_ vi和任何由外掛程式設定的Cookie)所支援。`D=<cookie value>`您無法使用。

動態變數能夠直接擷取多個變數中的長資料字串，而無需真正重複傳入冗長的字串，是其一大優點。有些瀏覽器設有 HTTP GET 要求 (包括 Adobe 影像要求) 的長度上限。若數個變數間有重複的資料，使用動態變數將可減少 Adobe 伺服器要求的長度，而確保能夠擷取到所有資料。.

在產生於頁面檢視的 Adobe 影像要求中，若您使用動態變數將[!UICONTROL 自訂流量 ] 的值複製到[!UICONTROL 自訂轉換 ]，您將會看 `v1=D=c1`1=1。若 eVar1 接收到先前位於要求中的值，Adobe 的伺服器將會在資料處理期間動態地將[!UICONTROL 自訂流量 1] 的值複製到[!UICONTROL 自訂轉換 1]。因此，原先使用[!UICONTROL 自訂流量 1] 傳遞的值，也會出現在[!UICONTROL 自訂轉換 1] 報告中。

動態變數的傳遞方式，是先將一個變數設為所需值，再將其他變數設為 `D=[variable abbreviation]`。For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). 動態變數可以從下列位置提取資料:

* 其他查詢字串變數
* HTTP 標題 (Cookie HTTP 標題除外)

若要建立動態變數，請新增一個特殊首碼至值開頭。預設首碼為 "D="。有兩種標記動態變數的方法:

* 使用預設首碼 D= (例如: s.prop1="D=User-Agent" )
* 對於非 JavaScript 實施，您可以使用 "D" 查詢字串變數來定義自訂首碼。For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

所使用的變數縮寫必須與傳入影像要求中的變數參數名稱相符。有些變數針對不同的案例能夠使用多種接受的參數。For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

下列資訊適用於動態變數:

* 動態變數可與各種版本的 AppMeasurement 程式碼搭配使用。
* 動態變數區分大小寫。
* 動態變數支援以引號括住的常值字串。
* 動態變數更換發生在處理規則、VISTA 及其他處理程序前。
* 動態變數首碼 "D=" 必須位於變數值開頭，而非中間位置。For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* 如同其他各種實施技術，Adobe 建議在將動態變數實施部署至生產環境前，務必要先在開發環境中充分測試。由於在用戶端除錯工具中不會顯示所複製的完整字串，請檢閱受影響的 Analytics 報表，以確認實施是否成功。
* 在具有不同長度上限的變數間複製值時請留意到，若複製的值超過目標變數的長度上限，將會導致截斷。例如，[!UICONTROL 自訂流量]變數的長度上限為 100 個字元，而[!UICONTROL 自訂轉換]變數的上限為 255 個字元。使用動態變數將 150 字元的值從 s.eVar1 複製到 s.prop1 時，此值在[!UICONTROL 自訂流量]報表中將會截斷為 100 個字元。

## 動態變數範例 {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

可在 Analytics 中使用的動態變數範例。

在產生於頁面檢視的 Adobe 影像要求中，若您使用動態變數將[!UICONTROL 自訂流量 ] 的值複製到[!UICONTROL 自訂轉換 ]，您將會看 `v1=D=c1`1=1。若 eVar1 接收到先前位於要求中的值，Adobe 的伺服器將會在資料處理期間動態地將[!UICONTROL 自訂流量 1] 的值複製到[!UICONTROL 自訂轉換 1]。因此，原先使用[!UICONTROL 自訂流量 1] 傳遞的值，也會出現在[!UICONTROL 自訂轉換 1] 報告中。

Note that the `D=[variable]` value should be in quotes. Analytics 程式碼會將其視為字串。字串在傳入至 Analytics 時會進行 URL 編碼 (如同您在 DigitalPulse 除錯程式或類似的公用程式中檢視要求時所見)。這是正常行為。Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>使用影像要求追蹤連結時，必須定義連結類型(download= lnk_ d、exit= lnk_ e或自訂link= lnk_ o)，也必須定義連結URL/名稱(pev2)。Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>動態變數不受Cookie(s_ cc、s_ sq、s_ fid、s_ vi和任何由外掛程式設定的Cookie)所支援。`D=<cookie value>`您無法使用。

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 範例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1=「D= pageName」 </code>
  </td> 
   <td colname="col2"> <p>擷取 eVar1 中的 pageName 值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= v2+」：「+ c2'&amp; amp；nbsp； </code>
  </td> 
   <td colname="col2"> <p>將 eVar2:prop2 串連至 prop1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1= s. eVar1=「D= g」&amp; amp；nbsp； </code>
  </td> 
   <td colname="col2"> <p>將頁面 URL 同時傳遞至 prop1 和 eVar1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1=「D= v0」 </code>
  </td> 
   <td colname="col2"> <p>擷取 eVar 1 中的促銷活動。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= User-Agent+」；-「+接受語言」 </code>
  </td> 
   <td colname="col2"> <p>串連使用者代理並接受 prop1 中的語言標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop1=「D= User-Agent」 </code>
  </td> 
   <td colname="col2"> <p>擷取 eVar 1 中的使用者代理， </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 影像請求範例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">/b/ss/rsid/？loc= Home&amp; D=~~&amp; c1=~~ v0/b/ss/rsid/？loc= Home&amp; D=~~&amp; c1=~~促銷活動/b/ss/rsid/？loc= Home&amp; c1= D%3dv%3d是/b/ss/rsid/嗎？loc= Home&amp; c1=%5b%5bv0%5d%5d%5b </code>
  </td> 
   <td colname="col2"> <p>將 prop1 設為促銷活動的 4 種方法 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/？loc= Home&amp; D=~~&amp; c2=~~ x-up-subno </code>
  </td> 
   <td colname="col2"> <p> 將 x-up-subno 標題提取至 prop2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c= D%3DUser-Agent </code>
  </td> 
   <td colname="col2"> <p> 將 prop1 設為動態變數，填入 HTTP 標題 User-Agent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22測試%22 </code>
  </td> 
   <td colname="col2"> <p> 將 prop1 設為動態變數，填入字串「test」。利用 + 運算元進行串連時這會更有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22US%3A%20.22Buser-Agent </code>
  </td> 
   <td colname="col2"> <p> 將 prop1 設為動態變數，填入首碼為「UA:」的 User-Agent。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; vid= D%3DX-TM-ANDID </code>
  </td> 
   <td colname="col2"> <p> 本範例會搜尋唯一標題，在此例中是 X-TM-ANTID。 </p> </td> 
  </tr> 
 </tbody> 
</table>
