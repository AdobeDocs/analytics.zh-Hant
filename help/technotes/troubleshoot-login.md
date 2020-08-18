---
title: 疑難排解登入Adobe Analytics的問題
description: 無法登入Adobe Analytics時的步驟。
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---


# 疑難排解登入Adobe Analytics的問題

Adobe Analytics使用多種驗證方法登入：

* 透過Experience Cloud的Adobe ID
* 舊版Analytics ID
* 單一登入

**如果您定期存取Analytics並隨機開始遇到登入問題，清除瀏覽器的Cookie和快取可解決大部分問題。**

有時，可用性問題會影響登入功能。 檢 [查status.adobe.com](https://status.adobe.com/tw) ，查看任何未結案事件。 否則，請根據您組織的驗證方法使用適當的章節。

## Adobe ID

使用Experience Cloud登入Adobe Analytics的疑難排解問題。

1. 導覽至 [experience.adobe.com](https://experience.adobe.com)。 如果您無法存取此網站，您的組織可能不允許此網域透過防火牆。 與您組織的IT團隊合作，讓其得以運作。 如需 [提供給您IT團隊的實用資訊，請參閱Adobe Experience Cloud中使用的IP](https://helpx.adobe.com/tw/analytics/kb/adobe-ip-addresses.html) 和網域。

2. 使用Adobe ID進行驗證：按一 **[!UICONTROL 下「使用Adobe ID登入」]**。 如果您無法登入，請再次檢查您的電子郵件地址是否已正確輸入。 否則，按一 **[!UICONTROL 下重設密碼]** ，然後依照提示重設您的Adobe ID密碼。

3. 驗證後存取Analytics:按一下右上方的9格線圖示，然後按一下「分析」。 如果您沒有此選項或此選項呈灰色，請與組織內的產品管理員合作，以確定您擁有正確的存取Analytics權限。

## 舊版Analytics ID

有時，您組織中的使用者登入時會收到下列錯誤訊息：

*為了安全起見，由於登入嘗試失敗太多，此帳戶已遭鎖定。*

如果清除瀏覽器的Cookie/快取無法解決問題，請與組織中的Analytics管理員合作重設使用者密碼。

>[!IMPORTANT]
>
>下列重設使用者密碼的步驟僅適用於舊版Analytics ID，而非Adobe ID。如果貴組織使用Adobe ID，您可在 [adminconsole.adobe.com管理使用者帳戶](https://adminconsole.adobe.com)。

1. 使用具有管理權限的帳戶登入Adobe Analytics。
2. 導覽至「管 **[!UICONTROL 理員]** >使 **[!UICONTROL 用者管理]**」。
3. 按一下「 **[!UICONTROL 使用者]** 」標籤，然後按 **[!UICONTROL 一下所要使用者旁的「編輯]** 」。
4. 將密碼變更為任何值，並勾選「要求 **[!UICONTROL 使用者在下次登入時變更密碼」方塊]**。
5. 通知用戶新密碼。

## 單一登入

請洽詢您組織中的管理員，以解決單一登入問題。

## 其他登入問題

如果上述任何步驟都無法運作，請判斷登入問題的廣度：

* 問題是使用不同的瀏覽器時發生，還是在所有瀏覽器上都發生？
* 問題是發生在網路上的不同電腦上，還是跨多台電腦？
* 嘗試使用不同的網路登入，例如行動資料連線、資料庫或家庭網路。 跨網路的問題是否存在？

如果問題在您的網路中隔離，請與您組織的IT團隊合作解決。 如果不限於單一網路，請聯絡Adobe客戶服務。
