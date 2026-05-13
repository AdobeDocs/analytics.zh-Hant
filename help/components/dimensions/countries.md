---
title: 國家/地區
description: 點擊的來源國家/地區。
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
TQID: https://experienceleague.adobe.com/qEG8tKa7eEuYV6XgYSlf4Y8FPaCiyWxPmdtL6KkKm94
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 65%

---

# 國家/地區

「國家/地區」[維度](overview.md)會報告點選源自於哪個國家/地區。 此維度有助於判斷訪客在造訪您的網站時最常來自哪些國家/地區。 您可以利用這些資料加強對這些國家/地區的行銷工作，或確保您在使用不同主要語言的國家/地區可提供最佳網站體驗。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。 查閱值以隨著點擊傳送的 IP 位址為基礎。 Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，共同維護 IP 位址與國家/區域之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 地理查閱]。

## 維度項目

維度項目包含全球各個國家/地區。 範例值包括 `"United States"`、`"United Kingdom"` 或 `"India"`。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。 有些電信業者會透過集中化或區域性網路節點取回IP流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
* **因隱私權原因而遮蔽IP位址的代理程式**：Apple的私人轉送之類的服務會透過中介或Proxy隨機傳送資料，以隱藏真正的IP位址。 接著，此Proxy會先取代其他IP位址，再轉送至Adobe。
