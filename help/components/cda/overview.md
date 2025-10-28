---
title: 跨裝置分析
description: 瞭解如何將裝置資料連結在一起，將資料從以裝置為中心轉變為以人為中心。
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: 6c74f4d4c14765742a2aafdfff2a083c6b0a7183
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 57%

---

# 跨裝置分析

{{available-existing-customers}}

>[!WARNING]
>
>跨裝置分析中的裝置圖表將於2025年12月31日&#x200B;**停止提供**。 請將目前任何啟用裝置圖表的VRS切換為[欄位型方法](/help/components/cda/field-based-stitching.md)。
>


跨裝置分析 (CDA) 功能將 Analytics 從裝置導向檢視轉變為以人為導向的檢視。因此分析師可以瞭解跨瀏覽器、裝置或應用程式的使用者行為。Adobe 支援將裝置資料連結在一起的兩個重要工作流程：

* [**依欄位拚接**](field-based-stitching.md)：推薦的拚接選項，因為這僅使用確定性比對將裝置連結在一起。
依欄位彙整可讓您選擇Analytics變數，作為虛擬報表套裝中跨裝置彙整的基礎。

* [**裝置圖表**](device-graph.md)：跨裝置分析會與私人圖表通訊，以將裝置拚接在一起。

使用 CDA，您可以回答下列問題：

* 有多少人與我的品牌互動？他們使用的裝置數量與類型為何？他們互相重疊的程度？
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何？登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換？
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變？我的漏斗分析會有何改變？
* 使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同？

當裝置連結時，變數的永續性會跨裝置傳遞。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站。該使用者找到您的行動應用程式並安裝，最終在其行動裝置上進行購買。當使用跨裝置分析時，您可以將行動裝置上的收入歸因於在其桌上型電腦上點擊的廣告。

Microsoft Azure用於跨裝置分析。 Adobe 會使用 Azure 來儲存裝置圖表資料，及執行跨裝置連結。因此，Adobe Analytics資料會在Adobe的資料處理中心與Adobe布建的Microsoft Azure例項之間來回傳遞。

請參閱[跨裝置分析Spark頁面](https://express.adobe.com/page/8ZpjsX6Lp5XTM/)，進一步瞭解跨裝置分析的功能和特色。

## 先決條件

使用跨裝置分析需要[欄位式拼接](field-based-stitching.md)和[裝置圖表](device-graph.md)方法，而且兩者都有各自的具體必要條件。

* 必須與 Adobe 簽署包含 Adobe Analytics Ultimate 的合約。
* 貴組織選擇啟用 CDA 的報告套裝。Adobe建議報表套裝中包含跨裝置資料，也就是來自多種裝置/瀏覽器/應用程式的資料。 某些組織將此概念稱為「全域」報表套裝，但從地理角度來說，跨裝置分析不見得須為全域。

## 限制

跨裝置分析是一項具突破性且完善的功能，但其使用方式有所限制。[依欄位拚接](field-based-stitching.md)和[裝置圖表](device-graph.md)方法也有各自的具體限制。

* 跨裝置分析功能只能透過Analysis Workspace使用。
* 跨裝置分析功能無法跨報表套裝運作，也無法合併來自多個報表套裝的資料。
* Adobe Analytics 報告套裝無法對應至多個組織識別碼。由於跨裝置分析會連結一個指定報表套裝中的裝置，因此跨裝置分析無法用於連結跨多個組織ID的資料。
* 跨裝置分析使用複雜的處理管道，其中包含多個相依元件。 此管道與基本Analytics報告工作流程並行執行。 在原始報表套裝和Cross-Device Analytics虛擬報表套裝之間，預計點選總數的資料不符率約為1%。
* Cross-Device Analytics 使用虛擬報表套裝和報表時間處理，且各有其專屬的限制。例如，它們目前並不支援行銷管道變數。如需這些限制的詳細資訊，請參閱[虛擬報表套裝](/help/components/vrs/vrs-about.md)和[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)。
* 專用圖表是使用與Experience Cloud和Adobe Analytics中的[客戶屬性](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/services/customer-attributes/attributes)功能所使用相同ID同步的ID同步。 不過，跨裝置分析虛擬報表套裝（不論是根據專用圖表或欄位式連結）與其餘的「客戶屬性」功能不相容。 換句話說，以客戶屬性為主的維度不適合在Cross-Device Analytics虛擬報表套裝中使用。
* 跨裝置分析目前與A4T不相容。
* 1.4 API 不受支援。Power BI 連接器和 Report Builder 都需依賴 1.4 API，因此與 CDA 不相容。
* Adobe的主動監控跨裝置分析銜接程式僅限於生產報表套裝。
* 跨裝置分析目前與Adobe Analytics [資料修復API](https://developer.adobe.com/analytics-apis/docs/2.0/)不相容
* 虛擬報表套裝中的歷史資料會隨著 Adobe 識別和連結裝置而改變。來源報表套裝中的資料不會變更。
* 拼接資料會遵循 8 到 12 小時的延遲時間。
* 特定裝置的比對紀錄資料最多可存放 1 年。
* 如果裝置在一年內達到非常多的比對紀錄條目，則比對紀錄將被截斷。確切的限制會依所使用的拼接選項而定。
