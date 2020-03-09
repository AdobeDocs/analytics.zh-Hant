---
title: 排解 Adobe Analytics 中工作階段的疑難問題
description: 瞭解如何解決登出 Adobe Analytics 時遇到的相關問題。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 排解 Adobe Analytics 中工作階段的疑難問題

本頁面提供工作階段的排解疑難資訊，此問題是指您可以成功登入，但無法保持登入狀態。如果您在登入 Adobe Analytics 時遇到問題，請參閱[排解登入 Adobe Analytics 的疑難問題](troubleshoot-login.md)。

幾乎所有因工作階段產生的問題都源自組織的自訂公司網路。如果您能登入 Adobe Analytics 但無法保持登入狀態，請使用本文章協助判斷原因。

## 判斷問題是否緣起於貴組織的網路

許多組織都部署了額外的網路功能來增強安全性，例如 Proxy 伺服器或防火牆。這些自訂功能有時會干擾 Adobe Analytics 中保留作用中工作階段的能力。

若要判斷您所連線的公司網路是否造成 Adobe Analytics 使用上的問題，請在公司網路以外的裝置上使用您的 Experience Cloud 登入憑證。例如可透過您的家庭網路或行動裝置的行動數據方案使用裝置。如果您能夠在未登出的狀態下成功在頁面間移動，表示貴組織的網路可能是系統將您登出 Adobe Analytics 的原因。

## Proxy 造成的問題

向 Adobe 提出請求時，Adobe 會使用授權標頭。有些 Proxy (例如現屬於 Symantec 的 Bluecoat) 會移除 Adobe Analytics 所使用的重要授權標頭資訊。當 Adobe 沒有看到授權標題，工作階段便會過期。

為解決此問題，Adobe 建議與貴組織的 IT 團隊合作，允許授權標頭通過貴組織的 Proxy。

> [!NOTE] 雖然 Analytics 社群的會員已發現下列實用連結，但 Adobe 並非這些連結的擁有者。檢視其內容時，請將此備註列入考量。

如需 Symantec Proxy 和授權標頭的資訊，請參閱：

* [在 ProxySG 或 ASG 設備上的 Proxy 鏈部署中設定上游 Proxy 驗證](https://support.symantec.com/en_US/article.TECH246122.html)
* [允許 ProxySG 一律向上游轉送伺服器授權](https://support.symantec.com/en_US/article.TECH244708.html)
