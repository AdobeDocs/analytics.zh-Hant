---
title: 反向連結
description: 顯示先前點擊的URL（如果該點擊位於您的網站外）。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# 反向連結

「反向連結」維度顯示訪客在到達您網站前所處的URL。 例如，如果訪客點按某個連結並 `example.com/example-page.html` 進入您的網站， `example.com/example-page.html` 則未定義為您網域的一部分的反向連結。

此維度需要您設定報表套裝的內部 [URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 如果您未設定內部URL篩選器，Adobe Analytics會將所有網域視為您網站的內部網域。

## 維屬性

* 依預設，此維度會使用最近的配置。
* 依預設，此維度會在瀏覽後過期。
* 在（低流量）下將維度值分組之前，此維度受500k唯一限制的約束。 資料倉庫沒有唯一限制。
* 如果度量沒有反向連結值，則會將其分組在下方 `Typed/Bookmarked`。
* 此維度通常會在瀏覽的首次點擊上設定，但可設定在瀏覽中間。

## 疑難排解

**問：我為何將`googleusercontent.com`視為維度值？**

答： [Google](https://about.google/) ，將網域用 `googleusercontent.com` 於其代管內容。 代管內容包括：

* **快取頁面**:Google的蜘蛛程式會不斷地編目網頁，並儲存網頁，以防網頁離線或無法使用。 按一下Google其中一個搜尋結果頁面的「快取」連結，即可在所有搜尋結果旁取得這些快取頁面。 當使用者按一下此連結，然後查看您網站上的原始內容時， `googleusercontent.com` 會列為其反向連結網域。 這些頁面具有子網域 `webcache.googleusercontent.com`。
* **翻譯的頁面**:Google提供強大而方便的翻譯服務。 使用本服務檢視網站時，其來源為 `googleusercontent.com`。 如果使用者按一下連結以返回原始內容，反向連結維度會顯示此網域的URL。 這些頁面具有子網域 `translate.googleusercontent.com`。
