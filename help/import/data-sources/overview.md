---
title: 資料來源概觀
description: 使用外部檔案將資料匯入Adobe Analytics。
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 資料來源概觀

Adobe Analytics資料來源可讓您匯入其他線上或離線資料以用於報表。 它們十分有助於瞭解網站外部業務的各個層面，以及它們如何與您的網站互動。 使用資料來源的一般工作流程包含下列步驟：

1. 您的組織會從其他來源收集資料。 範例包括點按前資料、客服中心資料，或發生在網站外部的交易資訊。
1. 使用Tab字元分隔文字檔案，以Adobe Analytics瞭解的方式將資料格式化。
1. 您可以將文字檔案上傳至FTP站台Adobe提供的FTP站台，以及隨附的 `.fin` 檔案。
1. Adobe會擷取文字檔，並將該資料與網站上收集的維度和量度一起顯示。

Adobe選件的資料來源有兩種一般型別。 所有資料來源範本皆以下列兩種型別之一為基礎：

* **摘要資料來源**：提供在Adobe Analytics中匯入高階資料的簡單方法。 您可以指定時間戳記、變數值和相關聯的量度。 接著，每個維度專案的量度會相應增加。 如果您想要並排檢視離線和線上資料，此功能就十分實用。 不過，它不會將線上和離線資料連結在一起。
* **交易ID資料來源**：如果AppMeasurement傳送的點選和資料來源列包含相符的交易ID，則資料來源中的維度和量度值會附加至該點選。

**完整處理資料來源** 自2021年3月25日起不再以資料來源型別提供。 請參閱 [生命週期結束公告](full-processing-eol.md) 以取得詳細資訊。

Adobe也提供 [資料來源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，可讓您建立資料來源及上傳資料，而不需使用產品UI或FTP位置。

## 後續步驟

[資料來源快速入門](getting-started.md)：將簡單資料來源上傳至開發報表套裝。
