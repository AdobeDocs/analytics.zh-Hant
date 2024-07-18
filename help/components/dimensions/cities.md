---
title: 城市
description: 點擊的來源城市。
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 73%

---

# 城市

「城市」[維度](overview.md)會報告點選源自於哪個城市。 此維度有助於判斷訪客在造訪您的網站時最常來自哪些城市。您可以利用這些資料加強這些城市的當地廣告，例如廣告看板或商業廣告。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。查閱值以隨著點擊傳送的 IP 位址為基礎。與[Digital Element](https://www.digitalelement.com/)Adobe，以維護IP位址與城市之間的查閱。

* 對於AppMeasurement實作，此維度可立即運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 地理查閱]。

## 維度項目

維度項目包含全球各個城市。範例值包括 `"New York (New York, United States)"`、`"Bangalore (Karnataka, India)"` 或 `"London (London, United Kingdom)"`。

某些維度項目可能包括 `"AOL"` (撥號網際網路服務提供者)。此服務的訂閱者會根據其帳號建立時所在的國家/區域，獲得一個指定的存取點。AOL 使用者可使用此存取點的 IP 位址。由於此維度是以 IP 位址為根據，因此系統會使用存取點的地理位置，而非訪客的實際位置。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。有些電信業者會透過集中化或區域性網路節點取回IP流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
* **因隱私權原因而遮蔽IP位址的代理程式**：Apple的私人轉送之類的服務會透過中介或Proxy隨機傳送資料，以隱藏真正的IP位址。 然後，此Proxy會取代其他IP位址，再轉送至Adobe。
