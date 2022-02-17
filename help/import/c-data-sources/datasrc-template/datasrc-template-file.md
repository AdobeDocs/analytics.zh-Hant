---
description: 有關資料來源範本的資訊；資料來源範本是一種資料框架，適合用來提交特定外部資料集給資料來源s。
subtopic: Data sources
title: 資料來源範本概觀
topic-fix: Developer and implementation
feature: Data Sources
exl-id: d3122582-d392-4bd9-af2a-fb3d1292ba66
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

例如，針對訪客 ID 資料類型，可以替列在[訪客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md) 中的任何量度或維度新增欄。

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。資料來源伺服器處理後，您的行銷報表就可以使用匯入的資料。

資料來源範本是 [!DNL .txt] 檔案，可以用任何文字編輯器開啟。不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「[!UICONTROL 資料來源啟動精靈]」中的選擇而異。

請參閱[匯入檔案參考](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)。
