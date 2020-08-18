---
title: 美國各州
description: 訪客所在的美國州別。
translation-type: tm+mt
source-git-commit: fdc77997c8aea07cc7db1d06c5c0c2cd2f2abbd9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 79%

---


# 美國各州

「美國各州」維度會報告美國的訪客所在的州別。此維度與[地區](regions.md)維度相仿，差別在於此維度是美國特有維度。如果您想要有比[國家/地區](countries.md)更精細、但比[城市](cities.md)粗略的深入分析，使用此維度將有所幫助。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。查閱值以隨著點擊傳送的 IP 位址為基礎。Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，共同維護 IP 位址與國家/地區之間的查閱。此維度可直接用於所有實作。

>[!TIP]
>
>如果您的組織遵循嚴格的隱私權法規，但[模糊化 IP 位址](/help/admin/admin/general-acct-settings-admin.md)不夠嚴謹，您可以要求完全停用地理位置資料。請聯絡客戶服務以取得報表套裝 ID，並要求關閉報表套裝的「地理位置」。

## 維度項目

維項包括區域和區域所在的國家。 範例值包括 `"California"`、`"Texas"` 或 `"Virginia"`。The dimension item `"Unspecified"` includes all international traffic outside of the United States.

此維度可以包 `"AOL"`括撥號網際網路服務提供商。 此服務的訂閱者會獲派一個存取點。 AOL使用者使用此存取點的IP位址。 由於此維度是以IP位址為基礎，因此會使用存取點的地理位置，而非訪客的實際位置。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。許多電信業者會透過集中化或地區性網路節點取回 IP 流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
