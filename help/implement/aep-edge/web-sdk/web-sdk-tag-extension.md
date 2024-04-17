---
title: 使用Web SDK標籤擴充功能將資料傳送至Adobe Analytics
description: 從簡潔的Adobe Experience Platform資料收集實作開始，以便使用XDM和Adobe Analytics ExperienceEvent欄位群組將資料傳送至Adobe Analytics。
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# 使用Web SDK標籤擴充功能將資料傳送至Adobe Analytics

此實作路徑牽涉到使用Adobe Experience Platform Data Collection中的標籤的全新Web SDK安裝。 其他實作路徑會在不同頁面上說明：

* [Web SDK JavaScript程式庫](web-sdk-javascript-library.md)：全新Web SDK安裝，使用Web SDK JavaScript程式庫(`alloy.js`)。 類似Web SDK標籤擴充方法（本頁），但您會自行管理實作，而不使用標籤UI。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。
* [Analytics擴充功能新增至Web SDK擴充功能](analytics-extension-to-web-sdk.md)：以順暢且系統的方式從Adobe Analytics標籤擴充功能移至Web SDK標籤擴充功能。 在您的組織準備好使用Adobe Experience Platform服務(例如Customer Journey Analytics)之前，此方法會抑制使用XDM的需求。 使用 `data` 物件而非 `xdm` 物件以傳送資料給Adobe。
* [AppMeasurement至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md)：順暢且系統地移轉至Web SDK，但不會使用標籤。 而是要手動移除Adobe Analytics資料彙集程式庫(`AppMeasurement.js`)並將其取代為Web SDK JavaScript程式庫(`alloy.js`)。

## 此實作路徑的優缺點

使用Web SDK擴充功能傳送資料給Adobe Analytics有利也有弊。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**最直接的方法**：此實施路徑最直接，通常是新Web SDK實施的建議路徑。 如果您不需擔心目前的Adobe Analytics實作，請填入適用的Web SDK XDM欄位。</li><li>**預先定義的結構描述**：如果您的組織不需要自己的結構描述，您只需使用針對Adobe Analytics的結構描述即可。 即使您邁向Customer Journey Analytics，此概念仍適用；prop和eVar的概念不適用於Customer Journey Analytics，但您可以繼續使用prop和eVar作為簡單的自訂維度。</li><li>**無需開發人員干預即可管理標籤**：標籤可讓您管理實作，而不需要開發人員對您的實作進行程式碼變更。 您的開發人員會安裝標籤載入器指令碼，而您可以完全控制資料的收集方式。</li></ul> | <ul><li>**使用特定結構描述鎖定到**：當您的組織移至Customer Journey Analytics時，您必須選擇繼續使用Adobe Analytics結構描述，或移轉至您自己的組織結構描述（這將是獨立的資料集）。 如果您的組織想要在移至Customer Journey Analytics時同時避免Adobe Analytics結構描述和移轉至個別的資料集，Adobe建議使用下列兩種方法之一：<ul><li>使用 `data` 物件： `data` 物件可讓您在不符合XDM結構描述的情況下將資料傳送至Adobe Analytics。 建立組織的結構描述後，您就可以使用資料流對應來對應 `data` 物件欄位新增至XDM。 兩者 [Analytics擴充功能新增至Web SDK擴充功能](analytics-extension-to-web-sdk.md) 和 [AppMeasurement至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md) 使用此 `data` 物件。</li><li>完全略過Adobe Analytics：如果您正在實作Web SDK，可以將該資料傳送到Adobe Experience Platform中的資料集，以用於Customer Journey Analytics。 您可以使用任何您喜歡的結構描述；Adobe Analytics完全不參與此工作流程，因此不需要Adobe Analytics ExperienceEvent欄位群組。 此方法產生最少的技術債，但也會將Adobe Analytics完全排除在外。</li></ul></ul> |


