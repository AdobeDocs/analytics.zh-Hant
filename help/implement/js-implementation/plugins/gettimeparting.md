---
description: getTimeParting 外掛程式會在自訂變數中填入小時、星期幾、週末與工作日等自訂變數。Analysis Workspace 提供立即可用的時間分段維度。當 Analysis Workspace 之外的其他 Analytics 解決方案需要使用時間分段維度時，應使用此外掛程式。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getTimeParting

getTimeParting 外掛程式會在自訂變數中填入小時、星期幾、週末與工作日等自訂變數。Analysis Workspace 提供立即可用的時間分段維度。當 [!UICONTROL Analysis Workspace] 之外的其他 Analytics 解決方案需要使用時間分段維度時，應使用此外掛程式。

此外掛程式會擷取使用者網頁瀏覽器中可用的日期與時間資訊。它會從這項資訊中取得一天中的某小時與一週中的某天。接著，它會將這項資料轉換成您所選擇的時區。它也會反映日光節約時間。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式程式碼 {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**設定區段**

將下列程式碼放入 [!DNL s_code.js] 檔案中標示為 [!UICONTROL CONFIG SECTION] 的區域中，並依照下列說明進行必要的更新。

`s._tpDST` - DST 值的陣列。陣列結構的格式如下: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

南半球用戶端注意: 在陣列中，DST 值為 DST start, DST end。

北半球用戶端注意: 在陣列中，DST 值為 DST end, DST start。

**參數**

```js
var tp = s.getTimeParting(h,z);
```

* h = (必要) 半球 - 指定您要將時間轉換為哪個半球。這是 'n'或 's' 的值。這是用來決定如何使用傳遞的 DST 陣列。如果傳遞 'n'，則外掛程式會在 DST 開啟時使用日期。如果傳遞 's'，則外掛程式會在 DST 關閉時使用日期。
* z = (選用) 時區 - 如果您想要資料根據特定時段，則該時段將需要指定為不同於這裡 GMT 的時間。請注意，在非 DST 期間，這應該是 GMT。如果未指定任何值，則它會預設為 GMT (例如，'-5' 表示美國東部時間)

**傳回**

以分鐘層次及一週中的某天傳回連結的時間值，例如:

```
8:03 AM|Monday
```

然後，您可以使用[分類](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)，將瀏覽分組為不同時段。例如，您可以在 Classification Rule Builder 中設定一個規則，將 9:00 AM 與 9:59 AM 之間的瀏覽分裝為 "9:00 AM - 10:00 AM"。作為分類的替代方案，您可以提供額外的用戶端邏輯，以 JavaScript 分裝瀏覽。

**範例呼叫**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**外掛程式區段**


將下列程式碼新增至 [!UICONTROL  檔案中的 ]PLUGINS SECTION[!DNL s_code.js]。

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**附註**

* 在部署至生產環境前，請務必對外掛程式安裝進行測試，以確保資料收集可如預期運作。
* 必須設定組態變數，外掛程式才能正常運作。

