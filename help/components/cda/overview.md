---
title: 跨裝置分析
description: 將裝置資料連結在一起，將資料從以裝置為中心轉變為以人為中心。
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 99%

---

# 跨裝置分析

跨裝置分析功能將 Analytics 從裝置導向檢視轉變為以人為導向的檢視。因此分析師可以瞭解跨瀏覽器、裝置或應用程式的使用者行為。Adobe 支援將裝置資料連結在一起的兩個重要工作流程：

* [**依欄位彙整**](field-based-stitching.md)：您可選擇 Analytics 變數，作為虛擬報表套裝中跨裝置結合的基礎。使用確定性比對來將裝置連結在一起。Adobe 建議針對大部分的確定性比對使用案例使用依欄位彙整。
* [**裝置圖表**](device-graph.md)：CDA 會與裝置圖表通訊，以將裝置彙整在一起。Co-op 圖表同時使用確定性比對和概率比對。

使用 CDA，您可以回答下列問題：

* 有多少人與我的品牌互動？他們使用的裝置數量與類型為何？他們互相重疊的程度？
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何？登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換？
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變？我的漏斗分析會有何改變？
* 使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同？

當裝置連結時，變數的永續性會跨裝置傳遞。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站。該使用者找到您的行動應用程式並安裝，最終在其行動裝置上進行購買。當使用 Cross-Device Analytics 時，您可以將行動裝置上的收入歸因於在其桌上型電腦上點擊的廣告。

我們秉持尊重合作夥伴和追求透明的精神，希望客戶了解我們的跨裝置分析會使用 Microsoft Azure。Adobe 會使用 Azure 來儲存裝置圖表資料，及執行跨裝置連結。因此，Adobe Analytics 資料會在 Adobe 的資料處理中心與 Adobe 佈建的 Microsoft Azure 例項之間來回傳遞。

請參閱[歷程 IQ：跨裝置分析 Spark 頁面](https://adobe.ly/aacda)，進一步了解跨裝置分析的功能和特色。

## 必要條件

使用 CDA 需具備下列所有條件。[依欄位彙整](field-based-stitching.md)和[裝置圖表](device-graph.md)方法也有各自的具體必要條件。

* 必須與 Adobe 簽署包含 Adobe Analytics Ultimate 的合約。
* 系統會根據報表套裝啟用跨裝置 Analytics 功能。Adobe 建議報表套裝中包含跨裝置資料，也就是來自多種裝置類型 (網頁、應用程式等) 的資料。某些組織將此概念稱為「全域」報表套裝，但從地理角度來說 CDA 不見得須為全域。

## 限制

跨裝置分析是一項具突破性且完善的功能，但其使用方式有所限制。[依欄位彙整](field-based-stitching.md)和[裝置圖表](device-graph.md)方法也有各自的具體限制。

* CDA 只能透過 Analysis Workspace 使用。
* 跨裝置分析功能無法跨報表套裝運作，也無法合併來自多個報表套裝的資料。
* Adobe Analytics 報表套裝無法對應至多個 IMS 組織。由於 CDA 會連結一個指定報表套裝中的裝置，因此 CDA 無法用於連結跨多個 IMS 組織的資料。
* 專用圖表是使用與[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hant#customer-attributes)功能在 Experience Cloud 和 Adobe Analytics 中所用的相同 ID 同步作業。不過，CDA 虛擬報表套裝 (不論是根據專用圖表或欄位式連結) 與其餘的「客戶屬性」功能不相容。 也就是說，以客戶屬性為主的維度不適合在 CDA 虛擬報表套裝中使用。
* CDA 目前與 A4T 不相容。
* 跨裝置分析使用虛擬報表套裝和報表時間處理，且各有其專屬的限制。如需這些限制的詳細資訊，請參閱[虛擬報表套裝](../vrs/vrs-about.md)和[報表時間處理](../vrs/vrs-report-time-processing.md)。
* 1.4 API 不受支援。Power BI 連接器和 Report Builder 都需依賴 1.4 API，因此與 CDA 不相容。
* 虛擬報表套裝中的歷史資料會隨著 Adobe 識別和連結裝置而改變。來源報表套裝中的資料不會變更。
* Adobe 的主動監控 CDA 銜接程序僅限於生產報表套裝。
* CDA 目前與 Adobe Analytics [資料修復 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md) 不相容。
