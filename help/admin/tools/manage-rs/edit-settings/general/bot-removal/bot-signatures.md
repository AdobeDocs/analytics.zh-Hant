---
title: 常見的機器人簽名
description: 辨識機器人的常見識別碼。
feature: Bot Removal
role: Admin
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---

# 常見的機器人簽名

雖然辨識資料集中的機器人會因環境而異，下面還是提供幾個辨識機器人的常見方式。

## 每次造訪的頁面瀏覽數很高

您可以提取包含 IP 位址、頁面瀏覽數和不重複訪客的 Data Warehouse 報表。 然後在 Excel 中建立計算，以得出每次造訪的頁面瀏覽數，並從最高排序到最低。 通常機器人每次造訪的頁面瀏覽數會很高 (幾百到幾千)。 當您進入實際流量時，會看到這個數字急劇下降。

## 沒有反向連結

機器人通常沒有反向連結 URL。 在分段中，這可以被篩選為 `Referring Domain equals Typed/Bookmarked`。

## 奇怪的使用者代理

機器人經常會使用未歸類在瀏覽器維度中的使用者代理，或是顯示為標準瀏覽器的 `unknown` 版本。 不明 Safari 和不明 Opera 極有可能是因為使用機器人。

## Linux 或「未指定」作業系統

我們並不是要詆毀偉大的開放原始碼 Linux 作業系統，但顯然機器人喜歡將 Linux 設定為作業系統。 不過，在排除來自 Linux 使用者的合法流量時，請務必謹慎。 機器人也喜歡不設定作業系統，這可以分段為 `Operating System &#x200B;equals Not Specified`。

## 頁面瀏覽數 = 造訪數 = 不重複訪客數

這尤其適用於使用者代理報表。 如您在底下螢幕擷圖中所見，這些瀏覽器的「不明版本」的訪客數幾乎與不重複訪客數相同 (而且頁面瀏覽數也幾乎相同)。 您可以為 `Single Page Visits equals Enabled` 或 `Hit Depth is less than 2` 建立 [!UICONTROL Include] 容器，將此隔離於分段中。

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-browsers-unknown.png)

## 造訪數為 1

機器人通常在每次執行時都會得到新的訪客 ID，因此只會發生一次造訪，而且其所有流量都是由造訪數 1 所組成。

## 螢幕解析度較低

當今使用者的螢幕解析度比過去幾年的使用者高許多。 機器人似乎很常用具有以下解析度的點擊：

* 1024 x 768
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* 未指定
* 1024 x 667

## 國家/地區 + 時區不相符

您會注意到來源國家/地區與時間不相符。 例如，位置可能是美國，但時區卻可能是 GMT。

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-country-time-zone.png)

## 未登入

使用者在造訪期間的任何時間點都不會登入，而且其使用者識別 eVar 不會從先前的造訪中保存下來。 雖然某些機器人可以設定為能夠進行驗證，但大多數的機器人沒有那麼聰明。

## 造訪中沒有 KPI

機器人通常不會新增商品到購物車或結帳。 在大多數期間，機器人不會提交潛在客戶表單或其他成功事件，但某些機器人確實會提交簡單的 HTML 表單。 

## 存在著特定查詢字串

有時機器人會嘗試透過點擊格式錯誤的 URL 或不存在的 URL (例如典型的 LAMP 或 Wordpress 管理員頁面) 或藉由附加特定查詢字串來破壞快取或網站。

## 源自於分散式運算平台的 IP 位址

網站託管服務 (例如 Amazon Web Services 或 Google 雲端) 可能會被濫用為機器人農場。 以下 IP 位址很容易成為機器人：
&#x200B;
* [Google 雲端](https://cloud.google.com/compute/)：以 `&#x200B;35.199` 或 `35.194&#x200B;` 開頭的 IP 位址
