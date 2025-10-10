---
title: 國家/地區
description: 點擊的來源國家/地區。
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 60%

---

# 國家/地區

「國家/地區」[維度](overview.md)會報告點選源自於哪個國家/地區。 此維度有助於判斷訪客在造訪您的網站時最常來自哪些國家/地區。您可以利用這些資料加強對這些國家/地區的行銷工作，或確保您在使用不同主要語言的國家/地區可提供最佳網站體驗。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。查閱值以隨著點擊傳送的 IP 位址為基礎。Adobe與[Digital Element](https://www.digitalelement.com/)合作，共同維護IP位址與國家/地區之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[!UICONTROL 設定資料流]時啟用[地理查閱](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)。

## 維度項目

維度項目包含全球各個國家/地區。範例值包括 `"United States"`、`"United Kingdom"` 或 `"India"`。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。有些電信業者會透過集中化或區域性網路節點取回IP流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
* **因隱私權原因而遮蔽IP位址的代理程式**：Apple的私人轉送之類的服務會透過中介或Proxy隨機傳送資料，以隱藏真正的IP位址。 接著，此Proxy會先取代其他IP位址，再轉送至Adobe。
