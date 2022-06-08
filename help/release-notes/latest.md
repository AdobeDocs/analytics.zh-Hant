---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 63%

---

# Adobe Analytics 目前的版本注意事項 (2022 年 5 月)

**上次更新**:2022年6月8日

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| 透過 Experience Edge 填入生命週期維度和量度 | 透過 Experience Edge 傳送的行動生命週期資料現在會出現在 Analytics 報告中。 如需有關透過 Experience Edge 收集哪些生命週期資料以及這些資料如何對應到現有生命週期報告的詳細資訊，請參閱相關文件。 [了解更多 - 即將推出] | 2022 年 5 月 27 日 |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics 中的修正

(為多個客戶進行的修正)

不適用

### Adobe Analytics 中的其他修正

(為個別客戶進行的修正)

AN-274429；AN-279640；AN-280918； AN-280945；AN-282884；AN-283565；AN-284785；AN-284814；AN-284854；AN-284989；AN-285244；AN-285253；AN-285432；AN-285528；AN-285535；AN-285710；AN-286255；AN-286340；AN-286434；AN-286454；AN-286630；AN-286716；AN-286854；AN-286911

### 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 在報告和分析中暫停計畫的報告 | 2022年6月8日 | 2022年4月21日，我們宣佈對計畫報告中特定的幾個功能進行了折舊，以準備之前宣佈的 [報告和分析的生命週期結束](https://express.adobe.com/page/6WnF8JK6IRDhf/)。 這些功能包括計畫新報告和新資料提取的能力。<p>為響應客戶尋求擴展並簡化從Reports and Analytics過渡的請求，我們決定將對這些功能的訪問擴展到 **2023年1月31日**。 請注意，報告和資料摘要的到期時間窗口將繼續限制為9個月；除非重新激活計畫，否則報告和資料提取交付將在此期間結束時暫停。 <p>要重申，這些功能將於2023年1月31日棄用，在此之前，您需要將計畫報告遷移到您在Adobe Analytics可用的其他機制之一。 如有其他問題或需要更多支援，請和 Adobe 客戶服務聯絡。 |
| 正在暫停計畫任務Report Builder | 2022年6月8日 | 2022年4月21日，我們在Report Builder中對計畫任務進行了更改，作為效能和交付優化工作的一部分。 這些更改包括刪除計畫交貨「在x次事件後結束」的功能。 為響應幾個客戶請求尋求更多時間來探索和實施備選方案，我們決定以有限的方式恢復此選項，直到 **2023年1月31日**。<p>您將繼續能夠計畫每小時Report Builder任務，並在最多99次事件後結束這些任務。 請注意，回滾僅適用於小時任務；「x次事件後結束」將不適用於所有其他交付間隔（每日、每週、每月和每年）。 請注意，此選項將於2023年1月31日棄用。 如需更多問題或支援，請聯繫Adobe客戶服務。 |
| **SFTP 升級** | 2022 年 5 月 9 日 | 此前，我們曾告知 Adobe 將在 2022 年 5 月升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。我們已將此升級推遲至 **2022年夏季**。 進行此變更後，將不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hant)詳述的變更。 |
| **更新支援部分客戶的瀏覽器加密方法** | 2022 年 3 月 28 日 | Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。**2022 年 6 月 23 日** 起，對於安全等級設定為「高」的客戶，部分 HTTPS 加密算法 (稱為加密) 的支援服務會被移除。此操作表示有些較舊版作業系統無法再將數據發送到 Analytics，因為這些系統不支援現代化的加密方法。使用預設「標準」密碼安全設定的客戶不會受到影響。我們已聯絡過目前設定為「高」等級的所有客戶。受此變動影響的加密詳細列表可在此處查看。 |
| **2022 ISO 區域更新** | 2021 年 3 月 11 日 | Adobe 預計在 **2022 年 6 月 10 日**&#x200B;執行 2022 ISO 區域更新。 預計此版本後將會有較小的地區資訊更新。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

### AppMeasurement

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

