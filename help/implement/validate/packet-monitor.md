---
title: 封包分析器
description: 封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 封包分析器

封包分析器可讓您檢視由實施傳送給 Adobe 資料收集伺服器的資料。

封包監視器與 Adobe Experience Cloud Debugger 類似，會顯示在影像要求中傳送了哪些資料參數；但是，封包監視器另外還提供下列功能：

* 檢視自訂的連結追蹤影像要求
* 檢視非使用 JavaScript 實施方法的影像要求，如硬式編碼的影像請求或 [!DNL Appmeasurement]

若要檢視 Analytics 要求，請使用 &quot;b/ss&quot; 篩選傳出的要求。

在極少數的情況下，即使未對 Adobe 的 [!DNL Analytics] 處理伺服器提出影像要求，除錯工具仍會報告影像要求。使用資訊包監視器是很好的做法，可以 100% 確定已成功引發特定影像要求。

雖然Adobe不提供官方封包監視器，但網際網路上卻有種類廣泛的封包監視器。 以下是一些其他人認為有用的資料包監視器。

>[!NOTE]這些並不是完整清單，而是常用監視器的清單。如果您有成功使用並發現有用的封包監視器，請使用此視窗右側的按 [!UICONTROL Feedback] 鈕，隨時提供意見回應。

| Firefox | Internet Explorer | Chrome | 獨立程式 |
|---|---|---|---|
| [觀察點](https://www.observepoint.com/product#plugin) （標籤檢視器） | [HttpWatch](https://www.httpwatch.com/) | [觀察點](https://www.observepoint.com/product#plugin) （標籤檢視器） | [查爾斯](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome 開發者工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [竄改資料](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]若您有關於這些資訊包監視器的問題，Adobe「不」提供支援或疑難排解。請向資訊包監視器的來源網站尋求協助。

## 回應程式碼中的 NS_BINDING_ABORTED

發生此錯誤是因為連結追蹤影像要求的設計是讓瀏覽器在等待Adobe資料收集伺服器的回應之前，先前往下一頁。

Adobe對影像要求的回應只是空白的1x1透明影像，與頁面內容無關。 若您在封包監視器中看見來自 Adobe 的明細項目 (附有 **[!UICONTROL 200 OK]** 回應或 **[!UICONTROL NS_BINDING_ABORTED]** 回應)，表示資料已送達我們的伺服器。您不需要再等待頁面。

整合為外掛程式的封包監視器很少會看到完整回應。 由於未收到完整回應，他們通常會將請求視為已中止。 這些監視器也很少區分中止的請求或回應。 單機包監視器通常會有更詳細的訊息，並更精確地報告狀態。 例如，使用者可能會在 ** Charles中收到一則訊息，說明「客戶端在收到整個回應之前已關閉連線」。 這表示資料確實已送達我們的伺服器，只要瀏覽器在收到1x1像素之前移至下一頁即可。

如果外部封包嗅探器報告資料收集要求已中止（而非回應），這會引起人們的擔憂。 Adobe [!DNL Customer Care] 可提供疑難排解方面的協助。
