---
title: 跨裝置分析
description: 將裝置資料整合在一起，將您的資料從以裝置為主變更為以個人為主。
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 73%

---


# 跨裝置分析

跨裝置分析功能將 Analytics 從裝置導向檢視轉變為以人為導向的檢視。因此分析師可以瞭解跨瀏覽器、裝置或應用程式的使用者行為。Adobe支援兩個重要工作流程，將裝置資料連結在一起：

* [**現場拼接**](field-based-stitching.md):可讓您選擇Analytics變數作為虛擬報表套裝中跨裝置拼接的基礎。 使用確定性匹配將設備連接在一起。 Adobe建議針對大部分的確定性比對使用案例使用欄位式拼接。
* [**裝置圖**](device-graph.md):CDA會與裝置圖形通訊，以將裝置接合在一起。 co-op圖同時使用確定性和概率性匹配。

使用CDA，您可以回答以下問題：

* 有多少人與我的品牌互動？他們使用的裝置數量與類型為何？他們互相重疊的程度？
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何？登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換？
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變？我的漏斗分析會有何改變？
* 使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同？

當裝置連結時，變數的持續存在性會跨裝置傳遞。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站。該使用者找到您的行動應用程式並安裝，最終在其行動裝置上進行購買。透過跨裝置分析功能，可將收入歸因於使用者在桌上型電腦上點按的廣告。

我們秉持尊重合作夥伴和追求透明的精神，希望客戶了解我們的跨裝置分析會使用 Microsoft Azure。Adobe 會使用 Azure 來儲存裝置圖表資料，及執行跨裝置連結。因此，Adobe Analytics 資料會在 Adobe 的資料處理中心與 Adobe 佈建的 Microsoft Azure 例項之間來回傳遞。

See the [Journey IQ: Cross-Device Analytics Spark page](http://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## 必要條件

使用CDA需要具備下列所有條件。 [基於現場的拼接](field-based-stitching.md) 、 [設備圖方法](device-graph.md) ，也有自己的特定前提。

* 必須與 Adobe 簽署包含 Adobe Analytics Ultimate 的合約。
* 系統會根據報表套裝啟用跨裝置分析功能。Adobe建議報表套裝包含跨裝置資料，即來自多種裝置類型（網路、應用程式等）的資料。 某些組織將此概念稱為「全域」報表套裝，但從地理角度來說 CDA 不見得須為全域。

## 限制

跨裝置分析是一項具突破性且完善的功能，但其使用方式有所限制。[基於現場的拼接](field-based-stitching.md) 、 [設備圖方法](device-graph.md) ，也有各自的特定局限性。

* CDA 只能透過 Analysis Workspace 使用。
* 跨裝置分析功能無法跨報表套裝運作，也無法合併來自多個報表套裝的資料。
* Adobe Analytics 報表套裝無法對應至多個 IMS 組織。由於 CDA 會連結一個指定報表套裝中的裝置，因此 CDA 無法用於連結跨多個 IMS 組織的資料。
* CDA 目前與客戶屬性不相容。這兩個功能在參考相同來源報表套裝的個別虛擬報表套裝中可保持一致。
* 跨裝置分析使用虛擬報表套裝和報表時間處理，且各有其專屬的限制。如需這些限制的詳細資訊，請參閱[虛擬報表套裝](../vrs/vrs-about.md)和[報表時間處理](../vrs/vrs-report-time-processing.md)。
* 1.4 API 不受支援。Power BI 連接器和 Report Builder 都需依賴 1.4 API，因此與 CDA 不相容。
* 虛擬報表套裝中的歷史資料會隨著 Adobe 識別和連結裝置而改變。來源報表套裝中的資料不會變更。
