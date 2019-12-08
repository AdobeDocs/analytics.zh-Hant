---
description: getAndPersistValue 外掛程式可依照您的選擇在指定時段內取得值，並將其填入 Analytics 變數中。一個常見作用就是檢視促銷活動被點進後所產生的頁面檢視次數，這可讓您輕易地看出每個促銷活動的最頻繁頁面。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getAndPersistValue

getAndPersistValue 外掛程式可依照您的選擇在指定時段內取得值，並將其填入 Analytics 變數中。一個常見作用就是檢視促銷活動被點進後所產生的頁面檢視次數，這可讓您輕易地看出每個促銷活動的最頻繁頁面。

>[!IMPORTANT]
>
>此外掛程式尚未通過是否能與 [JavaScript 適用的 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) 相容的驗證。詳情請參閱 [AppMeasurement 外掛程式支援](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)。

例如，您可能會使用此外掛程式，針對每位訪客在未來 30 天內進行的頁面檢視，將來自 *`campaign`* 變數的促銷活動追蹤程式碼設定至自訂流量 (*`s.prop`*) 變數中。此範例可讓您判斷追蹤程式碼因原始點進而產生了多少個頁面檢視。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**設定區段**: 此區段無需變更。

**外掛程式設定**

將下列程式碼放入 *`s_doPlugins()`* 函數中；此函數位於 *`s_code.js`檔案中標示為* Plugin Config *的區域中。*&#x200B;選擇一個自訂流量 (s.prop) 變數或一個自訂轉換 (s.eVar) 變數，用於持續值資料的擷取。此變數應為已使用管理控制台加以啟用，但目前未做任何其他用途的變數。您可以使用下列範例，並根據您的需求加以更新。

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* 有三個引數:

1. 可持續的目前填入的變數或值 (以上所示的 *`s.campaign`*)。
1. Cookie 名稱，可用來儲存值 (以上所示的 *`s_getval`*)。
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
