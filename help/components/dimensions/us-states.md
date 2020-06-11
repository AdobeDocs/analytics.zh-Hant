---
title: 美國各州
description: 訪客的美國州。
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# 美國州

「美國州」維度會報告美國訪客的狀態。 它與「區域」 [維類似](regions.md) ，只不過此維度是美國特有的。 如果您想要比「國家」更精細，但比「城市」更細緻的洞察力，使用這個維度就很有 [用](countries.md) ，但不像「城市」 [那麼細緻](cities.md)。

## 將資料填入此維度

此維度會參照Adobe內部的查閱規則。 查閱值以點擊所傳送的IP位址為基礎。 Adobe與 [Digital Element合作](https://www.digitalelement.com/) ，以維護IP位址與國家／地區間的查詢。 此維度適用於所有實作，不需開箱即用。

> [!TIP] 如果貴組織遵守嚴格的隱私 [權法規](/help/admin/admin/general-acct-settings-admin.md) ，但模糊化IP位址不夠，則您可要求完全停用地理位置資料。 請連絡客戶服務以取得報表套裝ID，並要求關閉報表套裝的「地理位置」。

## 維度值

維值包括區域和區域所在的國家。 範例值 `"California"`包括 `"Texas"`、或 `"Virginia"`。 維度值包 `"Unspecified"` 含美國以外的所有國際流量。

## 報告位置與實際位置之間的差異

由於此維度是以IP位址為基礎，因此某些情況可顯示報告位置與實際位置的差異：

* **代表公司Proxy的IP位址**: 這些訪客可顯示為透過使用者公司網路的流量，如果使用者正在遠端工作，則可能是不同的位置。
* **行動IP位址**: 行動IP定位的運作層級視位置和網路而定。 許多電信業者會透過集中或地區存在點回傳IP流量。
* **衛星ISP用戶**: 識別這些使用者的特定位置很困難，因為他們通常似乎源自上行鏈路位置。
* **軍事和政府IP**: 代表在全球各地旅行並透過其家鄉（而非目前駐在的基地或辦公室）進入的人員。
