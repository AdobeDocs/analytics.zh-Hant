---
title: 行動查閱維度
description: 根據裝置 IP 位址和使用者代理程度的維度。
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 100%

---

# 行動查閱維度

*此頁面會參考對您的網站進行存取之行動裝置的屬性。請參閱「[行動生命週期維度](lifecycle-dimensions.md)」或「[行動生命週期量度](../metrics/lifecycle-metrics.md)」，了解在行動應用程式內進行追蹤。*

行動查詢[維度](overview.md)可讓您深入分析造訪網站之行動裝置的屬性。這些屬性是以點擊的使用者代理程式和 IP 位址為主。您可以利用這些維度來了解行動裝置支援哪些功能。

## 將資料填入這些維度中

這些 Adobe 內部的維度參照查詢規則。

* 對於[!UICONTROL 行動電信業者]維度，Adobe 是與使用 NetAcuity 的 [Digital Element](https://www.digitalelement.com/) 合作維護 IP 位址和行動電信業者之間的查詢。
* 對於所有其他行動維度，Adobe 是與 [DeviceAtlas](https://deviceatlas.com/) 合作維護使用者代理程式與每個各別行動維度之間的查詢。

這些維度的適用性取決於實施類型：

* 對於 AppMeasurement 實施，這些維度可直接使用。
* 對於 Web SDK 的實施，在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)時可啟用[!UICONTROL 地理查詢] (適用於行動電信業者) 或[!UICONTROL 裝置查詢] (適用於所有其他維度)。

## 行動維度說明

>[!NOTE]
>
>標示為 `"None"` 的維度項目為非行動裝置。如果您要讓報表僅包含行動裝置，請將「行動裝置」維度拖曳至「工作區」畫布的區段區域中。

* **[!UICONTROL 行動音訊支援]**：決定裝置可播放的檔案格式。範例值包括 `"MP3"`、`"AAC"` 和 `"MIDI Monophonic"`。此維度中的值不互斥；單一點擊可歸因於多個維度項目。
* **[!UICONTROL 行動電信業者]**：裝置的手機或資料提供者。範例值包括 `"Reliance Jio"`、`"Airtel"`、`"Vodafone"` 和 `"Verizon"`。
* **[!UICONTROL 行動色彩深度]**：行動裝置的色彩深度 (以位元為單位)。
* **[!UICONTROL 行動 Cookie 支援]**：決定行動裝置是否支援 Cookie。此維度不會指出瀏覽器是否接受 Cookie。維度項目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **[!UICONTROL 行動裝置]**：訪客使用的行動裝置。
* **[!UICONTROL 行動裝置號碼]**：決定行動裝置是否傳輸其號碼。此維度不提供手機號碼本身。維度項目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **[!UICONTROL 行動裝置類型]**：行動裝置的類型。範例值包括 `"Mobile phone"`、`"Tablet"`、`"Media player"` 和 `"Gaming console"`。
* **[!UICONTROL 行動 DRM]**：行動裝置支援的 DRM 類型。範例值包括 `"DRM OMA forward"`、`"DRM OMA combined delivery"` 和 `"DRM OMA separate delivery"`。
* **[!UICONTROL 行動影像支援]**：行動裝置支援的影像類型。範例值包括 `"PNG"`、`"JPEG"` 和 `"GIF 87"`。此維度中的值不互斥；單一點擊可歸因於多個維度項目。
* **[!UICONTROL 行動資訊服務]**：裝置支援的新聞服務類型。新型裝置通常不會報告這類資訊。
* **[!UICONTROL Mobile Java VM]**：裝置支援的 Java 版本。
* **[!UICONTROL 行動郵件裝飾]**：判斷裝置是否支援 [Decomail](https://en.wikipedia.org/wiki/Decome)，這是一項在日文裝置上風行一時的功能。
* **[!UICONTROL 行動製造商]**：依製造商將行動裝置分類。範例值包括 `"Apple"`、`"Samsung"`、`"Huawei"` 和 `"Motorola"`。
* **[!UICONTROL 行動書籤的最大長度]**：行動裝置在已建立書籤的 URL 中支援的最大位元組數。新型裝置通常沒有限制。
* **[!UICONTROL 行動瀏覽器 URL 的最大長度]**：行動裝置在 URL 中支援的最大位元組數。新型裝置通常沒有限制。
* **[!UICONTROL 行動電子郵件的最大長度]**：行動裝置在電子郵件中支援的最大位元組數。新型裝置通常沒有限制。
* **[!UICONTROL 行動網路通訊協定]**：裝置在存取網際網路時支援的通訊協定類型。範例值包括 `"EDGE"`、`"GPRS"`、`"UMTS"` 和 `"LTE"`。
* **[!UICONTROL 行動作業系統 (已淘汰)]**：請改用[作業系統](operating-systems.md)維度。
* **[!UICONTROL 行動即按即說 (Push To Talk)]**：決定裝置是否支援 PTT (即按即說)，這可讓行動裝置的行為類似於雙向無線電。新型裝置通常不會報告這項功能。
* **[!UICONTROL 行動螢幕高度]**：螢幕的高度 (像素)。iPhone 因無法判斷 iPhone 裝置版本，而一律會報告 `"480"`。請參閱以下有關於確認 iPhone 裝置版本的小節。
* **[!UICONTROL 行動螢幕大小]**：行動裝置的完整尺寸 (像素)。報告的螢幕大小不指示裝置的方向。不論螢幕方向為何，報告中每個裝置的螢幕解析度都是固定的。這個大小是以決定較可能方向的研究為基礎。您可能會在相同的報表中看到 `"768x1024"` 和 `"1024x768"` 之類的大小，每個大小分別代表一或多個不同的裝置。
* **[!UICONTROL 行動螢幕寬度]**：螢幕的寬度 (像素)。
* **[!UICONTROL 行動視訊支援]**：行動裝置支援的視訊檔案格式和轉碼器。MP4 和 3GPP 檔案的不同轉碼器有數個維度項目。此維度中的值不互斥；單一點擊可歸因於多個維度項目。

## 依型號或版本區分 iPhone

行動裝置會在使用者代理程式字串中顯示其韌體版本，而非裝置版本。例如，目前這一代的 iPhone 包含與上一代 iPhone 若使用相同的韌體版本，則會有相同的使用者代理。由於無法使用 JavaScript 來判斷 iPhone 的裝置版本，所有 iPhone 都會屬於同一個貯體。行動維度必須以參考使用者代理的查閱為基礎，會造成所有 iPhone 都將行動螢幕大小顯示為 `320 x 480`。

如果您想要收集 iPhone 裝置版本，有兩種方式可以規避此限制。

* **使用行動 SDK**：行動 SDK 所包含的維度會公開供報告使用的裝置版本。相較於網站，此方法更適合用於行動應用程式。
* **使用其他可透過 JavaScript 使用的變數**：某些變數 (例如 `screen.height` 和 `screen.width`) 可用來推斷裝置版本。例如，您可在您的網站上使用下列程式碼片段：

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  此程式碼區塊會先偵測裝置是否為 iPhone。如果是，程式碼就會使用 JavaScript 將螢幕解析度提取至 eVar 中。如果螢幕解析度是獨特的解析度，此方法即可讓您大致偵測出裝置版本。
