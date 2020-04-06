---
description: 關於如何使用 Adobe 的資料來源的資訊。
subtopic: Data sources
title: 資料來源運作方式
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 資料來源運作方式

關於如何使用 Adobe 的資料來源的資訊。

>[!NOTE] 透過「資料來源」提交後，匯入的資料與您透過其他方法方法 (如 JavaScript、ActionSource、資料插入 API 等) 收集的報表資料就沒有差別。匯入資料後，便無法移除。

![](assets/data_sources_overview.png)

提交資料有兩種方法：

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

您可以透過行銷報告建立和管理FTP型資料來源，而行銷報告使用FTP檔案傳輸將資料檔案匯入Data Sources。 建立資料來源後，Adobe會提供FTP位置，供您用來上傳資料來源檔案。 上傳後，Data Sources會自動找到並處理它們。 處理後，資料便可用於行銷報告。

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe提供Data Sources API，可讓您以程式設計方式將應用程式連結至Data Sources。 這樣就不需要中介FTP伺服器，並透過HTTP、SOAP和REST傳輸資料。

請參 [閱Data Sources API檔案](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)。
