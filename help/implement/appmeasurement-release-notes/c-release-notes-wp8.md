---
description: 'null'
seo-description: 'null'
seo-title: Windows Phone 8
solution: Analytics,Experience Cloud
subtopic: 發行說明
title: Windows Phone 8
topic: 開發人員和實作
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>若要尋找目前的程式庫版本，請開啟除錯記錄。

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL Windows] Phone 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. 我們將不再對此 SDK 進行任何進一步的開發。

## 版本 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

發行日期: **2013 年 8 月 21 日**

* 「內容資料」密鑰現在可使用底線。

## 版本 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

發行日期: **2013 年 5 月 22 日**

* 錯誤修正及效能改善。

## 版本 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

發行日期: **2013 年 4 月 18 日**

* 已修正導致先前作業長度有時會計算錯誤的問題。

## 版本 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

發行日期: **2013 年 3 月 21 日**

* 已修正 `DateTime` 物件的本地化問題。

## 版本 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

發行日期: **2013 年 2 月 26 日**

* `ADMS_Measurement.visitorID` 現在會預先填入預設值。
* 已修正有時會導致快取自動回應的問題。

## 版本 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

發行日期: **2013 年 2 月 21 日**

* 已取代 `offlineThrottleDelay`，因為此設定由於執行緒最佳化而不再需要。此設定仍然存在，以保留回溯相容性，但不再有任何作用。
* `DayOfWeek` 現在是以 1 為基礎並從週日開始算起，以符合在其他平台上收集的值。
* 修正離線儲存體的問題，該問題有時會導致應用程式當機。

