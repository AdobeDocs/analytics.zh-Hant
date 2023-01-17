---
title: 作業系統
description: 訪客的作業系統。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 26de81f090cebb45473a04a2edbe281f1c8591a4
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 34%

---

# 作業系統

「作業系統」維度會顯示訪客使用的作業系統和版本。如果您的 Web 屬性中有作業系統專屬的功能，此維度可協助您了解哪些作業系統最常見。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包括訪客使用的作業系統。範例包括 `"Windows 10"`、`"OS X 10.15"`、 和 `"Android 9"`。

## 標籤和定義的變更

以下是使用者代理和Adobe Analytics報表中如何呈現作業系統的特定問題清單。

### 變更Apple作業系統的命名慣例：

從第11版開始，我們將使用OS X而非Mac OS來指稱Apple作業系統。

範例：

* macOS 10.15.7版(請參閱下方關於10.15.7版，而非UA字串中的表示法的說明)。
* OS X 11.0.0版

### Mac OS版本在10.15.7版之後的使用者代理中不正確 

自2023年1月起，所有瀏覽器中的「使用者代理」都會將Mac OS版本顯示為10.15.7（即使是較新版本）。 這樣做是因為將第11版納入UA顯然造成了一些網站的問題。 Apple也指出，在UA中加入錯誤的作業系統版本可提供一些隱私權優勢。

請注意，用戶端提示在平台版本提示(「Sec-CH-UA-Platform-Version」)中包含正確的版本。 這是高熵提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 詳細了解如何收集高熵提示。

### 從Windows 11開始，用戶代理中的Windows版本不正確

自2023年1月起，所有瀏覽器中的使用者代理將Windows 11顯示為Windows 10。

請注意，用戶端提示在平台版本提示(「Sec-CH-UA-Platform-Version」)中包含正確的版本。 這是高熵提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 詳細了解如何收集高熵提示。
