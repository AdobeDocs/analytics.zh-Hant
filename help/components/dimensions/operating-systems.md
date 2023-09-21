---
title: 作業系統
description: 訪客的作業系統。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 26%

---

# 作業系統

「作業系統」 [維度](overview.md) 顯示訪客使用的作業系統和版本。 如果您的 Web 屬性中有作業系統專屬的功能，此維度可協助您了解哪些作業系統最常見。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包括訪客使用的作業系統。範例包括 `"Windows 10"`、`"OS X 10.15"`、 和 `"Android 9"`。

## 標籤和定義的變更

以下是作業系統如何在「使用者代理程式」和Adobe Analytics報表中的呈現特定問題清單。

### 作業系統詳細程度的變更

在2023年3月2日，我們更新了報告，在作業系統中加入更多細節。 在此日期之後，我們會加入作業系統修補程式版本。 舉例來說，使用OS X 10.15.7的使用者在3月2日之前應該出現為「OS X 10.15」。 在3月2日之後，它們會顯示為「OS X 10.15.7」。

### 變更Apple作業系統的命名慣例：

從第11版開始，我們會使用MacOS而非OS X來參照Apple作業系統。

範例：

* 「OS X 10.15」（請參閱下文關於10.15.7版超過UA字串表示法的說明）。
* 「MacOS 11.0.0

### 10.15.7版之後使用者代理程式中的Mac作業系統版本不正確 

Apple電腦上的使用者代理程式顯示作業系統版本為10.15.7 （即使是較新版本）。 之所以這麼做，是因為在UA中加入版本11顯然會造成某些網站的問題。 這適用於以下情況 *所有瀏覽器* 和Google在Chromium瀏覽器上「凍結」使用者代理程式沒有關聯。

請注意，使用者端提示包含在平台版本提示中的正確版本(「Sec-CH-UA-Platform-Version」)。 這是高平均資訊量提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 有關如何收集高平均資訊量提示的詳細資訊。

### 從Windows 11開始的使用者代理程式中的Windows版本不正確

截至2023年1月，所有瀏覽器中的使用者代理程式都會將Windows 11顯示為Windows 10。

請注意，使用者端提示包含在平台版本提示中的正確版本(「Sec-CH-UA-Platform-Version」)。 這是高平均資訊量提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 有關如何收集高平均資訊量提示的詳細資訊。
