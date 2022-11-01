---
title: 建立資料層
description: 瞭解 Analytics 實施中的資料層是什麼，以及如何用來對映 Adobe Analytics 中的變數。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 571192e27972f2bc15912481f9a578427e1c1cfb
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 60%

---

# 建立資料層

資料層是網站上JavaScript物件的架構，包含Analytics實作中使用的變數值。 為Analytics變數指派值時，可提供更優異的控制力及更輕鬆的維護。

## 先決條件

[建立解決方案設計文件](solution-design.md) - 貴組織必須符合追蹤要求。確保在前往找組織內的開發團隊之前，先使用解決方案設計文件做好準備。

## 工作流程

使用資料層實施 Adobe Analytics 時，通常會依照下列步驟操作：

1. **與您的網站開發團隊合作實施資料層**：您的網站開發團隊主要負責確保資料層物件填入正確的值。請與您的網站開發團隊一起檢閱此頁面，確保團隊之間的期望相同。

   >[!NOTE]
   >
   > 可選擇遵循 Adobe 建議的資料層規格。如果您已有資料層，或選擇不遵循 Adobe 的規格，請確定貴組織對於需遵循的規格有共識。

1. **使用瀏覽器主控台驗證資料層**：建立資料層後，可以使用任何瀏覽器的開發人員主控台來驗證資料層是否正常運作。您可以使用 `F12` 鍵，在大部分的瀏覽器中開啟開發人員主控台。範例變數值應為 `adobeDataLayer.page.title`。
1. **使用Adobe Experience Platform資料收集將資料層物件對應至資料元素**:此步驟會依貴組織的實作方法而異：
   * **若使用Web SDK**:將所需的資料層物件對應至Adobe Experience Platform Edge中所需的XDM欄位。 請參閱 [Analytics變數對應](../aep-edge/variable-mapping.md) 以決定所需的資料層對應。
   * **如果使用Analytics擴充功能**:在Adobe Experience Platform資料收集的「標籤」下建立資料元素，並將其指派給所需的資料層物件。 然後在Analytics擴充功能中，將每個資料元素指派給適當的Analytics變數。

## 規格

Adobe建議使用 [Adobe用戶端資料層](https://github.com/adobe/adobe-client-data-layer/wiki) 適用於新實作或重組實作。

貴組織可使用其他資料層規格，例如 [客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf)，或完全的其他自定義規範。 最重要的是，要與符合貴組織需求的一致資料層保持一致。

資料層可擴展；如果貴組織有特定的需求，您可以在資料層中加入物件以符合這些需求。

## 設定資料層值

資料層通常會產生伺服器端，並參考用來建立網站內容的相同物件。根據貴組織[解決方案設計文件](solution-design.md)中設定的追蹤要求，建立網站的資料層。

## 後續步驟

[將資料層物件對應至資料元素](../launch/layer-to-elements.md)：在 Adobe Experience Platform 中使用您網站的資料層。
