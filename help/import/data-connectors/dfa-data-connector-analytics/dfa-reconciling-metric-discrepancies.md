---
description: 在比較 Adobe Analytics 量度與 DFA 量度時，有些量度可能會超出可接受的差異範圍。以下列出量度定義以及可能的變異原因。
keywords: DFA
title: 協調量度差異
topic: Data connectors
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 協調量度差異{#reconciling-metric-discrepancies}

在比較 Adobe Analytics 量度與 DFA 量度時，有些量度可能會超出可接受的差異範圍。以下列出量度定義以及可能的變異原因。

本章包含以下主題:

## 量度定義{#metric-definitions}

Adobe 在討論與 DFA 整合有關的量度時，會使用下列詞彙:

**曝光數**:「曝光數」是指檢視廣告的次數。「曝光數」會就個別的廣告列入報表，但也可彙整至廣告群組或其他多重廣告群組中。Analytics 中的曝光數量度會透過夜間資料來源匯入，從 DFA 匯入。

**點按**:「點按」是指點按廣告的次數，如 DFA 所報告。「點按」會在訪客進入客戶的網站之前，登錄於 DFA 重新導向頁面上。如同曝光數，Analytics 中的點按量度也會透過夜間資料來源匯入，從 DFA 匯入。

**點進**:「點進」是指使用者在點按廣告後進入著陸頁面的次數。此量度可能與點按略有不同。

**閱覽**:「閱覽」是指訪客在檢視廣告後未點按廣告即進入客戶網站的次數。訪客必須在閱覽時程內進入網站，此時程預設為 30 天。產生曝光的時間必須早於前次點按的時間。閱覽會就每一個促銷活動、每一個造訪個別登錄，並且會在整合以 DFA 促銷活動 ID 填入閱覽 eVar 時，以及在設定閱覽事件時計算閱覽次數。

## 差異的可能原因{#possible-reasons-for-discrepancies}

列出 Adobe Analytics 與 DFA 報表之間出現資料差異問題的若干可能原因。

### Safari 瀏覽器和其他會封鎖第三方 cookie 之瀏覽器的使用者 {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

接受第三方 cookie，通常是導致 Adobe Analytics 與 DFA 之間出現差異的最大原因。Safari 和其他某些瀏覽器依預設會封鎖第三方 cookie。這表示，根據預設，Safari 會接受大部分的 Analytics 實施所使用的第一方 cookie，但拒絕 DFA 所使用的第三方 cookie。

來自Analytics 15測試版客戶的資料範例顯示，通常不到0.5%的使用者拒絕第一方Cookie，而5-12%的使用者拒絕第三方Cookie（其中許多拒絕可能是由於預設瀏覽器設定）。

這種不一致的狀況，可能會導致 Analytics 與 DFA 所收集的資料出現很大的差異。

### 為何在 DFA 中報告的曝光數可能會高於在 Adobe Analytics 中報告的曝光數? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA 會以夜間批次將資料傳送至 Adobe 資料收集伺服器，因此，Analytics 中的數數資料最多可能會比 DFA 報表落後 2 天。
* Adobe 會使用 SAINT 分類功能，將匯入的 DFA 追蹤代碼分類為不同層級的彙整 (促銷活動名稱、版面名稱、廣告名稱等)。如果在執行分類報表時出現不一致的狀況，請執行簡易測試，確認分類是否仍落後於匯入的量度:

   * 在分類報表中，找出名為「無」的行項目。
   * 使用原始 DFA ID 報表 (例如促銷活動 ID)，依相同的變數劃分此明細項目。
   * 在此報表中，記下任何未分類的 DFA 追蹤代碼，其形式會是 `DFA:XXXXX:XXXXX`.
   * 若有許多這類的追蹤代碼存在，請調查夜間 SAINT 分類程序。

### 為何 DFA 點按次數可能高於 Adobe Analytics 點進次數? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* 在訪客到達客戶網站時，DFA 即會記錄一次點按。Analytics 則是等到著陸頁面載入且執行 Adobe JavaScript 信標時，才記錄點進。一般通常會有差異存在，因為訪客在 DFA 追蹤點按之後可能並未進入著陸頁面，或是`s.maxDelay`計時器可能到期。
* Ensure all placements and creatives in the Floodlight Configuration include the clickThroughParam in the landing page URL (for example "`?CID=1`"). 若未設定此參數，將導致 Adobe Analytics JavaScript 遺漏任何在第一次造訪點擊之後發生的點進。
* 請確定所有版面和創作的著陸頁面皆加上 JavaScript 的標記，且具有 DFA 整合模組，並確定該著陸頁面上的 Floodlight 設定 ID 與提供之廣告的 Floodlight 設定 ID 相符。不一致的狀況經常是由於廣告的著陸頁面設定為第三方網站或提供的廣告所致。
* 如果您使用多媒體廣告或 Flash (swf) 廣告，請確定在每次觸發 DFA 點按追蹤時，訪客的瀏覽器也會重新導向至將 `clickThroughParam` 包含在查詢字串中的著陸頁面。若無法重新導向瀏覽器，將導致系統記錄點進。
* 逾時代表 DFA 資料可能已可用，但 JavaScript 並未及時接收到回應的情況。當訪客到達著陸頁面時，Adobe JavaScript 會從 DFA 的 fls.doubleclick.net 服務要求訪客的資訊。The`s.maxDelay`參數會決定 JavaScript 應等待 Floodlight 服務 (FLS) 資料多久。If `s.maxDelay` is too high, visitors can leave the site before Adobe collects the hit data; meaning that no click data is recorded. If `s.maxDelay` is set too low, the visitor's Internet connection cannot retrieve the FLS data in time; meaning that the hit is sent to Adobe without DFA click information.
* 機器人流量可能會誇大 DFA 點按次數。機器人可能具有相關功能可以點按廣告，但不足以執行 Analytics 信標或引發可載入 Floodlight 伺服器要求資料的同步指令檔標記。若未從點按數據中移除這些機器人，就可能造成不一致的來源。
* 在`s.maxDelay`到期之前離開頁面的訪客以及傳回的 DFA 資料將會遺失；其 DFA 或訪客資料都不會被收集。
* Analytics 會嘗試識別並移除重複的點進，使每個活動的每次造訪只會計算一次點進。DFA會將點按「上一步」並多次透過廣告重新導向的訪客計為額外的ACM點按次數，而Analytics不會將這些點按計為多次點進次數。
* DFA Floodlight 標記不需要啟用 JavaScript 即可使用，但 Analytics 則需要。因此，在某些情況下，當 DFA 紀錄點擊時，Analytics 並未記錄。若要確認這是否會造成問題，請使用「訪客資料」功能表中的 Analytics JavaScript 報表。

### 為何 DFA 曝光後活動數可能高於 Adobe Analytics 閱覽次數? {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics 會嘗試識別並移除重複的點進，使每個活動的每次造訪只會計算一次點進。DFA會將點按「上一步」並多次透過廣告重新導向的訪客計為額外的ACM點按次數，而Analytics不會將這些點按計為多次點進次數。
* DFA Floodlight 標記不需要停用 JavaScript 即可使用，但 Analytics 則需要。因此，在某些情況下，當 DFA 紀錄點擊時，Analytics 並未記錄。
* DFA 會在使用 Floodlight 標記 (可能放在客戶網站上) 時計算曝光後活動數。Analytics 會在 JavaScript 信標 (影像要求) 執行後計算閱覽次數。網頁上的代碼版面，可判斷是否要將中止的頁面載入計為曝光後活動或閱覽。

### 如果不一致的程度遠超過可接受的範圍，且前述的可能原因並不適用，應該如何? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

請洽詢您的整合顧問或 Adobe Client Care，以記下不一致的狀況並將其回報給 Data connectors 工程團隊。為了加快要求的處理速度，請就有問題的量度，備妥 2 - 3 天份的量度比較資料 (在促銷活動代碼層級上)。在您的要求中，請指出您為了消除不一致所執行的所有動作。
