---
description: Ad Hoc Analysis 已與 Analytics Segmentation 環境整合，可讓您在 Adobe 產品間建立、共用、管理和套用訪客區段。Ad Hoc Analysis 為其區段產生器和區段管理員提供 Java 型使用者介面，這些介面與其他 Analytics 工具所使用的網路型工具完全相同，能比對伺服器呼叫並提供來自 Java 控制台的相同功能。
title: 建立區段
topic: Ad hoc analysis
uuid: e14fb777-900a-4700-8dc7-56a45c678d29
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '1209'
ht-degree: 94%

---


# 建立區段

Ad Hoc Analysis 已與 Analytics Segmentation 環境整合，可讓您在 Adobe 產品間建立、共用、管理和套用訪客區段。Ad Hoc Analysis 為其區段產生器和區段管理員提供 Java 型使用者介面，這些介面與其他 Analytics 工具所用的網路型工具完全相同，能比對伺服器呼叫並提供來自 Java 控制台的相同功能。

「Ad Hoc Analysis」包含用來建立區段的熟悉功能，再加上新功能升級，例如用來設定區段管理[工作流程](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html)的[區段管理員](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segmentation-workflow/seg-manage.html)。跟以往一樣，您可以在[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)中建立並儲存區段，或在 Ad Hoc Analysis 控制台中[從流失報表產生區段](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html)，然後將新區段或擴充區段儲存至觀眾庫，以供一般存取和應用。 ![](assets/seg__overview_ad_hoc.png)

## Ad Hoc Analysis 中的 Unified Segmentation {#section_5FA03A06DE054448AD519CE30C39E294}

如需在 Unified Segmentation 環境中建立和管理區段的相關資訊和指示，包括臨機分析功能，請參閱 [Unified Segmentation](/help/components/segmentation/segmentation-workflow/seg-build.md) 文件。

