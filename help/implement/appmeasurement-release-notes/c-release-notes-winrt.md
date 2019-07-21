---
description: 'null'
seo-description: 'null'
seo-title: WinRT for Windows 8
solution: Analytics、Marketing Cloud
subtopic: 發行說明
title: WinRT for Windows 8
topic: 開發人員和實施
uuid: cec19d63-114c-4ef6-a55 e-db6 aad4 e948 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# WinRT for Windows 8{#winrt-for-windows}

>[!NOTE]
>
>若要尋找目前的程式庫版本，請開啓偵錯記錄。

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>[!DNL WinRT][!DNL Windows] SDK的適用對象為 [Windows8.1通用應用程式商店](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) SDK。我們將不再對此 SDK 進行任何進一步的開發。

## 版本 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

發行日期: **2014 年 6 月 17 日**

隨附新功能的新版本包括地域位置、期限值、計時動作及加入支援。

## 版本 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

發行日期: **2014 年 5 月 22 日**

錯誤修正及效能改善。

## 3.1.0 版 {#section_F9059928B6FE43C99322A0DA35EB85C3}

發行日期: **2013 年 10 月 17 日**

* [!DNL Windows] 8.1相容性

## 版本 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

發行日期: **2013 年 4 月 18 日**

* 已修正導致先前作業長度有時會計算錯誤的問題。

## 版本 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

發行日期: **2013 年 3 月 21 日**

* `ADMS_Measurement.visitorID` 現在已預先填入預設值。
* 已修正擷取裝置資訊的問題。

## 版本 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

發行日期: **2013 年 2 月 21 日**

* 已取代 `offlineThrottleDelay`，因為此設定由於執行緒最佳化而不再需要。此設定仍然存在，以保留回溯相容性，但不再有任何作用。
* `DayOfWeek` 現在是以 1 為基礎並從週日開始算起，以符合在其他平台上收集的值。
* 在 TrackingHelper.js 中新增事件接聽程式的自動訂閱，以簡化生命週期追蹤。

## 版本 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

發行日期: **2012 年 11 月**

* 現在可在 C#、C++ 及 HTML5/WinJS 平台上準確收集螢幕解析度。
* `ADMS_Churn` 類別現在為內部。若要使用應用程式生命週期追蹤的最佳實務，請使用下列呼叫:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. 若註冊的作業長度已超過上限，則會傳送您設定的作業長度上限。Default `maxSessionLength` is 3600 (seconds).
* 新增 `lifecycleSessionTimeout` 組態變數，該變數可讓您指定在兩次應用程式啟動之間需經過的時間長度 (單位為秒)，超過該秒數後，該次啟動即視同新的作業階段。
* 將新的「前一個作業長度」量度新增至生命週期量度。
* 已更新 TrackingHelper 以詳細說明。
* 修正媒體模組錯誤。

## 版本 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**2012 年 10 月**

首次發行。
