---
description: 有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。
seo-description: 有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。
seo-title: Data Sources範本概述
solution: Analytics
subtopic: 資料來源
title: Data Sources範本概述
topic: 開發人員和實施
uuid: e768bcff-a996-44c7-a7 f2-9a2 c651 ead9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Data Sources範本概述

有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。

此精靈產生的範本，是為了讓您開始匯入而設計。不限使用範本中定義的欄。您可以視需要新增任何其他欄，只要選取的資料處理類型支援量度或定義。

您可以在下列各節查閱各類型支援的量度和維度:

* [網站記錄檔](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [流量](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC) (不再支援)
* [轉換](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [交易 ID](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [完全處理](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。資料來源伺服器處理後，您的行銷報表就可以使用匯入的資料。

The Data Source template is a [!DNL .txt] file that you can open with any text editor. 不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「[!UICONTROL 資料來源啟動精靈]」中的選擇而異。

請參閱[匯入檔案參考](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD)。
