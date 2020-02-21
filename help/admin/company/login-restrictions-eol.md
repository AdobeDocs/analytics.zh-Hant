---
title: '[!UICONTROL 強制 IP 登入限制]服務終止'
description: 瞭解[!UICONTROL 強制 IP 登入限制]的終止時間及實作
translation-type: ht
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# [!UICONTROL 強制 IP 登入限制]服務終止

Adobe Analytics 的&#x200B;**[強制 IP 登入限制](/help/admin/company/security-manager.md)**功能可讓您將特定 IP 位址加入白名單 (視為安全位址)，以便允許這些位址成功登入並存取您的 Adobe Analytics 環境。在許多情況下，此功能可用於將公司 IP 位址設為使用者唯一可登入的安全 IP 位址。因此，若要使用 Adobe Analytics，使用者必須位於公司辦公室或透過 VPN 登入網路。

我們計畫於 2020 年 10 月終止此功能。

## 我們為什麼要終止此功能？

某些情況下，Experience Cloud 登入移轉和/或 Experience Cloud 登入會導致此功能中斷。據悉，此功能會在客戶使用&#x200B;**[!UICONTROL 客戶屬性]**&#x200B;或&#x200B;**[!UICONTROL 對象庫]**&#x200B;時中斷。

此外，如果您擁有多個 Experience Cloud 解決方案，則可以藉由其他解決方案登入 Experience Cloud 來規避此功能需求，因為這項功能並不存在或受支援於 Analytics 本身之外。使用者透過假 IP，也能解決這個問題。

最後，Adobe 也透過單一登入和 Federated ID 提供運作正常且更為優異的替代解決方案。此功能可讓您對使用者的登入體驗提供更大的掌控度與安全性。請參閱參下方瞭解詳情。

## 移除此功能對您有何影響？

如您是已設定&#x200B;**[!UICONTROL 強制 IP 登入限制]**&#x200B;的客戶，此功能將於 2020 年 10 月移除。屆時，任何已設定的 IP 登入限制將無法再執行。如果您仍需依 IP 位址限制登入，請考量並實作我們建議的單一登入與 Federated ID 解決方案 (下方提供更多資訊與資源)。

此外，我們也會從 Analytics UI 的&#x200B;**[!UICONTROL 管理員 > 公司設定 > 安全管理員]**&#x200B;中移除&#x200B;**[!UICONTROLA強制 IP 登入限制]**&#x200B;設定 (如下所示)。

![](assets/sec-manager2.png)

## 您有哪些其他選項？

一如上文所述，此 Analytics 功能即將終止。為了讓您有餘裕實作 SSO 和 Federated ID，我們已將終止日期延遲至 2020 年 10 月。

SSO 和 Federated ID 都是我們目前已具備的 IP 登入限制功能解決方案，可為您提供更優越的控制、安全性和功能。如需瞭解如何設定 SSO/Federated ID，您可以參考下列說明文件。建議您仔細閱讀，並與 IT 部門合作，以便確實加以實作：

* [單一登入與 Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - 身分設定文件](https://helpx.adobe.com/tw/enterprise/using/set-up-identity.html)
* [Admin Console - 身分設定教學課程 (影片)](https://helpx.adobe.com/tw/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [設定 Federated ID 教學課程 (影片)](https://helpx.adobe.com/tw/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [單一登入 - 常見問題](https://helpx.adobe.com/tw/enterprise/using/sso-faq.html)
* [Adobe 支援的身分類型](https://helpx.adobe.com/tw/enterprise/using/identity.html)

如果您希望持續表達支持 IP 登入限制功能，並希望 Experience Cloud 提供支援，您可在我們的[論壇頁面](https://forums.adobe.com/ideas/11648)上投票支持此功能。