---
description: 'null'
seo-description: 'null'
seo-title: PHP
solution: Analytics
subtopic: 發行說明
title: PHP
topic: 開發人員和實施
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>若要尋找目前的程式庫版本，請開啓偵錯記錄。

## 版本 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

發行日期: **2014 年 8 月**

* 進行內部變更，以支援未來功能。

## 版本 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

發行日期: **2012 年 7 月**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. 這會導致不安全的頁面嘗試進行安全的影像要求。

## 版本 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

PHP 1.1 的「測量庫」包括下列 1.0 版的更新:

* 「地域劃分」更準確 (當 `sendFromServer` 啟用時)。
* 已修正錯誤，因此使用者現在可附加 `userAgent` 變數。
* 影像信標現已與更多行動瀏覽器更相容。
* 行動裝置啟用時，`imageDimensions` 變數的預設值為 5x5。
* 已調整機器人偵測清單。
* 已在 `debugTracking` 和 `sendFromServer` 啟用時，新增除錯資訊 (HTTP 標頭、回應、錯誤等)。

* Added the `debugFilename` variable (when `sendFromServer` is enabled).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* 完全支援 PHP 的 CGI 實施。
* 效能改良.

