---
title: 封包分析器
description: 封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 封包分析器

封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。

封包監視器與 Adobe Experience Cloud Debugger 類似，會顯示在影像要求中傳送了哪些資料參數；但是，封包監視器另外還提供下列功能：

* 檢視自訂的連結追蹤影像要求
* 檢視非使用 JavaScript 實施方法的影像要求，如硬式編碼的影像請求或 [!DNL Appmeasurement]

若要檢視 Analytics 要求，請使用 &quot;b/ss&quot; 篩選傳出的要求。

在極少數的情況下，即使未對 Adobe 的 [!DNL Analytics] 處理伺服器提出影像要求，除錯工具仍會報告影像要求。使用資訊包監視器是很好的做法，可以 100% 確定已成功引發特定影像要求。

由於 Adobe 不提供官方的資訊包監視器，所以網路上有許多各式各樣的資訊包監視器。以下是其他人覺得很實用的資訊包監視器。

> [!NOTE]這些並不是完整清單，而是常用監視器的清單。若您有使用成功且覺得很實用的資訊包監視器，請不吝賜教使用本視窗右方的[!UICONTROL 「回饋意見」]按鈕告訴我們。

| Firefox | Internet Explorer | Chrome | 獨立程式 |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (標籤檢視器) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (標籤檢視器) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome 開發者工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

> [!NOTE]若您有關於這些資訊包監視器的問題，Adobe「不」提供支援或疑難排解。請向資訊包監視器的來源網站尋求協助。

## 回應程式碼中的 NS_BINDING_ABORTED

發生此錯誤的原因是，連結追蹤影像要求依設計會允許瀏覽器直接進入下一頁，而不等候 Adobe 資料收集伺服器的回應。

Adobe 對於影像要求的回應會是空白的 1x1 透明影像，與頁面的內容沒有關聯。若您在封包監視器中看見來自 Adobe 的明細項目 (附有 **[!UICONTROL 200 OK]** 回應或 **[!UICONTROL NS_BINDING_ABORTED]** 回應)，表示資料已送達我們的伺服器。此時，頁面即無須再等候。

整合為外掛程式的封包監視器很少會看見完整回應。監視器常會因為未收到完整回應，而認為要求已中止。這些監視器也鮮少會區分中止的是要求還是回應。獨立式封包監視器通常就會有較詳細的訊息，並且會報告較精準的狀態。例如，使用者可能會在 *Charles* 中收到一則訊息，指出「用戶端在接收完整回應前即中斷連線」。這表示資料已送達我們的伺服器，但瀏覽器在 1x1 像素送達前即移至下一頁。

若外部封包 Sniffer 回報資料收集要求已中止 (而不是回應中止)，就表示可能會有問題。Adobe [!DNL Customer Care] 可提供疑難排解方面的協助。
