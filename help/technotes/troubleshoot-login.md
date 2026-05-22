---
title: 疑難排解登入 Adobe Analytics 的問題
description: 無法登入 Adobe Analytics 時應採取的步驟。
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
TQID: https://experienceleague.adobe.com/akXZpx8BUywqvI2NGvk9dqIBL-pHEAza1-I05pC89io
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 607
ht-degree: 88%

---

# 疑難排解登入 Adobe Analytics 的問題

Adobe Analytics 會使用多種驗證方法來登入：

* 透過CX Enterprise的Adobe ID
* 舊版 Analytics ID
* 單一登入

**如果您定期存取 Analytics 且開始遇到隨意的登入問題，您可清除瀏覽器的 Cookie 和快取記憶即可解決大部分問題。**

有時，可用性問題會影響登入功能。 查看 [status.adobe.com](https://status.adobe.com/zh-tw)，了解任何未結案的事件。 否則，請根據您組織的驗證方法使用適當的章節。

## Adobe ID

使用CX Enterprise登入Adobe Analytics的疑難排解問題。

1. 導覽至[Adobe CX Enterprise](https://experience.adobe.com)。 如果您無法存取此網站，可能是您的組織設有防火牆而不允許您使用此網域。 請讓您組織的 IT 團隊允許您存取此網站。 如需要為您IT團隊提供實用資訊，請參閱[Adobe Analytics使用的IP位址](/help/technotes/ip-addresses.md)。

2. 使用 Adobe ID 進行驗證：按一 下「**[!UICONTROL 使用 Adobe ID登入]**」。 如果您無法登入，請再次檢查您輸入的電子郵件地址是否正確。 否則，請按一下「**[!UICONTROL 重設密碼]**」，然後依照提示重設您的 Adobe ID 密碼。

3. 驗證後存取 Analytics：按一下右上方的 9 格線圖示，然後按一下「Analytics」。 如果您沒有此選項或此選項呈灰色，請找您組織內的產品管理員，確定您擁有存取 Analytics 的正確權限。

## 舊版 Analytics ID

您組織中的使用者嘗試登入時，可能會收到下列錯誤：

*為了安全起見，由於登入嘗試失敗太多，此帳戶已遭鎖定。*

如果清除瀏覽器的 Cookie/快取記憶無法解決問題，請找組織內的 Analytics 管理員為您重設使用者密碼。

>[!IMPORTANT]
>
>下列重設使用者密碼的步驟僅適用於舊版Analytics ID，不適用於Adobe ID。 如果您的組織使用Adobe ID，您可以在[adminconsole.adobe.com](https://adminconsole.adobe.com)管理使用者帳戶。

1. 使用具備管理權限的帳戶登入 Adobe Analytics。
2. 瀏覽至「**[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 使用者管理]**」。
3. 按一下「**[!UICONTROL 使用者]**」標籤，然後按 一下所要使用者旁的「**[!UICONTROL 編輯]**」。
4. 將密碼變更為任何值，並勾選「**[!UICONTROL 要求使用者在下次登入時變更密碼]**」。
5. 通知用戶新密碼。

## 單一登入

請洽詢您組織中的管理員，以解決單一登入問題。

## 過期登入

您組織中的使用者嘗試登入時，可能會收到下列錯誤：

*錯誤：此登入已過期。*

此錯誤如預期運作。 Adobe Analytics 可讓管理員設定使用者帳戶有效的日期範圍。 如果目前日期在帳戶有效日期範圍以外，即無法登入。 請找您組織內的 Analytics 管理員，為您延長登入的有效日期範圍。 Adobe客戶服務無權變更使用者帳戶的有效登入日期範圍。

## 其他登入問題

如果上述任何步驟都無法運作，請確定登入問題的範圍：

* 問題是使用不同的瀏覽器時會發生，還是在所有瀏覽器上都發生？
* 問題是發生在網路的不同一台電腦上？或是發生在跨多台電腦上？
* 嘗試使用不同的網路登入，例如行動資料連線、圖書館或家庭網路。 問題是否在跨網路中出現？

如果問題單獨存在於您的網路中，請找您組織的 IT 團隊解決問題。 如果不限於單一網路，請聯絡 Adobe 客戶服務。
