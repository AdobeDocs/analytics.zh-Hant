---
title: 排解 Adobe Analytics 中工作階段的疑難問題
description: 瞭解如何解決登出 Adobe Analytics 時遇到的相關問題。
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 97%

---

# 排解 Adobe Analytics 中工作階段的疑難問題

本頁面提供工作階段的排解疑難資訊，此問題是指您可以成功登入，但無法保持登入狀態。如果您在登入 Adobe Analytics 時遇到問題，請參閱[排解登入 Adobe Analytics 的疑難問題](troubleshoot-login.md)。

幾乎所有因工作階段產生的問題都源自組織的自訂公司網路。如果您能登入 Adobe Analytics 但無法保持登入狀態，請使用本文章協助判斷原因。

## 判斷問題是否緣起於貴組織的網路

許多組織都部署了額外的網路功能來增強安全性，例如 Proxy 伺服器或防火牆。這些自訂功能有時會干擾 Adobe Analytics 中保留作用中工作階段的能力。

若要判斷您所連線的公司網路是否造成 Adobe Analytics 使用上的問題，請在公司網路以外的裝置上使用您的 Experience Cloud 登入憑證。例如可透過您的家庭網路或行動裝置的行動數據方案使用裝置。如果您能夠在未登出的狀態下成功在頁面間移動，表示貴組織的網路可能是系統將您登出 Adobe Analytics 的原因。

## Proxy 造成的問題

向 Adobe 提出請求時，Adobe 會使用授權標頭。某些 Proxy (例如 Edge Secure Web Gateway (先前稱為 Bluecoat)) 會去除 Adobe Analytics 所使用的關鍵授權標頭資訊。 當 Adobe 沒有看到授權標題，工作階段便會過期。

為解決此問題，Adobe 建議與貴組織的 IT 團隊合作，允許授權標頭通過貴組織的 Proxy。

>[!NOTE]
>
>雖然 Analytics 社群的成員已找到下列實用連結，但這些連結並非 Adobe 所擁有。 檢視其內容時，請將此備註列入考量。

如需 Proxy 和授權標頭的資訊，請參閱：

* [在 ProxySG 或 ASG 設備上的 Proxy 鏈部署中設定上游 Proxy 驗證](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [如何將使用者認證轉送給 ProxySG 設備背後的伺服器](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
