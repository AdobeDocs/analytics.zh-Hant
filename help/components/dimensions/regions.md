---
title: 地區
description: 訪客的地理區域。
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
TQID: https://experienceleague.adobe.com/Yjy-VGZ0alwfMR408QClnOEIB2z-rfgH5XCn9K0bE1A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 87%

---

# 地區

「區域」[維度](overview.md)會報告訪客的地理區域。 這是小於國家/區域、大於城市的地理區域。 在某些國家，區域是指一個州、省或府/州。 在其他地方，則是指構成國、行政區或大都會區域。 如果您想要有比[國家/地區](countries.md)更精細、但比[城市](cities.md)粗略的洞察，使用此維度將有所幫助。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。 查閱值以隨著點擊傳送的 IP 位址為基礎。 Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，共同維護 IP 位址與國家/區域之間的查閱。 此維度可直接用於所有實施作業。

## 維度項目

維度項目包含區域和區域所在的國家/區域。 範例值包括 `"California (United States)"`、`"Tokyo (Japan)"` 或 `"Sao Paulo (Brazil)"`。

某些維度項目可能包括 `"AOL"` (撥號網際網路服務提供者)。 此服務的訂閱者會根據其帳號建立時所在的國家/區域，獲得一個指定的存取點。 AOL 使用者可使用此存取點的 IP 位址。 由於此維度是以 IP 位址為根據，因此系統會使用存取點的地理位置，而非訪客的實際位置。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。 許多電信業者會透過集中化或區域性網路節點取回 IP 流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
* **因隱私權原因而遮蔽IP位址的代理程式**：Apple的私人轉送之類的服務會透過中介或Proxy隨機傳送資料，以隱藏真正的IP位址。 接著，此Proxy會先取代其他IP位址，再轉送至Adobe。
