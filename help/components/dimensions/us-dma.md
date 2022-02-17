---
title: US DMA
description: 點擊的指定市場區域。
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# 美國DMA

「美國 DMA」維度會報告訪客的指定市場區域 (DMA)。此維度以 [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/) 彙編的媒體市場為基礎。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱規則。查閱值以隨著點擊傳送的 IP 位址為基礎。Adobe 與 Nielsen 合作，共同維護 IP 位址與 DMA 之間的查閱。此維度可直接用於所有實作。

## 維度項目

維度項目包含訪客的 DMA 和 DMA 代碼。3 位數的代碼並非郵遞區號，而是 Nielsen 彙編的 DMA 代碼。範例值包括 `"Dallas-Ft. Worth (623)"`、`"New York (501)"` 或 `"Los Angeles (803)"`。維度項目 `"No Metro (0)"` 包含美國以外的所有國際流量。

## 報告的位置與實際位置之間的差異

由於此維度以 IP 位址為基礎，因此在某些情況下，報告的位置與實際位置之間可能會出現差異：

* **代表公司 Proxy 的 IP 位址**：這些訪客可能會顯示為來自使用者公司網路的流量，但若使用者正在遠端工作，則可能是不同的位置。
* **行動 IP 位址**：行動 IP 定位會根據位置與網路而在不同層級運作。許多電信業者會透過集中化或區域性網路節點取回 IP 流量。
* **衛星 ISP 使用者**：要識別這些使用者的特定位置並不容易，因為他們通常看似源自於上行位置。
* **軍事和政府 IP**：此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非其目前駐在基地或辦公室) 進入的工作人員。
