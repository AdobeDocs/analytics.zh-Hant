---
description: 跨裝置訪客身分識別可協助您連結多個裝置間的訪客。跨裝置訪客識別會使用訪客 ID 變數 s.visitorID，為使用者建立裝置間的關聯。
keywords: Analytics Implementation
subtopic: Visitors
title: 連結跨裝置的使用者
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# 連結跨裝置的使用者

> [!IMPORTANT]不建議您繼續使用這種跨裝置識別訪客的方法。請參 [閱「元件」使用指南](/help/components/cda/cda-home.md) 中的「跨裝置分析」。

跨裝置訪客身分識別可協助您連結多個裝置間的訪客。Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. 識別 `visitorID` 獨特訪客時，變數會優先處理最高順序。

當您使用自訂訪客ID傳送點擊時，Adobe會檢查是否有任何具有相符訪客ID的訪客描述檔。 如果訪客資料存在，系統中已有的訪客資料會從此開始使用，而不再使用先前的訪客資料。

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. 有效識別碼包括其使用者名稱、電子郵件地址的雜湊，或不含任何個人識別資訊的內部ID。

客戶從每個裝置登入後，都會系結至相同的使用者個人檔案。 如果訪客稍後登出裝置，則他們仍屬於相同的訪客資料，因為Adobe會識別每個裝置上的瀏覽器Cookie屬於相同的訪客資料。 Adobe建議在刪除瀏 `visitorID` 覽器Cookie時盡可能使用變數。

## 限制

使用您自己的自訂訪客ID，可讓您更能控制訪客的識別方式，但有其限制。

* **訪客重複資料刪除不具可回溯性**:如果訪客首次存取您的網站，然後進行驗證，則會計入兩個獨特訪客。 一個獨特訪客會自動產生一般Analytics ID計數，另一個則會計算自訂訪客ID的登入計數。 每次訪客使用新裝置或清除其Cookie時，都會出現此獨特訪客的複製。
* **與Experience Cloud ID服務不相容**:自從跨裝置訪客身分識別問世以來，Adobe已推出更強大、更可靠的方式來跨裝置追蹤訪客。 這些新的識別方法與自訂訪客ID覆寫不相容。 如果您打算使用ID服務、跨裝置分析(CDA)或Device co-op,Adobe強烈建議不要使用變 `visitorID` 數。
