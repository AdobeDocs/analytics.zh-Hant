---
description: 使用 HTML 影像標記實施 Analytics (硬式編碼影像請求)
keywords: Analytics Implementation;html image tag;hardcoded image request
title: 使用 HTML 影像標記實作 Analytics
topic: Developer and implementation
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用 HTML 影像標記實作 Analytics

使用 HTML 影像標記實施 Analytics (硬式編碼影像請求)

接著，瀏覽器會要求影像。資料會隨著此影像要求，透過影像要求之查詢字串中的變數而移動。JavaScript 結合了瀏覽器層級變數與頁面層級變數，以組成全方位的資料收集解決方案。在某些情況下，完全由伺服器建立的影像標記是適用的。以下列出 JavaScript 型實施的標準元素: 

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> HTML程式碼 </td> 
   <td> 此部分包含設定 JavaScript 變數值的 HTML 頁面 (或範本) 中所放置的 JavaScript 程式碼。 </td> 
  </tr> 
  <tr> 
   <td> JavaScript 程式庫 </td> 
   <td> <p>此檔案包含下列用途的共用程式碼:  </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">對瀏覽器查詢有關於各種屬性的資料，例如 JavaScript 版本、作業系統版本、所使用之監視器的大小和解析度，以及其他變數 </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">為所有變數編碼，並將其串連到會將這些變數傳輸到資料收集伺服器的影像要求 (&lt;img&gt;) 中。接著，它會參考已載入並執行的 JavaScript 程式庫檔案。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> &lt;noscript&gt; 標記 </td> 
   <td> &lt;noscript&gt; 標記中可放入簡易版的影像要求，以在使用者停用 JavaScript 或不具備 JavaScript 功能時執行。這部分的實施是選用的，一般而言，約適用於 2% 的網際網路填入。 </td> 
  </tr> 
 </tbody> 
</table>

JavaScript 可偵測伺服器無法取得的瀏覽器設定，例如瀏覽器視窗高度/寬度、螢幕解析度和 Netscape 外掛程式等。使用伺服器端方法建立影像標記時，將無法擷取這些變數。JavaScript 可在影像要求中設定隨機數字，以抑制瀏覽器和 Proxy 伺服器快取。這可讓所有頁面檢視皆正確受到追蹤。在特定情況下，伺服器端程式碼會有優於 JavaScript 型程式碼之處，其中包括: 

* JavaScript 的正確性非常高 (98-100%)。在某些情況下，我們會需要最高度的正確性，即使是使用者在 JavaScript 執行前即快速點按至其他頁面時，也是如此。在伺服器端建立影像標記，可讓正確度提高數個百分點。
* 對於追蹤轉換事件 (例如購買)，準確度相當重要。
* 此策略也可用來完全填入 <noscript> 標籤內的影像要求，在沒有 JavaScript 或已停用 JavaScript 的情況下追蹤使用者。

> [!NOTE]要使用伺服器產生的影像標籤，必須以額外的時間實施，且在除錯、部署及維護上都較為困難。Adobe 強烈建議客戶盡可能對每個頁面都使用 JavaScript 型資料收集。使用此實施方法，將無法收集或支援不同的報表和功能，包括訪客點按對映、下載連結、退出連結和瀏覽器相關變數 (瀏覽器寬度/高度等)。

