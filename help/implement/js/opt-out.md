---
title: 選擇退出連結
description: 瞭解如何為網站的訪客建立實施選擇退出連結。
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 67%

---

# 實施選擇退出連結

>[!IMPORTANT]
>
> 本文為（計畫）在其網站上實作Adobe Analytics **的** Adobe Analytics客戶提供有關如何為網站使用者提供選擇退出連結的說明。 <p><p>
><p>-ERR:REF-NOT-FOUND-<p>-ERR:REF-NOT-FOUND-> 如果您&#x200B;**正在造訪已實作Adobe Analytics**&#x200B;的網站，而您想要選擇退出，**<span style="color:red">本文不適合您</span>**。 請參閱[Adobe隱私權選擇](https://www.adobe.com/tw/privacy/opt-out.html)以控制Adobe如何使用您的資訊。

網站的某些訪客不希望您的資料集內含有他們的瀏覽資訊。Adobe可讓您的網站訪客選擇退出分析，選擇退出分析。

您可使用選擇退出連結讓網站訪客在Analytics報表中忽略其資料。 這些連結僅限於AppMeasurement實作；Adobe建議改用[Adobe Experience Cloud選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)。 選擇加入服務更加健全，可跨多種Adobe Experience Cloud產品運作，包括Adobe Analytics和AppMeasurement。

當訪客到達選擇退出 URL 時，系統會提示他們安裝選擇退出 Cookie。如果使用者選擇不被追蹤且已設定選擇退出Cookie，AppMeasurement會繼續將資料傳送至Adobe。 不過這些資料不會經過處理，也不會納入報表。

>[!TIP]
>
>Adobe 另提供隱私權設定給每個報表套裝。請參閱「管理員使用指南」中的[隱私權設定](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md)。

## 退出 URL

貴組織的退出頁面取決於實作中的 [`trackingServer`](../vars/config-vars/trackingserver.md) 變數值。

* 在Analytics擴充功能中：
   1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
   1. 按一下所需的標籤屬性。
   1. 按一下「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 下方的「[!UICONTROL 設定]」。
   1. 按一下[!UICONTROL 「一般」]摺疊式功能表，接著記下[!UICONTROL 「追蹤伺服器」]值。

* 在 JavaScript 實作中：
   1. 在網頁伺服器上，利用程式碼或文字編輯器開啟網站使用的 AppMeasurement.js 檔案。
   1. 記下 `trackingServer` 變數值。

* 使用 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html?lang=zh-Hant)：
   1. 使用 Chrome 瀏覽器導覽至您的網站。
   1. 開啟 Experience Cloud Debugger，然後前往[!UICONTROL 「網路」]標記。
   1. 記下[!UICONTROL 「要求 URL - 主機名稱」]值。

找出實作的 `trackingServer` 網域後，將路徑 `/optout.html` 附加至結尾。例如：

* 協力廠商 Cookie：`https://example.data.adobedc.net/optout.html`
* 第一方 Cookie：`https://stats.example.com/optout.html`

## 選擇退出查詢字串參數

您可以使用查詢字串將設定自動載入此頁面。

### 地區

加入 `locale` 查詢字串參數，自動切換選擇退出頁面的語言。將以下任一值指派給此查詢字串參數：

* `en_US` （英文，預設）
* `bg_BG` （保加利亞文）
* `zh_CN` （簡體中文）
* `zh_TW` （繁體中文）
* `cs_CZ` （捷克文）
* `da_NK` （丹麥文）
* `nl_NL` （荷蘭文）
* `et_EE` （愛沙尼亞文）
* `fi_FI` （芬蘭文）
* `fr_FR` （法文）
* `de_DE` （德文）
* `el_GR` （希臘文）
* `it_IT` （義大利文）
* `jp_JP` （日文）
* `ko_KR` （韓文）
* `lv_LV` （拉脫維亞文）
* `lt_LT` （立陶宛文）
* `nb_NO` （挪威文）
* `pl_PL` （波蘭文）
* `pt_BR` （葡萄牙文）
* `sk_SK` （斯洛伐克文）
* `es_ES` （西班牙文）

例如，`https://example.data.adobedc.net/optout.html?locale=ko_KR` 會以韓文載入選擇退出頁面。

### 快顯視窗

在頁面中新增「關閉視窗」按鈕，保留將選擇退出頁面變成快顯視窗的可能。使用 `popup` 查詢字串參數，並指定 `1` 值。

例如，`https://example.data.adobedc.net/optout.html?popup=1` 會載入包含「關閉視窗」按鈕的選擇退出頁面。

>[!NOTE]
>
>在過去，此查詢字串參數會強制顯示快顯視窗。不過現代化的瀏覽器大多將快顯視窗的控制權交給一般使用者。

### 單一點擊選擇退出

允許使用者立即選擇退出追蹤。新增 `opt_out` 和 `confirm_change` 兩個查詢字串參數，並為每個參數指定 `1` 值。

例如，`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` 會立即將選擇退出 Cookie 安裝在訪客頁面上。

### 單一點擊選擇加入

透過刪除選擇退出 Cookie，讓使用者立即選擇重新加入追蹤。新增 `opt_in` 和 `confirm_change` 兩個查詢字串參數，並為每個參數指定 `1` 值。

例如，`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` 會立即刪除訪客的選擇退出 Cookie。
