---
description: getValOnce 外掛程式可防止指定的變數設為先前定義的值。它會使用 Cookie 來判斷變數最後顯現的值。若目前的值與 Cookie 值相符，則會以空白字串覆寫變數，再將其傳送至 Adobe 的處理伺服器。此外掛程式可用來防止轉換變數例項數因為使用者重新整理頁面或點按「上一頁」按鈕而膨脹。
keywords: Analytics 實施
seo-description: getValOnce 外掛程式可防止指定的變數設為先前定義的值。它會使用 Cookie 來判斷變數最後顯現的值。若目前的值與 Cookie 值相符，則會以空白字串覆寫變數，再將其傳送至 Adobe 的處理伺服器。此外掛程式可用來防止轉換變數例項數因為使用者重新整理頁面或點按「上一頁」按鈕而膨脹。
seo-title: getValOnce
solution: Analytics
subtopic: 外掛程式
title: getValOnce
topic: 開發人員和實施
uuid: 82Fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getValOnce

getValOnce 外掛程式可防止指定的變數設為先前定義的值。它會使用 Cookie 來判斷變數最後顯現的值。若目前的值與 Cookie 值相符，則會以空白字串覆寫變數，再將其傳送至 Adobe 的處理伺服器。此外掛程式可用來防止轉換變數例項數因為使用者重新整理頁面或點按「上一頁」按鈕而膨脹。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

**參數**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **變數**: 將受到檢查的變數。此變數通常與要定義的變數相同。
* **Cookie**: 儲存先前值做為比較依據之 Cookie 的名稱。此 Cookie 可以是任何值。
* (可選) **有效期**: Cookie 距離到期的天數。若未設定，或設定為 0，預設的有效期將是瀏覽器工作階段。
* (可選) **分鐘**: 若您將此項目設為字串值 m，有效期的值即會以分鐘為單位來定義，而不使用日。*`m`*&#x200B;有效期值是以分鐘為單位，而非數日定義。If not set, *`days`* is the default expiration.

**屬性**

* 此外掛程式常用於轉換變數。但您也可將其用於任何 [!DNL Analytics] 變數。
* Javascript 發現此函數時，即會比較定義的值與儲存在 Cookie 中的值。若定義的值與 Cookie 值不同，則會設定定義的值。若定義的值與 Cookie 值相同，則會傳回空字串。
* Cookie 只能儲存單一值，亦即外掛程式只會查看最後定義的值。
* 外掛程式不會阻止任何值去定義已定義的變數。外掛程式只會防止最後一個值連續設定多次。
* 若使用者封鎖或拒絕 Cookie，則一律會傳回原始值。
* 外掛程式的工作階段與 [!DNL Analytics] 所定義的工作階段 (或瀏覽) 不同。[!DNL Analytics] 會在活動達 12 小時或未活動達 30 分鐘後終止工作階段。由於外掛程式使用的是瀏覽器的工作階段定義，因此只有在使用者關閉標籤或退出瀏覽器後，才會終止工作階段。

   * 若使用者在關閉您的頁面後，於 30 分鐘內開啟另一個標籤並重新導覽至您的網站，外掛程式將會建立新的工作階段，同時保留 [!DNL Analytics] 瀏覽。
   * 若使用者讓瀏覽器視窗保持開啟而未點按任何連結超過 30 分鐘，[!DNL Analytics] 瀏覽即會過期，但瀏覽器工作階段仍會持續。

>[!NOTE]
>
>下列指示要求您變更網站上的資料收集代碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 實施 {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

>[!NOTE]
>
>If your organization uses Marketing Channels and has rules set up based on `s.campaign`, it is recommended that you not use the getValOnce plugin when setting the `s.campaign`value. 這樣可能會導致將錯誤管道指派給次要促銷活動點進次數。

若要實施此外掛程式，請將下列程式碼放入您的 [!DNL s_code.js] 檔案中

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Once the above code is implemented, define the desired variable using the *`getValOnce`* function. 以下幾個範例將說明其實施方式:

**在 Cookie 設定後的 30 天內偵測到重複值時，防止定義相同的促銷活動值:**`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`**如果在設定Cookie後30分鐘內偵測到重復值，則防止定義相同的eVar值：**`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`**防止同一個瀏覽器作業中多次定義相同的eVar值：**`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`**Notes**

* 在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
* 確定您刪除 Cookie 或在測試期間使用新的唯一值，否則將不會傳送變數。

