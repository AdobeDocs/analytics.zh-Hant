---
title: 封包分析器
description: 封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。
keywords: 封包 Sniffer、http 狀態、200、302、charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 99%

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
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome 開發者工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.telerik.com/fiddler) |
| [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>若您有關於這些封包監視器的問題，Adobe「不」提供支援或疑難排解。請向封包監視器的來源網站尋求協助。

## 典型 HTTP 回應狀態代碼

AppMeasurement 將資料傳送至 Adobe 資料收集伺服器時，而伺服器會以回應狀態代碼回應。

* **200 OK**：來自資料收集伺服器的最常見回應。已成功接收影像要求，並傳回透明影像。
* **302 FOUND**：收到此回應有幾個可能的原因：
   * 訪客的第一個影像要求：如果使用者第一次造訪您的網站，就會發生重新導向。此重新導向的目的是取得訪客 Cookie。並不會影響資料收集。
   * Comscore 與 Adobe 的整合：如果您的組織使用 Comscore/Analytics 整合，則每個影像要求一律會產生 302 回應。
* **404 NOT FOUND**：此回應表示找不到影像要求，且資料沒有傳送至 Adobe 資料收集伺服器。硬式編碼影像要求格式不正確時，也可能出現此回應。請與實作 Analytics 的個人或團隊合作以解決此問題。

## 回應程式碼中的 NS_BINDING_ABORTED

出現此訊息的原因是，連結追蹤影像要求依設計會允許瀏覽器直接進入下一頁，而不等候 Adobe 資料收集伺服器的回應。

Adobe 對於影像要求的回應會是空白的 1x1 透明影像，與頁面的內容沒有關聯。若您在封包監視器中看見來自 Adobe 的條列項目 (含有 **[!UICONTROL 200 OK]** 回應或 **[!UICONTROL NS_BINDING_ABORTED]** 回應)，表示資料已送達 Adobe 的伺服器。此時，頁面即無須再等候。

整合為外掛程式的封包監視器很少會看見完整回應。監視器常會因為未收到完整回應，而認為要求已中止。這些監視器也鮮少會區分中止的是要求還是回應。獨立式封包監視器通常就會有較詳細的訊息，並且會報告較精準的狀態。例如，使用者可能會在 *Charles* 中收到一則訊息，指出「用戶端在接收完整回應前即中斷連線」。這表示資料已送達我們的伺服器，但瀏覽器在 1x1 像素送達前即移至下一頁。

若外部封包監視器回報資料收集要求已中止 (而不是回應中止)，就表示可能出現問題。Adobe [!DNL Customer Care] 可提供疑難排解方面的協助。
