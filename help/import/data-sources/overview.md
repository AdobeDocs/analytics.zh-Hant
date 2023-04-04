---
title: 資料來源概觀
description: 使用外部檔案將資料匯入Adobe Analytics。
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 資料來源概觀

Adobe Analytics資料來源可讓您匯入其他線上或離線資料以用於報表。 它們有助於了解您網站外業務的各個層面，以及它們與您網站的互動方式。 使用資料來源的一般工作流程包含下列步驟：

1. 貴組織會從其他來源收集資料。 範例包括點按前資料、客服中心資料，或網站外發生的交易相關資訊。
1. 資料的格式化方式，讓Adobe Analytics能透過以定位點分隔的文字檔了解。
1. 將文字檔案上傳至FTP站台Adobe提供，以及隨附的 `.fin` 檔案。
1. Adobe內嵌文字檔案，並連同您網站上收集的維度和量度一起顯示該資料。

Adobe提供的資料來源有兩種一般類型。 所有資料源模板都基於以下兩種類型之一：

* **摘要資料來源**:提供在Adobe Analytics中匯入高階資料的簡單方式。 您可以指定時間戳記、變數值和相關量度。 接著，每個維度項目的這些量度會隨之增加。 如果您想要並排檢視離線和線上資料，此功能就十分實用。 不過，它不會將線上和離線資料連結在一起。
* **交易ID資料來源**:如果AppMeasurement傳送的點擊和資料來源列包含相符的交易ID，資料來源中的維度和量度值會附加至該點擊。

**完全處理資料來源** 自2021年3月25日起，不再以資料來源類型形式提供。 請參閱 [終止公告](full-processing-eol.md) 以取得更多資訊。

Adobe也提供 [資料來源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，可讓您不使用產品UI或FTP位置，即可建立資料來源及上傳資料。

## 後續步驟

[資料來源快速入門](getting-started.md):上傳簡單資料來源至開發報表套裝。
