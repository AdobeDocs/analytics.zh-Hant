---
title: 反向連結
description: 顯示上次點擊的 URL (如果該點擊位於您的網站之外)。
translation-type: ht
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# 反向連結

「反向連結」維度會顯示訪客在到達您網站前所處 URL。例如，假設訪客從 `example.com/example-page.html` 點按連結找到您的網站，如果 `example.com/example-page.html` 沒有定義為您網域的一部分，那麼它就是反向連結。

此維度需要您設定報表套裝的[內部 URL 篩選器](/help/admin/admin/internal-url-filter-admin.md)。如果您未設定內部 URL 篩選器，Adobe Analytics 會將所有網域視為您網站的內部網域。

## 維度屬性

* 此維度預設使用最近的配置。
* 此維度依預設為在造訪結束後到期。
* 在 (低流量) 下將維度值分組前，此維度的不重複值上限為 500,000 個。Data Warehouse 沒有不重複限制。
* 如果量度沒有反向連結值，則會將其分組在 `Typed/Bookmarked` 下。
* 此維度通常設定在第一次的造訪點擊上，但也可以設定在中繼造訪上。

## 疑難排解

**問：為什麼我會看到`googleusercontent.com`這個維度值？**

答：[Google](https://about.google/) 將 `googleusercontent.com` 這個網域用於其託管內容。託管內容包括：

* **快取頁面**：Google的編目程式會持續編目網站並儲存網頁，以防網頁離線或無法使用。按一下 Google 其中一個搜尋結果頁面上的「快取」連結，即可在所有搜尋結果旁看見這些快取頁面。當使用者點按連結並查看您網站上的原始內容，`googleusercontent.com` 便將列為他們的反向連結網域。這些頁面具有下列子網域：`webcache.googleusercontent.com`。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。使用本服務檢視網站時，其來源為 `googleusercontent.com`。如果使用者點按連結返回原始內容，反向連結維度會顯示來自此網域的 URL。這些頁面具有下列子網域：`translate.googleusercontent.com`。
