---
title: 選擇退出連結
description: 瞭解如何為網站的訪客建立實施選擇退出連結。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 實施選擇退出連結

>[!IMPORTANT] Adobe 建議使用選擇加入服務，尤其是針對涉及 GDPR 法規的組織。請參閱 Experience Cloud Identity Service 使用指南中的[選擇加入服務概述](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)。

網站的某些訪客不希望您的資料集內含有他們的瀏覽資訊。Adobe 提供的功能，讓您得以提供網站訪客選擇退出的方法，拒絕他人收集個人資訊。所有實施類型都能獲得滿足；貴組織需自行負責隱私權原則，以及遵守您簽署的條款。

當訪客到達選擇退出 URL 時，系統會提示他們安裝選擇退出 Cookie。如果使用者選擇不進行追蹤且設定選擇退出 Cookie，您的 JavaScript 檔案會繼續將資料傳送至 Adobe 伺服器。不過這些資料不會經過處理，也不會納入報表。

>[!TIP] Adobe 另提供隱私權設定給每個報表套裝。請參閱「管理員使用指南」中的[隱私權設定](../../admin/admin/privacy-settings.md)。

## 退出 URL

貴組織的退出頁面取決於實施中的 [`trackingServer`](../vars/config-vars/trackingserver.md) 變數值。

* 在 Adobe Experience Platform Launch 中：
   1. 登入 [launch.adobe.com](https://launch.adobe.com)，然後按一下所需的屬性。
   2. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
   3. 按一下 [!UICONTROL General] accordion，並記下 [!UICONTROL Tracking Server] 值。

* 在 JavaScript 實施中：
   1. 在網頁伺服器上，利用程式碼或文字編輯器開啟網站使用的 AppMeasurement.js 檔案。
   2. 記下 `trackingServer` 變數值。

* 使用 [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)：
   1. 使用 Chrome 瀏覽器導覽至您的網站。
   2. Open the Experience Cloud Debugger, then go to the [!UICONTROL Network tab].
   3. Note the [!UICONTROL Request URL - Hostname] value.

找出實施的 `trackingServer` 網域後，將路徑 `/optout.html` 附加至結尾。例如：

* 第三方 Cookie：`https://example.sc.omtrdc.net/optout.html`
* 第一方 Cookie：`https://stats.example.com/optout.html`

## 選擇退出查詢字串參數

您可以使用查詢字串將設定自動載入此頁面。

### 地區

加入 `locale` 查詢字串參數，自動切換選擇退出頁面的語言。將以下任一值指派給此查詢字串參數：

* en_US (英文，預設)
* bg_BG (保加利亞文)
* zh_CN (簡體中文)
* zh_TW (繁體中文)
* cs_CZ (捷克文)
* da_NK (丹麥文)
* nl_NL (荷蘭文)
* et_EE (愛沙尼亞文)
* fi_FI (芬蘭文)
* fr_FR (法文)
* de_DE (德文)
* el_GR (希臘文)
* it_IT (義大利文)
* jp_JP (日文)
* ko_KR (韓文)
* lv_LV (拉脫維亞文)
* lt_LT (立陶宛文)
* nb_NO (挪威文)
* pl_PL (波蘭文)
* pt_BR (葡萄牙文)
* sk_SK (斯洛伐克文)
* es_ES (西班牙文)

例如，`https://example.sc.omtrdc.net/optout.html?locale=ko_KR` 會以韓文載入選擇退出頁面。

>[!TIP] `en_US` 查詢字串值不是必要值，因為頁面預設會以英文載入。

### 快顯視窗

在頁面中新增「關閉視窗」按鈕，保留將選擇退出頁面變成快顯視窗的可能。使用 `popup` 查詢字串參數，並指定 `1` 值。

例如，`https://example.sc.omtrdc.net/optout.html?popup=1` 會載入包含「關閉視窗」按鈕的選擇退出頁面。

>[!NOTE] 在過去，此查詢字串參數會強制顯示快顯視窗。不過現代化的瀏覽器大多將快顯視窗的控制權交給一般使用者。

### 單一點擊選擇退出

允許使用者立即選擇退出追蹤。新增 `opt_out` 和 `confirm_change` 兩個查詢字串參數，並為每個參數指定 `1` 值。

例如，`https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` 會立即將選擇退出 Cookie 安裝在訪客頁面上。

### 單一點擊選擇加入

透過刪除選擇退出 Cookie，讓使用者立即選擇重新加入追蹤。新增 `opt_in` 和 `confirm_change` 兩個查詢字串參數，並為每個參數指定 `1` 值。

例如，`https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` 會立即刪除訪客的選擇退出 Cookie。
