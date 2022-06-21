---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c083c9d62d71dfd2d8a6360f24d8cc40f18f427d
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 68%

---

# 本Adobe Analytics發行說明（2022年6月）

**上次更新日期**：2022 年 6 月 16 日

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| **新建流可視化UI** | 為流可視化提供其他功能，使其更強大、更強大。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 2022年6月15日開始推出；2022年6月27日或28日前正式提交 |
| **共用移動記分卡中的注釋** | 可以顯示在Workspace-Mobile Scorecard中建立的注釋。 這允許您直接在Mobile Scorecard項目中共用上下文資料細微差別和有關您的組織和市場活動的洞見，可在分析儀表板移動應用中查看。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=en) | 2022 年 6 月 15 日 |
| **支援具有邊緣集合的促銷變數的產品語法版本** | 現在，您可以通過設定相關的XDM欄位，使用產品語法的等效項來設定促銷變數。 請參閱 [產品變數](../implement/vars/page-vars/products.md) 的子菜單。 `products` 變數和 [Adobe Experience Edge中的分析變數映射](../implement/aep-edge/variable-mapping.md) 的子菜單。 | 2022 年 6 月 15 日 |
| **透過 Experience Edge 填入生命週期維度和量度** | 透過 Experience Edge 傳送的行動生命週期資料現在會出現在 Analytics 報告中。 有關XDM欄位與現有移動生命週期報告對應的詳細資訊，請參閱文檔。 [了解更多](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 2022 年 5 月 27 日 |
| **分析處理規則中提供的移動服務處理規則** | Adobe移動服務終止日期為2022年12月31日。 由Adobe移動服務建立或生成的現有處理規則將自動遷移到Adobe Analytics處理規則，您可以在這些規則中編輯和管理它們。 可以查看，但在產品日落之前，無法在移動服務中編輯。 如有其他問題或需要更多支援，請和 Adobe 客戶服務聯絡。[了解更多](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=en) | 2022 年 6 月 15 日 |
| **分類集 — 第1階段** | 這一新的分類用戶體驗的分階段發佈顯著提高了對客戶擁有的分類資料的可見性。 請參閱 [分類集](../components/classifications/sets/overview.md) 的子菜單。 | 有限測試於2022年6月15日開始，2023年初正式提供 |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics 中的修正

AN-251686；AN-283542；AN-286572；AN-286945；AN-286784；AN-286944；AN-287012；AN-287319；AN-287333；AN-287348；AN-287429；AN-288238；AN-288281；AN-288660；AN-288769；AN-288798；AN-288871；AN-288872；AN-288941；AN-288951；AN-288952；AN-288956；AN-289062；AN-289340；AN-289346；AN-289488；AN-289562；AN-289580；AN-289861；AN-289892;

### 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，，我們宣布了淘汰排程報告的幾個特定功能，以便為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告，以及擷取新資料的能力。<p>因應客戶要求延長以及為了順利從 Reports and Analytics 進行轉換，我們決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍為九個月；報告和資料擷取的傳遞將在此期間結束時暫停，除非重新啟用排程。<p>要重申，這些功能將於2023年1月31日棄用。 在此日期之前，您必須將計畫報告遷移到您在Adobe Analytics可用的其他機制之一。 如有其他問題或需要更多支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們對 Report Builder 中的排程工作推出變更，這屬於我們效能和傳遞最佳化工作的一部分。這些變更包括移除已排程傳遞在「x 次發生次數後結束」的能力。因應多位客戶要求更多時間以便探索和實施替代方案，我們決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**。<p>您可以繼續計畫每小時Report Builder任務，並在最多99次事件後結束這些任務。 請注意，回復僅適用於每小時工作；「x 次發生次數後結束」仍不適用於所有其他傳遞間隔 (每日、每週、每月和每年)。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有其他問題或需要更多支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP 升級** | 2022 年 5 月 9 日 | 此前，我們曾告知 Adobe 將在 2022 年 5 月升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。我們已將此升級推遲到 **2022 年夏天**。進行此變更後，將不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hant)詳述的變更。 |
| **更新支援部分客戶的瀏覽器加密方法** | 2022 年 3 月 28 日 | Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。**2022 年 6 月 23 日** 起，對於安全等級設定為「高」的客戶，部分 HTTPS 加密算法 (稱為加密) 的支援服務會被移除。此操作表示有些較舊版作業系統無法再將數據發送到 Analytics，因為這些系統不支援現代化的加密方法。使用預設「標準」密碼安全設定的客戶不會受到影響。我們已聯絡過目前設定為「高」等級的所有客戶。受此影響的密碼的詳細清單 |
| **2022 ISO 區域更新** | 2021 年 3 月 11 日 | Adobe對2022 ISO區域執行更新 **2022年6月10日**。 預計此版本後將會有較小的地區資訊更新。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

### AppMeasurement

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

