---
description: 要達到成功的 DFA 實施，必須針對您的網站將 s.maxDelay 最佳化。
keywords: DFA
seo-description: 要達到成功的 DFA 實施，必須針對您的網站將 s.maxDelay 最佳化。
seo-title: 調整 s.maxDelay
solution: Analytics
title: 調整 s.maxDelay
topic: Data connectors
uuid: 7640af26-6ac6-427e-9cfc-932c86cf5ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 調整 s.maxDelay{#tuning-s-maxdelay}

要達到成功的 DFA 實施，必須針對您的網站將 s.maxDelay 最佳化。

一般而言，提高或降低的決策 *`s.maxDelay`* 牽涉到取得更多DFA訪客資料並危及收集Adobe訪客資料之間的權衡。Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. 降低 s.maxDelay 可確保能夠收集 Adobe 訪客資料，但可能會失去 DFA 訪客資料。

*`s.maxDelay`*&#x200B;所包含的不僅止是連絡 DFA 時的網路通訊時間；它也代表瀏覽器在引發及評估這些通訊所依據之 JavaScript 時的延遲。這是因為Integrate模組會在 *`s.maxDelay`* 將HTML元素插入DOM後開始計時器，以便從DFA Floodlight伺服器提取資料。瀏覽器根據這個新的 HTTP 元素起始 HTML 要求實際花費的時間量，會隨著同時載入的其他影像或 JavaScript 檔案、訪客電腦的速度和特定的瀏覽器實施方式而有所不同。此外，在從 DFA Floodlight 伺服器擷取 JSON 資料時，瀏覽器必須要評估 JavaScript。這項作業同樣也完全由瀏覽器所控制，且若有大量的 JavaScript 代碼同時執行，或是有許多非同步的 JavaScript 要求，此作業則可能延遲。

請記住，*`s.maxDelay`*&#x200B;的設定必須要考量著陸頁面的複雜性，以及 DFA 的網路延遲量。在某些網站上，降低複雜性的可行方式之一是在頁面載入時即引發 Adobe 收集代碼，如此，在對 Floodlight 伺服器執行要求時，瀏覽器中的流量負載將會較輕。

在調整&#x200B;*`s.maxDelay`*&#x200B;因為每次s. maxDelay逾時都會增加。在決定是否要增加或減少 *`s.maxDelay`* 時，建議您遵循此程序：

1. 收集數天資料並 *`s.maxDelay`* 設定為特定值。
1. 執行 [!DNL Daily Unique Visitors Report] 時間範圍。
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. 請記住，對於每一個訪客只會收集一次逾時。

現在，請利用下圖計算

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

請注意，「逾時百分比」實際上會考量網站的所有訪客。其中有些訪客其實完全不會繫結至 DFA，因此逾時次數是失真的。To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). 此方式會有較高的精確性。

如果逾時百分比很低，請考慮降低&#x200B;*`s.maxDelay`*。如果很高，請增加 *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

當您移轉至 2.0 版的整合時，由於移除了 302 重新導向的關係，我們預期逾時次數將會降低。根據對測試版用戶端的初步觀察，逾時次數呈現穩定下降趨勢，收集到的 DFA 資料也因而增多
