---
description: s.t() 函數會將該頁面上所定義的所有變數編譯為影像要求，並將其傳送至我們的伺服器。
keywords: track;Analytics Implementation;page tracking;track page
subtopic: Functions
title: s.t() 函數 - 頁面追蹤
topic: Developer and implementation
uuid: 67696e46-1e0d-4200-bfad-4217d1023948
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s.t() 函數 - 頁面追蹤

s.t() 函數會將該頁面上所定義的所有變數編譯為影像要求，並將其傳送至我們的伺服器。

## 函數的屬性 {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* 移除 [!UICONTROL s.t()] 呼叫會使任何資料皆無法送達 [!DNL Analytics]。多個 [!UICONTROL s.t()] 呼叫會引發多個影像要求 (使您網站上的報告流量倍增)。

* 若您要在單一頁面載入時引發多個影像要求，建議您使用 [!UICONTROL s.tl()] 函數。
* 觸發此函數一律會使[!UICONTROL 頁面檢視]增加，也一律會納入 [!UICONTROL s.pageName] 變數。

## 實施 {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

在[!UICONTROL 程式碼管理員]中產生程式碼時，頁面程式碼底部會出現下列項目: 

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

每一行程式碼都有特定用途: 

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

這一行是實際引發 Javascript 函數的程式碼。[!UICONTROL s_code] 變數及其隨附的 document.write 方法，適用於不支援影像物件的瀏覽器 (第 3 版之前的 Netscape 瀏覽器和第 4 版之前的 Internet Explorer；估計佔所有網路使用者的 0.5% 以下)。

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

如有任何其他關於 [!UICONTROL s.t()] 函數的問題，請與組織的客戶經理連絡。他們會安排您與 Adobe 實施顧問會面，為您提供所需協助。
