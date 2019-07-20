---
description: 關於如何使用 Adobe 的資料來源的資訊。
seo-description: 關於如何使用 Adobe 的資料來源的資訊。
seo-title: Data Sources如何運作
solution: Analytics
subtopic: 資料來源
title: Data Sources如何運作
topic: 開發人員和實施
uuid: ee9e6e74-9b00-4733-9a4b-d9 f2 b954 cc7 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Data Sources如何運作

關於如何使用 Adobe 的資料來源的資訊。

>[!NOTE]
>
>透過Data Sources提交後，匯入的資料不會與使用其他方法(JavaScript指標、ActionSource、資料插入API等)收集的報告資料不一致。一旦匯入資料便「無法」移除。

![](assets/data_sources_overview.png)

提交資料的兩種方法:

* [FTP](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

您可透過行銷報表建立和管理 FTP 型資料來源，行銷報表利用 FTP 檔案傳輸將資料檔案匯入資料來源。建立資料來源後，Adobe 會提供 FTP 位置給您，讓您可用以上傳「資料來源」檔案。上傳後，資料來源會自動找到檔案並處理它們。處理完成之後，資料就可以在行銷報表中使用。

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe 提供資料來源 API，讓您以程式將您的應用程式連結至資料來源。這麼做不需要中間媒介的 FTP 伺服器，而是透過 HTTP、SOAP、REST 傳輸資料。

請參閱[資料來源 API 文件](https://marketing.adobe.com/developer/documentation/data-sources/c-data-sources-api)。
