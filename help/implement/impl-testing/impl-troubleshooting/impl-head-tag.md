---
description: Analytics 程式碼會建立影像物件，這是一種不會顯示在頁面上的不可見影像。
keywords: Analytics Implementation
title: 將 Analytics 程式碼放入 head 標記中
topic: Developer and implementation
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 將 Analytics 程式碼放入 head 標記中

Analytics 程式碼會建立影像物件，這是一種不會顯示在頁面上的不可見影像。

>[!NOTE]
>
>本節內容僅適用於傳統 s_code.js 實施。[JavaScript 1.0 適用的 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) 支援在 `<head>` 標籤中部署程式庫和頁面程式碼。

在過去，常見的實施方式是將 Analytics JavaScript 程式碼放在  <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 與 </head> 標記之間。將程式碼放在這兩個標記之間，會使將資料傳入 Adobe 伺服器的要求所傳回的 1 x 1 像素影像在任何情況下都無法影響頁面配置。將程式碼放在文件標題中，意味著程式碼會較早出現。這可讓程式碼及早執行，而讓您更有效地計算部分頁面載入的頁面檢視數。

某些程式碼元素在執行時，必須要有內文物件存在。由於網頁瀏覽器會依接收時的順序執行程式碼，若 Analytics JavaScript 程式碼位於文件標題中，此程式碼將會在內文物件存在之前執行。因此，您的實施將不會收集 [!UICONTROL ClickMap] 資料，並且無法使用檔案下載或[!UICONTROL 退出]連結的自動追蹤。您也不會收到連線類型資料或訪客首頁資料。將程式碼放在文件標題中的確有其效用，但同時也會導致 Analytics 的功能大受限制，使用者也會因為特定報表和工具 (包括 [!UICONTROL ClickMap]) 無法記錄資料，而感到疑惑。

Analytics 程式碼可放置在正常格式 HTML 頁面的 BODY 標籤內的任一處 (<BODY></BODY>)。Adobe 建議將程式碼放在位於頁面頂端的全域含入檔中 (在 HTML 內文標記內)。程式碼可放置在頁面上的任一處，但下列情況例外: 

* 放置於表格內時，請只將程式碼放在 <td></td> 標籤內。例如，請勿將程式碼放置在開頭 <tr> 標籤與開頭 <td> 標籤之間。
* 設定變數的程式碼必須存在於 s_code.js 檔案的參考之後。
* 確認 s_code.js 檔案的 *`s_account`* 變數中的[!UICONTROL 報表套裝 ID] 已正確設定。從「程式碼管理員」下載特定報表套裝的程式碼時，或是由 Adobe 技術顧問提供時，此變數通常都會正確設定。

若您想整合 Analytics 與 Target，則必須將 JavaScript 含入檔放在頁面底部。下列範例說明正確放置 Analytics 程式碼的方式: 

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3.
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

