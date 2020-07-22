---
title: 行動裝置尺寸
description: 根據裝置的使用者代理字串的維度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 4%

---


# 行動裝置尺寸

*本頁面參照存取您網站之行動裝置的屬性。 如果您想要追蹤行動應用程式上的裝置，請參閱「實[作使用指南」中的](/help/implement/mobile-device-sdk.md)「實作行動裝置分析」。*

行動維度可提供瀏覽您網站之行動裝置屬性的相關分析。 您可以使用這些維度來協助瞭解行動裝置支援哪些功能。

## 將資料填入這些維度

這些維度會參考Adobe內部的查閱規則。 查閱值以隨點擊傳送 `User-Agent` 的HTTP標題為基礎。 Adobe與 [DeviceAtlas合作](https://deviceatlas.com/) ，以維護使用者代理與行動維度之間的查詢。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），所有行動裝置尺寸都可立即使用。

## 行動維度說明

>[!NOTE]
>
>標示為非 `"None"` 行動裝置的維度項目。 如果您想要只包含行動裝置的報表，請將「行動裝置」維度拖曳至「工作區畫布」的區段區域。

* **行動音訊支援**: 決定裝置可播放的檔案格式。 範例值 `"MP3"`包括、 `"AAC"`和 `"MIDI Monophonic"`。 此維中的值不是互斥的； 單一點擊可歸因於多個維度項目。
* **行動電信業者**: 如果使用者代理包含電信業者專用的裝置，則電信業者是維度項目。 範例值 `"Reliance Jio"`包括 `"Airtel"`、 `"Vodafone"`和 `"Verizon"`。
* **行動裝置色彩深度**: 行動裝置的色深（以位元為單位）。
* **行動Cookie支援**: 判斷行動裝置是否支援Cookie。 若瀏覽器接受Cookie，則此報告不會狀態。 維度項目 `"Supported"`包括、 `"Not supported"`和 `"Unknown"`。
* **行動裝置**: 訪客使用的行動裝置。
* **行動裝置號碼**: 確定移動設備是否發送其號碼。 維度項目 `"Supported"`包括、 `"Not supported"`和 `"Unknown"`。
* **行動裝置類型**: 行動裝置的類型。 範例值 `"Mobile phone"`包括 `"Tablet"`、 `"Media player"`和 `"Gaming console"`。
* **行動DRM**: 行動裝置支援的DRM類型。 範例值 `"DRM OMA forward"`包括、 `"DRM OMA combined delivery"`和 `"DRM OMA separate delivery"`。
* **行動影像支援**: 行動裝置支援的影像類型。 範例值 `"PNG"`包括、 `"JPEG"`和 `"GIF 87"`。 此維中的值不是互斥的； 單一點擊可歸因於多個維度項目。
* **行動資訊服務**: 裝置支援的新聞服務類型。 最近使用的裝置通常不會報告此資訊。
* **Mobile Java VM**: 裝置支援的Java版本。
* **行動郵件裝飾**: 判斷裝置是否支援日文裝置常用的反編譯功能。
* **行動製造商**: 依製造商將行動裝置分組。 範例值 `"Apple"`包括 `"Samsung"`、 `"Huawei"`和 `"Motorola"`。
* **行動書籤最大長度**: 行動裝置在書籤化URL中支援的最大位元組數。 最新裝置通常沒有限制。
* **行動瀏覽器URL最大長度**: 行動裝置在URL中支援的最大位元組數。 最新裝置通常沒有限制。
* **行動電子郵件最長長度**: 行動裝置在電子郵件中支援的最大位元組數。 最新裝置通常沒有限制。
* **行動網路通訊協定**: 訪問Internet時設備支援的協定類型。 範例值 `"EDGE"`包括 `"GPRS"`、 `"UMTS"`和 `"LTE"`。
* **行動作業系統（已淘汰）**: 請改用 [作業系統](operating-systems.md) 維度。
* **行動即按即說**: 判斷裝置是否支援PTT（即按即說），這可讓行動裝置的行為類似雙向無線電。 最近使用的裝置通常不會報告此功能。
* **行動螢幕高度**: 螢幕高度（以像素為單位）。 請注意，iPhone會因無 `"480"` 法判斷iPhone裝置版本而一律報告。 請參閱以下有關決定iPhone裝置版本的章節。
* **行動螢幕大小**: 行動裝置的完整尺寸（以像素為單位）。 報告的螢幕大小不指示裝置的方向。不論螢幕方向為何，報告中每個裝置的螢幕解析度都是固定的。這個大小是以決定較可能方向的研究為基礎。You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **行動螢幕寬度**: 螢幕寬度（以像素為單位）。
* **行動視訊支援**: 行動裝置支援的視訊檔案格式和轉碼器。 MP4和3GPP檔案的不同轉碼器中，存在數個維度項目。 此維中的值不是互斥的； 單一點擊可歸因於多個維度項目。

## 依型號或版本分隔iPhone

行動裝置會在使用者代理字串中報告其韌體版本，而非裝置版本。 例如，目前的iPhone包含與上一代iPhone相同的使用者代理（如果使用相同的韌體版本）。 由於無法使用JavaScript來判斷iPhone的裝置版本，所有iPhone都屬於同一個貯體。 行動維度嚴格以參考使用者代理的查閱為基礎，因此您會發現所有iPhone都會報告行動螢幕大小 `320 x 480`。

如果您想要收集iPhone裝置版本，有兩種方式可以規避此限制。

* **使用iOS SDK**: 行動SDK包含可公開裝置版本以供報告使用的維度。 相較於網站，此方法更適合行動應用程式。
* **使用其他可透過JavaScript使用的變數**: 某些變數(例如 `screen.height` 和 `screen.width`)可用來推斷裝置版本。 例如，您可在網站上使用下列程式碼片段：

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   此程式碼區塊會先偵測裝置是否為iPhone。 如果是，程式碼會使用JavaScript將螢幕解析度提取至eVar。 如果螢幕解析度是唯一的，此方法可讓您大致偵測裝置版本。
