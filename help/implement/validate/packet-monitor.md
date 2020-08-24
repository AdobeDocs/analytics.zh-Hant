---
title: 封包分析器
description: 封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: b359582fe8ab6ee04bb478825d9989d850390f96
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 58%

---


# 封包分析器

封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。

封包監視器與 Adobe Experience Cloud Debugger 類似，會顯示在影像要求中傳送了哪些資料參數；但是，封包監視器另外還提供下列功能：

* 檢視自訂的連結追蹤影像要求
* 檢視非使用 JavaScript 實施方法的影像要求，如硬式編碼的影像請求或 [!DNL Appmeasurement]

若要檢視 Analytics 要求，請使用 &quot;b/ss&quot; 篩選傳出的要求。

在極少數的情況下，即使未對 Adobe 的 [!DNL Analytics] 處理伺服器提出影像要求，除錯工具仍會報告影像要求。使用資訊包監視器是很好的做法，可以 100% 確定已成功引發特定影像要求。

由於 Adobe 不提供官方的資訊包監視器，所以網路上有許多各式各樣的資訊包監視器。以下是其他人覺得很實用的資訊包監視器。

>[!TIP]
>
>這些並不是完整清單，而是常用監視器的清單。

| Firefox | Internet Explorer | Chrome | 獨立程式 |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (標籤檢視器) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (標籤檢視器) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome 開發者工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe不支援或疑難排解您在這些資訊包監視器上遇到的任何問題。 請洽詢封包監視器的原始網站以取得協助。

## 典型HTTP響應狀態代碼

當AppMeasurement傳送資料至Adobe資料收集伺服器時，伺服器會以回應狀態代碼回應。

* **200 OK**:來自資料收集伺服器的最常見回應。 已成功接收影像要求，並傳回透明影像。
* **302找到**:收到此回應有幾個可能的理由：
   * 訪客的第一個影像要求：如果使用者第一次瀏覽您的網站，就會發生重新導向。 此重新導向是取得訪客Cookie。 它不會影響資料收集。
   * Comscore與Adobe的整合：如果您的組織使用Comscore/Analytics整合，每個影像要求一律會產生302回應。
* **404找不到**:此回應表示找不到影像要求，且資料不會傳送至Adobe資料收集伺服器。 當硬式編碼影像要求格式不正確時，也可能發生此回應。 與實作Analytics的個人或團隊合作以解決此問題。

## 回應程式碼中的 NS_BINDING_ABORTED

出現此訊息是因為連結追蹤影像要求的設計是讓瀏覽器在等待Adobe資料收集伺服器的回應之前，先前往下一頁。

Adobe 對於影像要求的回應會是空白的 1x1 透明影像，與頁面的內容沒有關聯。If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe&#39;s servers. 此時，頁面即無須再等候。

整合為外掛程式的封包監視器很少會看見完整回應。監視器常會因為未收到完整回應，而認為要求已中止。這些監視器也鮮少會區分中止的是要求還是回應。獨立式封包監視器通常就會有較詳細的訊息，並且會報告較精準的狀態。例如，使用者可能會在 *Charles* 中收到一則訊息，指出「用戶端在接收完整回應前即中斷連線」。這表示資料已送達我們的伺服器，但瀏覽器在 1x1 像素送達前即移至下一頁。

如果外部封包監視器報告資料收集要求已中止，而非回應，這就引起了顧慮。 Adobe [!DNL Customer Care] 可提供疑難排解方面的協助。
