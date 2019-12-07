---
description: 有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。
subtopic: Data sources
title: 資料來源範本概觀
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料來源範本概觀

有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。

此精靈產生的範本，是為了讓您開始匯入而設計。不限使用範本中定義的欄。您可以視需要新增任何其他欄，只要選取的資料處理類型支援量度或定義。

您可以在下列各節查閱各類型支援的量度和維度:

* [網站記錄檔](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (不再支援)
* [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [訪客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [完全處理](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。資料來源伺服器處理後，您的行銷報表就可以使用匯入的資料。

The Data Source template is a [!DNL .txt] file that you can open with any text editor. 不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「[!UICONTROL 資料來源啟動精靈]」中的選擇而異。

請參閱[匯入檔案參考](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)。
