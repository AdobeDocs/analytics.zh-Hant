---
description: getAndPersistValue 外掛程式可依照您的選擇在指定時段內取得值，並將其填入 Analytics 變數中。一個常見作用就是檢視促銷活動被點進後所產生的頁面檢視次數，這可讓您輕易地看出每個促銷活動的最頻繁頁面。
keywords: Analytics 實施
seo-description: getAndPersistValue 外掛程式可依照您的選擇在指定時段內取得值，並將其填入 Analytics 變數中。一個常見作用就是檢視促銷活動被點進後所產生的頁面檢視次數，這可讓您輕易地看出每個促銷活動的最頻繁頁面。
seo-title: getAndPersistValue
solution: Analytics
subtopic: 外掛程式
title: getAndPersistValue
topic: 開發人員和實施
uuid: ddeab80c-260e-44b6-8843-8b8b369ec19b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

getAndPersistValue 外掛程式可依照您的選擇在指定時段內取得值，並將其填入 Analytics 變數中。一個常見作用就是檢視促銷活動被點進後所產生的頁面檢視次數，這可讓您輕易地看出每個促銷活動的最頻繁頁面。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. 此範例可讓您判斷追蹤程式碼因原始點進而產生了多少個頁面檢視。

>[!NOTE]
>
>下列指示要求您變更網站上的資料收集代碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**設定區段**: 此區段無需變更。

**外掛程式設定**

將下列程式碼放入&#x200B;*`s_doPlugins()`* 函數 *`s_code.js`***。選擇一個自訂流量 (s.prop) 變數或一個自訂轉換 (s.eVar) 變數，用於持續值資料的擷取。此變數應為已使用管理控制台加以啟用，但目前未做任何其他用途的變數。您可以使用下列範例，並根據您的需求加以更新。

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* 有三個引數:

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
1. 以天為單位的持續時段。範例中顯示的 "30"，會使此值在使用者於未來 30 天內每次進行頁面檢視時，都填入至選取的變數中。若未加以設定，則會預設為&#x200B;*工作階段*。

**外掛程式區段**: 將下列程式碼新增至 [!DNL s_code.js] 檔案中標示為 PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
