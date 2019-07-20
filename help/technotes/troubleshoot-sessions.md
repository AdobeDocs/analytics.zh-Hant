---
title: 疑難排解Adobe Analytics中的作業
description: 瞭解如何解決從Adobe Analytics登出的問題。
seo-title: 疑難排解Adobe Analytics中的作業
seo-description: 瞭解如何解決從Adobe Analytics登出的問題。
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# 疑難排解Adobe Analytics中的作業

此頁面與疑難排解作業有關，表示您可以成功登入，但仍有問題留待登入。If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

幾乎所有以作業階段為基礎的問題都源自於組織自訂的公司網路。如果您可以登入Adobe Analytics但無法登入，請使用此文章來協助判斷原因。

## 判斷此問題是否因您組織的網路而定

許多組織部署額外的網路功能以增強安全性，例如Proxy伺服器或防火牆。這些自訂有時會干擾在Adobe Analytics中保留作用中會話的能力。

若要判斷您連線的公司網路是否會導致使用Adobe Analytics，請在公司網路外部的裝置上使用Experience Cloud登入憑證。裝置的例子可以是您的家庭網路或行動裝置的資料計劃。如果您可以成功地從頁面移至頁面，而不是登出，則您的組織網路可能是您登出Adobe Analytics的原因。

## 因IP集區而引起的問題

有些網路使用稱為IP位址集區的實務，在組織使用的範圍內，裝置的IP位址可經常變更。作為Adobe安全性實務的一部分，如果IP位址發生變更，則該作業已過期。

如果您的組織使用IP位址集區，請使用下列指示將您的IP範圍新增至Adobe的電子白名單：

1. 與組織的IT團隊合作，取得組織中使用的IP範圍清單
2. 請客戶支援委派聯絡Adobe客戶服務，並向Adobe提供IP範圍
3. 代理商會將IP範圍輸入白名單中，以防止工作階段在提供範圍內的同時過期。

## 因proxy而引起的問題

Adobe在向Adobe提出要求時使用授權標題。有些proxy(例如BlueCoat(現在由Symantec擁有)會移除Adobe Analytics使用的重要授權標題資訊。當Adobe看不到授權標題時，作業即過期。

若要解決此問題，Adobe建議您與組織的IT團隊合作，允許授權標題透過組織的proxy進行授權。

> [!NOTE] 注意
>
> 雖然Analytics社群成員發現下列連結有用，但並不屬於Adobe所有。檢視其內容時，請考量此附註。

Symantec proxy和驗證標題的資訊可在此處找到：

* [在ProxSG或ASG裝置上的Proxy鏈結部署中配置上游代理驗證](https://support.symantec.com/en_US/article.TECH246122.html)
* [允許ProxSG永遠在上游轉送伺服器授權](https://support.symantec.com/en_US/article.TECH244708.html)
