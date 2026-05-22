---
title: 美國各州
description: 訪客所在的美國州別。
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
TQID: https://experienceleague.adobe.com/YLZIz1-J-LVvases2X1AgNxQR1eTtqoeDoxFVCg2MV4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 77%

---

# 美國各州

「美國各州」[維度](overview.md)會報告美國的訪客所在州。 此維度與[地區](regions.md)維度相仿，差別在於此維度是美國特有維度。 如果您想要有比[國家/地區](countries.md)更精細、但比[城市](cities.md)粗略的洞察，使用此維度將有所幫助。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。 查閱值以隨著點擊傳送的 IP 位址為基礎。 Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，共同維護 IP 位址與國家/區域之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)時啟用[!UICONTROL 地理查閱]。

## 維度項目

維度項目包含區域和區域所在的國家/區域。 範例值包括 `"California"`、`"Texas"` 或 `"Virginia"`。 維度項目 `"Unspecified"` 包含美國以外的所有國際流量。

此維度可能包括 `"AOL"` 撥接網際網路服務供應商。 此服務的訂閱者會獲得存取點。 AOL 使用者可使用此存取點的 IP 位址。 由於此維度是以 IP 位址為根據，因此系統會使用存取點的地理位置，而非訪客的實際位置。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。 有些電信業者會透過集中化或區域性網路節點取回IP流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
* **因隱私權原因而遮蔽IP位址的代理程式**：Apple的私人轉送之類的服務會透過中介或Proxy隨機傳送資料，以隱藏真正的IP位址。 接著，此Proxy會先取代其他IP位址，再轉送至Adobe。
