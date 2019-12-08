---
description: 'null'
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# PHP{#php}

> [!NOTE]若要尋找目前的程式庫版本，請開啟偵錯記錄功能。

## 版本 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

發行日期: **2014 年 8 月**

* 進行內部變更，以支援未來功能。

## 版本 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

發行日期: **2012 年 7 月**

* 針對在 IIS 中 $_SERVER['HTTPS'] 傳回的 "off" 新增一項檢查。若沒有此檢查，不論是透過 HTTP 或 HTTPS 進行要求，轉型為布林值 ((bool)$_SERVER['HTTPS']) 會在 IE 中傳回 true。這會導致不安全的頁面嘗試進行安全的影像要求。

## 版本 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

PHP 1.1 的「測量庫」包括下列 1.0 版的更新:

* 「地域劃分」更準確 (當 `sendFromServer` 啟用時)。
* 已修正錯誤，因此使用者現在可附加 `userAgent` 變數。
* 影像信標現已與更多行動瀏覽器更相容。
* 行動裝置啟用時，`imageDimensions` 變數的預設值為 5x5。
* 已調整機器人偵測清單。
* 已在 `debugTracking` 和 `sendFromServer` 啟用時，新增除錯資訊 (HTTP 標頭、回應、錯誤等)。

* 已新增 `debugFilename` 變數 (當 `sendFromServer` 啟用時)。

* 當 `pagename` 或 `pageURL` 皆未設定時，頁面名稱變數會預設為 `$_SERVER['SCRIPT_NAME']`。

* 完全支援 PHP 的 CGI 實施。
* 效能改良。

