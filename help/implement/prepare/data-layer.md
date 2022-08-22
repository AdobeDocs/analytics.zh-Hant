---
title: 建立資料層
description: 瞭解 Analytics 實施中的資料層是什麼，以及如何用來對映 Adobe Analytics 中的變數。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 76c36a136359290e341febc554773a71b1cc7c66
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 63%

---

# 建立資料層

資料層是站點上JavaScript對象的框架，其中包含Analytics實現中使用的變數值。 它允許在將值分配給Analytics變數時進行更好的控制和更輕鬆的維護。

## 先決條件

[建立解決方案設計文件](solution-design.md) - 貴組織必須符合追蹤要求。確保在前往找組織內的開發團隊之前，先使用解決方案設計文件做好準備。

## 工作流程

使用資料層實施 Adobe Analytics 時，通常會依照下列步驟操作：

1. **與您的網站開發團隊合作實施資料層**：您的網站開發團隊主要負責確保資料層物件填入正確的值。請與您的網站開發團隊一起檢閱此頁面，確保團隊之間的期望相同。

   >[!NOTE]
   >
   > 可選擇遵循 Adobe 建議的資料層規格。如果您已有資料層，或選擇不遵循 Adobe 的規格，請確定貴組織對於需遵循的規格有共識。
1. **使用瀏覽器主控台驗證資料層**：建立資料層後，可以使用任何瀏覽器的開發人員主控台來驗證資料層是否正常運作。您可以使用 `F12` 鍵，在大部分的瀏覽器中開啟開發人員主控台。範例變數值應為 `adobeDataLayer.page.title`。
1. **使用Adobe Experience Platform資料收集將資料層對象映射到資料元**:此步驟因組織的實施方法而異：
   * **如果使用Web SDK**:將所需資料層對象映射到Adobe Experience Platform邊緣中所需的XDM欄位。 請參閱 [分析變數映射](../aep-edge/variable-mapping.md) 確定所需的資料層映射。
   * **如果使用分析擴展**:在「Adobe Experience Platform資料收集中的標籤」下建立資料元素，並將它們分配給所需的資料層對象。 然後，在分析擴展中，將每個資料元素分配給相應的分析變數。

## 規格

Adobe建議使用 [Adobe客戶端資料層](https://github.com/adobe/adobe-client-data-layer/wiki) 用於新的或重組的實施。

您的組織可以自由使用其他資料層規範，如 [客戶體驗數字資料層](https://www.w3.org/2013/12/ceddl-201312.pdf)，或完全另一個自定義資料層。 與滿足您組織需求的一致資料層保持一致是最重要的。



使用[客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf)報表，取得每個物件和子物件的詳細資訊。並非所有網站都使用全部物件，例如，如果您托管一個新聞網站，您就不可能使用 `digitalData.product` 物件陣列。

資料層可擴展；如果貴組織有特定的需求，您可以在資料層中加入物件以符合這些需求。

## 設定資料層值

資料層通常會產生伺服器端，並參考用來建立網站內容的相同物件。根據貴組織[解決方案設計文件](solution-design.md)中設定的追蹤要求，建立網站的資料層。

## 後續步驟

[將資料層物件對應至資料元素](../launch/layer-to-elements.md)：在 Adobe Experience Platform 中使用您網站的資料層。
