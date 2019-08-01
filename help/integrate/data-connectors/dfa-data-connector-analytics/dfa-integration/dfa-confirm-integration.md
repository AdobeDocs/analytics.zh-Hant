---
description: 在您完成所有必要的網站更新後，您可以使用 Charles*、Chrome Developer Tools 或 Firebug* 等網路流量檢視器，來確認 DFA 正在與 Adobe 收集伺服器通訊。
keywords: DFA
seo-description: 在您完成所有必要的網站更新後，您可以使用 Charles*、Chrome Developer Tools 或 Firebug* 等網路流量檢視器，來確認 DFA 正在與 Adobe 收集伺服器通訊。
seo-title: 確認成功的 DFA 整合
solution: Analytics
title: 確認成功的 DFA 整合
topic: Data connectors
uuid: d658cd7c-6377-439a-850c-ecea8 c41 f970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 確認成功的 DFA 整合{#confirming-a-successful-dfa-integration}

在您完成所有必要的網站更新後，您可以使用 Charles*、Chrome Developer Tools 或 Firebug* 等網路流量檢視器，來確認 DFA 正在與 Adobe 收集伺服器通訊。

在您部署具有 DFA 功能的 `s_code.js` 檔案後，請使用網路流量檢視器來檢視 DFA 與 Adobe 資料收集伺服器之間的要求，並尋找下列項目:

* A request to DFA's `fls.doubleclick.net/json` service. 視您所使用的 DFA 版本之不同，此服務可能會以不同的方式回應。DFA 整合 1.5 版:

   * 以 [!DNL ad.doubleclick.net] 為目標的 HTTP 302 重新導向。這將會在回應時傳送一個「位置:」標記，其中包含廣告訪客的相關資訊。
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. 此服務會將廣告訪客的相關資訊轉譯為 JSON (JavaScript 物件標記法) 編碼字串。這項資料會連同「200 確定」HTTP 回應一起傳回。

* DFA 整合 2.0 版 (啟用「進階廣告服務」):

   * [!DNL fls.doubleclick.net] 會直接以「200 確定」回應。

在前述任一情況下，成功的要求都會產生包含參數 vX 的 Adobe 資料收集伺服器要求，其中，X 是您的閱覽 eVar 數字。此參數值採用下列格式: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX。此字串包含關於現行訪客的前次點按和前次曝光數的資料。
