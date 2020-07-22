---
title: US DMA
description: 點擊的指定市場區域。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---


# US DMA

「美國DMA」維度會報告訪客的指定市場區域(DMA)。 它以尼爾森匯編的媒體市場 [為基礎](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/)。

## 將資料填入此維度

此維度會參照Adobe內部的查閱規則。 查閱值以點擊所傳送的IP位址為基礎。 Adobe與Nielsen合作，維護IP位址與DMA之間的查詢。 此維度適用於所有實作，不需開箱即用。

>[!TIP]
>
>如果貴組織遵守嚴格的隱私 [權法規](/help/admin/admin/general-acct-settings-admin.md) ，但模糊化IP位址不夠，則您可要求完全停用地理位置資料。 請連絡客戶服務以取得報表套裝ID，並要求關閉報表套裝的「地理位置」。

## 維度項目

維度項目包括訪客的DMA和DMA代碼。 3位數的代碼不是郵遞區號，而是Nielsen的DMA代碼。 範例值 `"Dallas-Ft. Worth (623)"`包括 `"New York (501)"`、或 `"Los Angeles (803)"`。 維度項目 `"No Metro (0)"` 包含美國境外的所有國際流量。

## 報告位置與實際位置之間的差異

由於此維度是以IP位址為基礎，因此某些情況可顯示報告位置與實際位置的差異：

* **代表公司Proxy的IP位址**: 這些訪客可顯示為透過使用者公司網路的流量，如果使用者正在遠端工作，則可能是不同的位置。
* **行動IP位址**: 行動IP定位的運作層級視位置和網路而定。 許多電信業者會透過集中或地區存在點回傳IP流量。
* **衛星ISP用戶**: 識別這些使用者的特定位置很困難，因為他們通常似乎源自上行鏈路位置。
* **軍事和政府IP**: 代表在全球各地旅行並透過其家鄉（而非目前駐在的基地或辦公室）進入的人員。