* [新特性](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [現有的區段有什麼改變？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [現有的區段資料夾有什麼改變？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [我是否可以在區段管理員中管理所有 Analytics 區段？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [點擊容器是什麼？是否與頁面檢視容器不同？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [要使用、建立和管理區段需要有什麼權限？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [我應如何處理具有…的重複區段](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [Adobe 建議我該如何清理區段？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [我為何刪除不了區段？](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [更多關於現有區段會有什麼改變的資訊](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## 功能 {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* [區段在所有報表套裝中都通用。](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/seg-home.html)之前，不同的報表套裝使用不同的區段。
* [區段管理員](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segmentation-workflow/seg-manage.html)可讓您藉由區段共用、標記、驗證及核准功能來設定[工作流程](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html)。
* 並已更新[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)，簡化區段建立過程。
* 您可以[標記區段](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html)來加以組織以供稍後搜尋，而不是透過使用資料夾的方式。之前，您是使用資料夾 (在 [!DNL ad hoc analysis] 中) 來組織區段。
* 您可以在 Ad Hoc Analysis 外建立[循序區段](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html)。

   >[!NOTE]
   >
   >在 Ad Hoc Analysis 中，您不能在區段加入日期範圍。此功能可在 Analysis Workspace 中使用。您也可以在 Ad Hoc Analysis 中不使用「僅限在此之前/僅限在此之後」的順序。

## 現有的區段有什麼改變？ {#section_76CF47142D1A4FB6A0718AD9073049FE}

您的現有區段將繼續按照 Analytics Segmentation 推出前的方式運作。任何已套用這些區段的報表都將繼續正常運作。

原本預先定義的區段與套裝區段多半會以區段範本的形式移轉至區段產生器。區段範本的用途是快速建立具有常見對象的自訂區段。區段範本無法直接套用至報表，但可以輕易儲存成自訂區段。

## 現有的區段資料夾有什麼改變？ {#section_FB04DCF775694E69B761DCA53F301C30}

「區段管理員」不再使用 (Ad Hoc Analysis) 資料夾，而是使用[標記](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html)。您的資料夾名稱會自動轉換成標記，而這些標記會套用至對應的區段。

## 我是否可以在區段管理員中管理所有 Analytics 區段？ {#section_AF5EDD72C74A4739BD40C4AF125CE489}

在 Ad Hoc Analysis 區段管理員中，您只看得到屬於您 (您建立的區段) 和專屬於您的共用區段。

## 點擊容器是什麼？它是否與頁面檢視容器不同？ {#section_65BBE60A836C4001938830DDA15DC256}

「頁面檢視」容器已重新命名為「點擊」容器，以表示此容器會將所有類型的資料 (而不只是頁面檢視) 分段。例如，連結追蹤呼叫與來自行動 SDK 的 [!DNL trackAction] 呼叫均可在點擊容器中受到納入或排除。

請注意，此容器的運作方式並無改變，只是名稱有變而已。

## 要使用、建立和管理區段需要有什麼權限？ {#section_648DFA3A882146C485A84ED014EEC707}

所有使用者均可建立和編輯個人區段。這些區段可直接共用給任何其他 Analytics 使用者。

管理員可以編輯任何區段、與群組[共用區段](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/t-seg-share.html)，以及為組織[設定存取區段的權限](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segment-reference/seg-rights.html)。

## 有具有相同名稱、但不同定義的重複區段時該怎麼辦？ {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

由於區段可在多個報表套裝中運作，因此您可能發現有多個區段具有相同名稱。建議您採取以下任一操作：

* 重新命名具有相同名稱、但不同定義的區段，或是
* 刪除不再需要的區段。

## Adobe 建議我該如何清理區段？ {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* 以 legacy 標記標記所有區段。
* 檢閱您現有的區段。
* 適時將這些區段新增至區段庫。
* 核准要做為標準區段的區段。
* 標記區段時依照最佳實務。

## 我為何刪除不了區段？ {#section_0FEB6711031A4ABCA915CDA745ECF38D}

如果區段已[發佈至 Experience Cloud](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/audiences/t-publish-audience-segment.html)，則您無法加以刪除或編輯。不過，您可以加以複製再編輯複製的版本。

## 更多關於現有區段會有什麼改變的資訊 {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 區段類別 </th> 
   <th colname="col2" class="entry"> 這些區段有何變化？ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 我的最愛區段 (Ad Hoc Analysis) </td> 
   <td colname="col2">這些 Ad Hoc Analysis 區段在 Adobe Analytics 中會顯示為一般區段。 <p>不應將它們與「區段管理員」中可讓您將區段標記為我的最愛的「我的最愛」功能混淆。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">預先設定的區段： 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">單頁存取次數 </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">來自行動裝置的瀏覽次數 </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">來自免費搜尋的瀏覽次數 </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">來自付費搜尋的瀏覽次數 </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">具有訪客 ID Cookie 的瀏覽次數 </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些區段會以區段範本的形式移轉至區段產生器。 </p> <p>已套用這些區段的現有報表將可繼續正常運作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud (套裝) 區段： 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">非購買者 </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">購買者 </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">首次瀏覽次數 </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">來自社交網站的瀏覽次數 </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">超過 10 分鐘的瀏覽次數* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">先前造訪過 5 次以上的造訪* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">來自 Facebook 的瀏覽次數* </li> 
    </ul> </td> 
   <td colname="col2"> <p> 這些區段 (具有星號 * 標記者除外) 多半會以區段範本的形式移轉至區段產生器。另外，新增了數個新的區段範本。 </p> <p>已套用這些區段的現有報表將可繼續正常運作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">管理員區段 <p>(也稱為「全域」區段) </p> </td> 
   <td colname="col2"> <p> <b>管理員</b>區段將會移轉至新的區段介面，並顯示為共用給每個人的區段。 </p> <p>這些區段的擁有者是設為其帳戶在登入公司的管理員使用者清單中存在最久的管理員，不過所有管理員都可以刪除、編輯和共用這些區段。 </p> <p>「管理主控台」中原本供管理員建立和管理這些全域區段的區段管理介面已不存在。管理員現在應該使用新的區段產生器，來建立區段以及將區段共用給適當的群組/個人或每個人。 </p> </td> 
  </tr> 
 </tbody> 
</table>

