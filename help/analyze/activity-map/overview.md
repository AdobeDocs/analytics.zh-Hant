---
description: 使用視覺疊加層對連結活動進行排名，以監視您網頁的客群參與度。
title: Activity Map 概觀
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
TQID: https://experienceleague.adobe.com/1-o8wAr6cY8jSR2facQEvh--wvXByJf6R01r4RcVEhI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 100%

---

# Activity Map 概觀

Adobe Analytics Activity Map 是 Adobe Analytics 中的一項功能，可提供網頁和行動應用程式上使用者參與度的視覺化表示。 此功能可讓行銷人員和分析師追蹤和分析使用者的互動情形，例如點按和捲動行為。 Activity Map 會產生熱度圖與疊加層報告，顯示網頁上最受歡迎的元素，協助您最佳化數位體驗。

Activity Map 作為一個概念，是由數個重要的元件所組成：

* **報告套裝設定**：在您開始使用 Activity Map 之前，報告套裝必須先啟用 Activity Map。 請參閱報告套裝設定中的 [Activity Map 報告](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。
* **實施**：大多數 Activity Map 報告皆可開箱即用。 然而，部分網站可能需要額外的實施，才能充分發揮連結追蹤的效益。 以下是可用的實施變數：
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：依連結名稱篩選點按資料。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：依區域名稱篩選點按資料。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)：變更用來填入 Activity Map 區域維度的屬性。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md)：自訂 Activity Map 用來填入 Activity Map 連結維度的邏輯。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md)：自訂 Activity Map 用來填入 Activity Map 區域維度的邏輯。
* **疊加層**：一個瀏覽器擴充功能，讓您可以檢視疊加在網站上的點按資料。 如需更多資訊，請參閱 [Activity Map 擴充功能介面](overlay/overview.md)。 此功能不適用於 Web SDK 實施方式。
* **維度**：除了疊加層擴充功能之外，Activity Map 也提供多個您可在 Analysis Workspace 中使用的維度。
   * [Activity Map 連結](/help/components/dimensions/activity-map-link.md)：被點按的連結名稱。
   * [Activity Map 區域](/help/components/dimensions/activity-map-region.md)：被點按的區域名稱。
   * [Activity Map 頁面](/help/components/dimensions/activity-map-page.md)：點按連結時的頁面名稱。
   * [依區域區分的 Activity Map 連結](/help/components/dimensions/activity-map-link-by-region.md)：Activity Map 連結與 Activity Map 區域的串接值。

## 功能和優點

* **使用者參與度的視覺化呈現**：Activity Map 提供使用者行為的動態視覺化呈現，讓您能清楚看見使用者實際點按的位置。 這些視覺化資料讓您更輕鬆地確認相關模式、趨勢以及感興趣的區域。 接著，您就能針對設計、內容放置環境以及使用者流程做出有明智的決策。

* **熱度圖**：Activity Map 會產生熱度圖，顯示網頁中點按次數最多或互動次數最多的區域。 熱度圖是使用顏色編碼來表示參與程度，讓您能夠找出互動熱點，並讓注意力優先放在高影響力的區域。 這項資訊對於最佳化行動呼籲按鈕、連結、表單或任何其他互動元素而言可能非常實用。

* **疊加層報告**：Activity Map 中的層加層報告提供網頁上特定元素的詳細點按量度。 透過了解各個元素的點進率與參與度等級，您可以微調設計與內容策略，以提升使用者體驗。 此功能不適用於 Web SDK 實施方式。

* **區段分析«**：您可以根據不同的區段來分析使用者行為，例如流量來源、人口統計資料或人物誌。 透過將資料進行區段劃分，您可以發現特定使用者群組的重要洞察，進而實現個人化體驗與精準的行銷策略。

## 實際應用

* **網站最佳化**：Activity Map 協助您透過識別表現不佳的元素、改善導覽以及提升整體使用者體驗，將您的網站最佳化。 透過分析使用者互動，您可以做出以資料為依據的決策，來簡化使用者流程、簡化表單，或調整內容放置環境以發揮最大影響力。

* **轉換率最佳化**：Activity Map 會以視覺化方式呈現使用者參與度並分析點進率，在進行 CRO 中發揮至關重要的作用。 您可以發現轉換的障礙，並嘗試不同的設計變化，以最佳化轉換漏斗、登陸頁面以及結帳程序。

* **A/B 測試**：Activity Map 可與 A/B 測試結合使用，以衡量設計或內容變更所帶來的影響。 透過比較不同版本的網頁之間的參與量度，您可以判斷哪些變化能帶來更高的使用者參與度、轉換率或收入。

