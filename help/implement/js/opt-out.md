---
title: 退出連結
description: 瞭解如何為您網站的訪客建立實作退出連結。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# 實作退出連結

> [!IMPORTANT] Adobe建議使用選擇服務，尤其是針對符合GDPR法規的組織。 See [Opt-in service overview](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) in the Experience Cloud Identity Service user guide.

您網站的某些訪客不希望其瀏覽資訊包含在您的資料集中。 Adobe提供的功能是，為網站的訪客提供選擇退出所收集資訊的方式。 所有實施類型都得到滿足；貴組織需自行負責隱私權政策，並遵守您簽署的條款。

當訪客到達選擇退出URL時，會提示他們安裝選擇退出Cookie。 如果使用者選擇不進行追蹤並設定選擇退出Cookie，您的JavaScript檔案會繼續傳送資料至Adobe伺服器。 但是，該資料不會處理或包含在報表中。

> [!TIP] Adobe也提供每個報表套裝的隱私權設定。 請參 [閱「管理員](../../admin/admin/privacy-settings.md) 」使用指南中的「隱私權設定」。

## 退出URL

您組織的退出頁面取決於您實作 [`trackingServer`](../vars/config-vars/trackingserver.md) 中的變數值。

* 在Adobe Experience Platform Launch中：
   1. 登入 [launch.adobe.com](https://launch.adobe.com) ，然後按一下所要的屬性。
   2. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
   3. 按一下「 [!UICONTROL 一般] 」accordion，並記下「追 [!UICONTROL 蹤伺服器] 」值。

* 在JavaScript實作中：
   1. 在您的網頁伺服器上，在程式碼或文字編輯器中開啟您網站上使用的AppMeasurement.js檔案。
   2. 請注意 `trackingServer` 變數值。

* Using the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. 使用Chrome瀏覽器導覽至您的網站。
   2. 開啟Experience cloud除錯程式，然後前往「網 [!UICONTROL 路」標籤]。
   3. 請注意 [!UICONTROL 「請求URL —— 主機名稱] 」值。

找到實作的網域後， `trackingServer` 請將路徑附 `/optout.html` 加至結尾。 例如:

* 協力廠商Cookie: `https://example.sc.omtrdc.net/optout.html`
* 第一方 Cookie: `https://stats.example.com/optout.html`

## 退出查詢字串參數

您可以使用查詢字串自動載入此頁面的設定。

### 地區

加入查詢字串參數，自動切換選擇退出頁面 `locale` 的語言。 指派此查詢字串參數以下值之一：

* en_US（英文，預設）
* bg_BG（保加利亞文）
* zh_CN（簡體中文）
* zh_TW（繁體中文）
* cs_CZ（捷克文）
* da_NK（丹麥文）
* nl_NL（荷蘭文）
* et_EE（愛沙尼亞文）
* fi_FI（芬蘭文）
* fr_FR（法文）
* de_DE（德文）
* el_GR（希臘文）
* it_IT（義大利文）
* jp_JP（日文）
* ko_KR（韓文）
* lv_LV（拉脫維亞文）
* lt_LT（立陶宛文）
* nb_NO（挪威文）
* pl_PL（波蘭文）
* pt_BR（葡萄牙文）
* sk_SK（斯洛伐克文）
* es_ES（西班牙文）

例如， `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` 以韓文載入退出頁面。

> [!TIP] 查詢 `en_US` 字串值不是必要值，因為頁面依預設會以英文載入。

### 彈出畫面

新增「關閉視窗」按鈕至頁面，讓潛在使用者將退出頁面變成快顯視窗。 使用查 `popup` 詢字串參數，並為其指定值 `1`。

例如，載 `https://example.sc.omtrdc.net/optout.html?popup=1` 入包含「關閉視窗」按鈕的退出頁面。

> [!NOTE] 歷史上，此查詢字串參數會強制出現快顯視窗。 不過，大部份的現代瀏覽器都能讓使用者控制彈出式視窗。

### 單鍵退出

允許使用者立即選擇退出追蹤。 新增兩個查詢字串參 `opt_out` 數 `confirm_change`，並為每個參數指定值 `1`。

例如， `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` 立即在訪客頁面上安裝退出Cookie。

### 單鍵選擇加入

可讓使用者透過刪除退出Cookie，立即選擇退回追蹤。 新增兩個查詢字串參 `opt_in` 數 `confirm_change`，並為每個參數指定值 `1`。

例如，立 `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` 即刪除訪客的退出Cookie。
