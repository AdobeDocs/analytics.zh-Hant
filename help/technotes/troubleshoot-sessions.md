---
title: 疑難排解Adobe Analytics中的工作階段
description: 瞭解如何解決登出Adobe Analytics的相關問題。
seo-title: 疑難排解Adobe Analytics中的工作階段
seo-description: 瞭解如何解決登出Adobe Analytics的相關問題。
translation-type: tm+mt
source-git-commit: 5df7bc43587deed41786f6c85f472fb6f908caf8

---


# 疑難排解Adobe Analytics中的工作階段

本頁面是有關疑難排解工作階段的資訊，這表示您可以成功登入，但有未登入的問題。 如果您在登入Adobe Analytics時遇到問題，請參閱「疑難排解登 [入Adobe Analytics的問題」](troubleshoot-login.md)。

幾乎所有基於會話的問題都源自組織的定製公司網路。 如果您能夠登入Adobe Analytics，但無法繼續登入，請使用本文章協助判斷原因。

## 確定問題是否由於您組織的網路

許多組織都部署了額外的網路功能來增強安全性，例如代理伺服器或防火牆。 這些自訂功能有時會干擾Adobe Analytics中保留作用中工作階段的能力。

若要判斷您所連線的公司網路是否造成使用Adobe Analytics的問題，請在公司網路以外的裝置上使用您的Experience cloud登入認證。 例如，裝置可透過您的家庭網路或行動裝置的資料計畫。 如果您能夠在未登出的情況下成功地從頁面間移動，您組織的網路可能是您登出Adobe Analytics的原因。

## Proxy造成的問題

Adobe向Adobe提出要求時會使用授權標題。 有些Proxy(例如Bluecoat（現為Symantec所有）會移除Adobe Analytics使用的重要授權標題資訊。 當Adobe未看到授權標題時，作業階段即會過期。

為解決此問題，Adobe建議與貴組織的IT團隊合作，以透過貴組織的Proxy允許授權標題。

> [!NOTE] 雖然 Analytics 社群的會員已發現下列實用連結，但 Adobe 並非這些連結的擁有者。檢視其內容時，請將此備註列入考量。

有關Symantec Proxy和驗證標頭的資訊，請參見：

* [在ProxySG或ASG裝置上的代理鏈部署中配置上游代理驗證](https://support.symantec.com/en_US/article.TECH246122.html)
* [允許ProxySG始終向上游轉發伺服器授權](https://support.symantec.com/en_US/article.TECH244708.html)
