---
title: 行動維度
description: 根據裝置 IP 位址的維度
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '892'
ht-degree: 100%

---

# 行動維度

*此頁面會參考對您的網站進行存取之行動裝置的屬性。如果您想要在行動應用程式上追蹤裝置，請參閱「實施作業」使用指南中的[對行動裝置實施作業 Analytics](/help/implement/mobile-device-sdk.md)。*

行動維度可讓您深入分析造訪網站之行動裝置的屬性。您可以利用這些維度來瞭解行動裝置支援哪些功能。

## 將資料填入這些維度中

這些維度會參考 Adobe 內部的查詢規則。[!UICONTROL 行動電信業者] 查詢是以 IP 位址來確定，並使用我們從 NetAcuity (一種數位元素產品) 取得的資料。
如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，所有行動維度將可立即運作。

## 行動維度說明

>[!NOTE]
>
>標示為 `"None"` 的維度項目為非行動裝置。如果您要讓報表僅包含行動裝置，請將「行動裝置」維度拖曳至「工作區」畫布的區段區域中。

* **行動音訊支援**：決定裝置可播放的檔案格式。範例值包括 `"MP3"`、`"AAC"` 和 `"MIDI Monophonic"`。此維度中的值不互斥；單一點擊可歸因於多個維度項目。
* **行動電信業者**：此維度值是透過根據 Analytics 擷取的 IP 位址查詢協力廠商 (數位元素) 資料來填入。範例值包括 `"Reliance Jio"`、`"Airtel"`、`"Vodafone"` 和 `"Verizon"`。
* **行動色彩深度**：行動裝置的色彩深度 (以位元為單位)。
* **行動 Cookie 支援**：決定行動裝置是否支援 Cookie。此報表不會指出瀏覽器是否接受 Cookie。維度項目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **行動裝置**：訪客使用的行動裝置。
* **行動裝置號碼**：決定行動裝置是否傳輸其號碼。維度項目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **行動裝置類型**：行動裝置的類型。範例值包括 `"Mobile phone"`、`"Tablet"`、`"Media player"` 和 `"Gaming console"`。
* **行動 DRM**：行動裝置支援的 DRM 類型。範例值包括 `"DRM OMA forward"`、`"DRM OMA combined delivery"` 和 `"DRM OMA separate delivery"`。
* **行動影像支援**：行動裝置支援的影像類型。範例值包括 `"PNG"`、`"JPEG"` 和 `"GIF 87"`。此維度中的值不互斥；單一點擊可歸因於多個維度項目。
* **行動資訊服務**：裝置支援的新聞服務類型。新型裝置通常不會報告這類資訊。
* **Mobile Java VM**：裝置支援的 Java 版本。
* **行動郵件裝飾**：判斷裝置是否支援 Decomail，這是一項在日文裝置上風行一時的功能。
* **行動製造商**：依製造商將行動裝置分組。範例值包括 `"Apple"`、`"Samsung"`、`"Huawei"` 和 `"Motorola"`。
* **行動書籤的最大長度**：行動裝置在已建立書籤的 URL 中支援的最大位元組數。新型裝置通常沒有限制。
* **行動瀏覽器 URL 的最大長度**：行動裝置在 URL 中支援的最大位元組數。新型裝置通常沒有限制。
* **行動電子郵件的最大長度**：行動裝置在電子郵件中支援的最大位元組數。新型裝置通常沒有限制。
* **行動網路通訊協定**：裝置在存取網際網路時支援的通訊協定類型。範例值包括 `"EDGE"`、`"GPRS"`、`"UMTS"` 和 `"LTE"`。
* **行動作業系統 (已淘汰)**：請改用[作業系統](operating-systems.md)維度。
* **行動即按即說 (Push To Talk)**：決定裝置是否支援 PTT (即按即說)，這可讓行動裝置的行為類似於雙向無線電。新型裝置通常不會報告這項功能。
* **行動螢幕高度**：螢幕的高度 (像素)。請注意，iPhone 因無法判斷 iPhone 裝置版本，而一律會報告 `"480"`。請參閱以下有關於確認 iPhone 裝置版本的小節。
* **行動螢幕大小**：行動裝置的完整尺寸 (像素)。報告的螢幕大小不指示裝置的方向。不論螢幕方向為何，報告中每個裝置的螢幕解析度都是固定的。這個大小是以決定較可能方向的研究為基礎。您可能會在相同的報表中看到 `"768x1024"` 和 `"1024x768"` 之類的大小，每個大小分別代表一或多個不同的裝置。
* **行動螢幕寬度**：螢幕的寬度 (像素)。
* **行動視訊支援**：行動裝置支援的視訊檔案格式和轉碼器。MP4 和 3GPP 檔案的不同轉碼器有數個維度項目。此維度中的值不互斥；單一點擊可歸因於多個維度項目。

## 依型號或版本區分 iPhone

行動裝置會在使用者代理程式字串中顯示其韌體版本，而非裝置版本。例如，目前這一代的 iPhone 包含與上一代 iPhone 若使用相同的韌體版本，則會有相同的使用者代理。由於無法使用 JavaScript 來判斷 iPhone 的裝置版本，所有 iPhone 都會屬於同一個貯體。行動維度必須以參考使用者代理的查閱為基礎，因此您會發現所有 iPhone 都將行動螢幕大小報告為 `320 x 480`。

如果您想要收集 iPhone 裝置版本，有兩種方式可以規避此限制。

* **使用 iOS SDK**：行動 SDK 所包含的維度會公開供報告使用的裝置版本。相較於網站，此方法更適合用於行動應用程式。
* **使用其他可透過 JavaScript 使用的變數**：某些變數 (例如 `screen.height` 和 `screen.width`) 可用來推斷裝置版本。例如，您可在您的網站上使用下列程式碼片段：

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   此程式碼區塊會先偵測裝置是否為 iPhone。如果是，程式碼就會使用 JavaScript 將螢幕解析度提取至 eVar 中。如果螢幕解析度是獨特的，此方法即可讓您大致偵測出裝置版本。
