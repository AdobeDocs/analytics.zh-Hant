---
description: 使用視覺化覆蓋圖來排名連結活動，以監控您網頁的觀眾參與情形。
title: Activity Map 概觀
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 4%

---

# Activity Map 概觀

Adobe Analytics Activity Map 是 Adobe Analytics 中的一項功能，可提供網頁和行動應用程式上使用者參與度的視覺化表示。它可讓行銷人員和分析師追蹤和分析使用者互動，例如點按和捲動行為。 Activity Map會產生熱度圖和覆蓋報表，顯示網頁上最熱門的元素，協助您最佳化數位體驗。

Activity Map作為一個概念，由幾個重要元件組成：

* **報表套裝設定**：報表套裝必須先啟用Activity Map，您才能開始使用。 請參閱報表套裝設定中的[Activity Map報表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)。
* **實作**：大部分的Activity Map報表都可立即使用。 不過，有些網站可能需要額外的實施，才能充分運用連結追蹤。 下列實作變數可供使用：
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：依連結名稱篩選點選資料。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：依區域名稱篩選點按資料。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)：變更填入Activity Map地區維度的屬性。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md)：自訂Activity Map用來填入Activity Map連結維度的邏輯。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md)：自訂Activity Map用來填入Activity Map地區維度的邏輯。
* **覆蓋**：可讓您檢視網站上覆蓋之點按資料的瀏覽器擴充功能。 如需詳細資訊，請參閱[Activity Map擴充功能介面](overlay/overview.md)。
* **維度**：除了覆蓋延伸功能外，Activity Map還提供幾個可在Analysis Workspace中使用的維度。
   * [Activity Map連結](/help/components/dimensions/activity-map-link.md)：被點按的連結名稱。
   * [Activity Map地區](/help/components/dimensions/activity-map-region.md)：被點按的地區名稱。
   * [Activity Map頁面](/help/components/dimensions/activity-map-page.md)：點選連結時的頁面名稱。
   * [各地區的Activity Map連結](/help/components/dimensions/activity-map-link-by-region.md)： Activity Map連結與Activity Map地區的串連值。

## 功能和優點

* **使用者參與視覺化**： Activity Map可提供使用者行為的動態視覺化表示法，讓您精確檢視使用者點選的位置。 此視覺資料可讓您更容易識別模式、趨勢和感興趣的區域。 接著，您就可以針對設計、內容位置和使用者流程，做出明智的決策。

* **熱度圖**： Activity Map會產生熱度圖，顯示網頁中最常點按或互動的區域。 熱度圖使用色彩編碼來代表參與程度，讓您能夠識別熱點並優先關注高影響力區域。 此資訊對於最佳化call-to-action按鈕、連結、表單或任何其他互動式元素非常有用。

* **覆蓋報表**： Activity Map中的覆蓋報表可提供網頁上特定元素的詳細點選量度。 透過瞭解個別元素的點進率和參與層級，您可以微調設計和內容策略以提升使用者體驗。

* **區段分析**：您可以根據不同的區段來分析使用者行為，例如流量來源、人口統計或角色。 透過劃分資料，您可以揭示特定使用者群組的寶貴見解、實現個人化體驗和目標式行銷策略。

## 實用應用程式

* **網站最佳化**： Activity Map可協助您識別表現缺佳的元素、改善導覽並增強整體使用者體驗，進而最佳化您的網站。 透過分析使用者互動，您可以進行資料導向式決策，以簡化使用者流程、簡化表單或調整內容位置，以獲得最大的影響。

* **轉換率最佳化**：透過視覺化使用者參與度和分析點進率，Activity Map在CRO工作中扮演關鍵角色。 您可以找出轉換的障礙，並使用不同的設計變異來實驗，以最佳化轉換漏斗、登陸頁面和結帳程式。

* **A/B測試**： Activity Map可以與A/B測試結合，以測量設計或內容變更的影響。 透過比較不同網頁版本之間的參與量度，您可以判斷哪些變異會導致較高的使用者參與度、轉換率或收入。

