---
title: 常見的機器人簽名
description: 識別bot的常用標識符。
feature: Bot Removal
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# 常見的機器人簽名

雖然在資料集中識別bot的方法因環境而異，但有幾種常見的識別bot的方法。

## 每次訪問的頁面視圖數

您可以提取具有IP地址、頁面視圖和唯一訪問者的Data Warehouse報告。 然後在Excel&#x200B;中為每次訪&#x200B;問的頁面視圖建立計算，然後從最高到最低排序。 Bot通常每次訪問都有非常多的頁面視圖（數百到數千）。 當你進入實際交通時，你會看到急劇的下降。

## 無引用者

Bot通常沒有引用URL。 在分段中，可以按 `Referring Domain equals Typed/Bookmarked`。

## 奇怪的用戶代理

Bot通常使用未在瀏覽器維中分類或顯示為 `unknown` 標準瀏覽器的版本。 未知的Safari和未知的Opera都極有可能成為機器人。

## Linux或「未指定」作業系統

我們不是想破壞大型開源Linux作業系統的信譽，但顯然僵屍會將它設定為作業系統。 但是，請注意將合法通信從Linux用戶中排除。 Bot還喜歡不設定作業系統，該作業系統可分段為 `Operating System &#x200B;equals Not Specified`。

## 頁面視圖=訪問=唯一訪問者

這尤其適用於用戶代理報告。 正如您在下面的螢幕截圖中看到的，這些瀏覽器的「未知版本」的訪問者數量幾乎與唯一訪問者相同（頁面視圖數量幾乎相同）。 這可以通過構建 [!UICONTROL 包括] 容器 `Single Page Visits equals Enabled` 或 `Hit Depth is less than 2`。

![](assets/bots-browsers-unknown.png)

## 訪問數1

機器人通常每次執行時都會獲得新的訪問者ID，因此每次訪問都只發生一次，其所有流量都將包含1次訪問。

## 降低顯示器解析度

現代用戶的解析度監視器比過去要高得多。 使用以下解析度的命中似乎很受bot的歡迎：

* 1024 x 768&#x200B;&#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* 未指定
* 1024 x 667

## 國家/地區+時區不匹配

您會注意到源國家和時區之間的不匹配。 例如，地點可能是美國，但時區可能是我的GMT。

![](assets/bots-country-time-zone.png)

## 未登錄

用戶在訪問中的任何時刻都不登錄，並且其用戶標識var在以前的訪問中不會持續。 雖然可以設定一些bot來進行驗證，但大多數機器人並不那麼聰明。

## 未訪問KPI

Bot通常不會將產品添加到購物車或簽出。 大多數情況下，他們不提交潛在客戶表單或其他成功事件，但某些bot確實提交了簡單的HTML表單。&#x200B;

## 存在特定查詢字串

有時，bot會通過點擊不存在的格式錯誤的URL或URL（如典型的LAMP或Wordpress管理頁）或附加特定查詢字串來嘗試中斷快取或中斷站點。

## 源自分佈式計算平台的IP地址

像Amazon Web Services或Google雲這樣的網路托管服務可能會被濫用為兩個農場。 這些IP地址極有可能是bot:&#x200B;
* [Google雲](https://cloud.google.com/compute/):IP地址以 `&#x200B;35.199` 或 `35.194&#x200B;`
