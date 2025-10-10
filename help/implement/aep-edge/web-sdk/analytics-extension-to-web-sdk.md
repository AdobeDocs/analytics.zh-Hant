---
title: 從Adobe Analytics標籤擴充功能移轉至網路SDK標籤擴充功能
description: 更新Adobe Experience Platform資料收集標籤上的Analytics實作，以使用Web SDK擴充功能。
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 6%

---

# 從Adobe Analytics標籤擴充功能移轉至網路SDK標籤擴充功能

此實作路徑涉及從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能的方法。 其他實作路徑會在不同頁面上說明：

* [AppMeasurement移轉至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md)：移轉至Web SDK的順暢且有條不紊的方法，但不使用標籤。 請改為手動移除Adobe Analytics資料收集程式庫(`AppMeasurement.js`)，並將其取代為Web SDK JavaScript程式庫(`alloy.js`)。
* [Web SDK標籤擴充功能](web-sdk-tag-extension.md)：全新的Web SDK安裝，您可使用Adobe Experience Platform Data Collection中的標籤來管理實作。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。
* [Web SDK JavaScript資料庫](web-sdk-javascript-library.md)：使用Web SDK JavaScript資料庫(`alloy.js`)的全新Web SDK安裝。 自行管理實作，而不使用標籤UI。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。

## 此實作路徑的優缺點

使用此移轉方法的優缺點。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優點 | 缺點 |
| --- | --- |
| <ul><li>**您的網站上沒有程式碼變更**：因為您的實作已安裝標籤，所以可以在標籤介面中進行所有移轉更新。</li><li>**使用您現有的實作**：此方法不需要全新實作。 雖然這確實需要新的規則動作，但您可以以最小的變更重複使用現有的資料元素和規則條件。</li><li>**不需要結構描述**：對於移轉至Web SDK的這個階段，您不需要XDM結構描述。 相反地，您可以填入`data`物件，這會直接將資料傳送到Adobe Analytics。 一旦移轉至Web SDK完成，您就可以為貴組織建立結構描述，並使用資料流對應來填入適用的XDM欄位。 如果移轉流程的這個階段需要結構描述，貴組織將被強制使用Adobe Analytics XDM結構描述。 使用此結構描述會使您的組織未來更難以使用您自己的結構描述。</li></ul> | <ul><li>**實作技術債**：由於此方法使用您現有實作的修改形式，因此可能更難追蹤實作邏輯並在需要時執行變更。 自訂程式碼可能特別難以偵錯。</li><li>**需要對應才能將資料傳送到 Platform**：當您的組織準備好使用 Customer Journey Analytics 時，您必須將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform 中的資料集。此動作要求`data`物件中的每個欄位必須是資料流對應工具中的專案，以將其指派給XDM結構描述欄位。 此工作流程僅需進行一次對應，且不涉及進行實施變更。但是，這是額外進行的步驟，在 XDM 物件中傳送資料時不需要進行。</li></ul> |

Adobe建議在下列情況下使用此實施路徑：

* 您已有使用Adobe Analytics標籤擴充功能的現有實作。 如果您有使用AppMeasurement的實作，請改為遵循[從AppMeasurement移轉至Web SDK](appmeasurement-to-web-sdk.md)。
* 您打算在未來使用Customer Journey Analytics，但不想從頭開始將您的Analytics實作取代為網頁SDK實作。 在Web SDK上從頭開始取代實作需要花費最大的心力，但同時也提供最可行的長期實作架構。 如果您的組織願意徹底實施網頁SDK，請參閱Customer Journey Analytics使用手冊中的[透過Adobe Experience Platform網頁SDK擷取資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)。

## 移轉至Web SDK所需的步驟

下列步驟包含需努力達成的具體目標。 按一下每個步驟，以取得如何完成的詳細指示。

+++**1.建立和設定資料流**

在Adobe Experience Platform Data Collection中建立資料流。 當您傳送資料至此資料流時，它會轉送資料至Adobe Analytics。 未來，相同的資料流會將資料轉送至Customer Journey Analytics。

1. 導覽至[experience.adobe.com](https://experience.adobe.com)並使用您的認證登入。
1. 使用右上方的首頁或產品選擇器來導覽至&#x200B;**[!UICONTROL 資料彙集]**。
1. 在左側導覽中，選取&#x200B;**[!UICONTROL 資料串流]**。
1. 選取「**[!UICONTROL 新資料流]**」。
1. 輸入想要的名稱，然後選取&#x200B;**[!UICONTROL 儲存]**。
1. 建立資料流後，請選取&#x200B;**[!UICONTROL 新增服務]**。
1. 在服務下拉式功能表中，選取&#x200B;**[!UICONTROL Adobe Analytics]**。
1. 輸入與您目前傳送分析資料的目標網站相同的報表套裝ID。 按一下「**[!UICONTROL 儲存]**」。

![新增Adobe Analytics服務](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

您的資料流現在已準備好接收資料並傳遞給Adobe Analytics。

+++

+++**2. 將Web SDK擴充功能新增至標籤屬性**

本節將準備您的標籤，以利後續步驟中進行的大量移轉作業。

1. 按一下Adobe Experience Platform介面左上方的漢堡圖示，然後選取&#x200B;**[!UICONTROL 標籤]**。
1. 選取所需的標籤屬性。
1. 在標籤屬性的左側導覽中，選取&#x200B;**[!UICONTROL 擴充功能]**。
1. 選取頂端附近的&#x200B;**[!UICONTROL 目錄]**，檢視所有可用擴充功能的清單。
1. 搜尋並選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;擴充功能，然後按一下右側的&#x200B;**[!UICONTROL 安裝]**。

   ![目錄](assets/catalog.png) {style="border:1px solid lightslategray"}

1. 擴充功能組態設定隨即顯示。 找出「資料串流」段落，然後選取您在上一步中建立的資料串流。

   ![資料流選擇](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. 選取「**[!UICONTROL 儲存]**」。

您的標籤屬性現在已安裝Web SDK。

+++

+++**3.建立資料物件資料元素**

資料物件資料元素提供直覺式架構，可設定Web SDK用來傳送至資料流的裝載。 您在下列步驟中更新的大部分規則都會與此資料元素互動。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL 資料元素]**。
1. 選取&#x200B;**[!UICONTROL 新增資料元素]**
1. 為資料元素執行下列設定：
   * [!UICONTROL 名稱]：您想要的任何專案，例如「資料層」或「資料物件」
   * [!UICONTROL 擴充功能]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 資料元素型別]： [!UICONTROL 變數]
   * 核取方塊可以保持原樣
1. 在右側，選取下列設定：
   * 屬性選項按鈕： [!UICONTROL 資料]
   * 解決方案： [!UICONTROL Adobe Analytics]
1. 選取「**[!UICONTROL 儲存]**」。

![建立資料元素](assets/create-data-element.png) {style="border:1px solid lightslategray"}

您的標籤屬性現在擁有更新每個規則所需的一切。

+++

+++**4.更新規則以使用Web SDK擴充功能，而非Analytics擴充功能**

此步驟包含移轉至Web SDK所需的大部分工作，且需要瞭解您實作的運作方式。 以下提供範例來作為如何編輯典型標籤規則的範例。 更新實施中的所有標籤規則，以Web SDK擴充功能取代Adobe Analytics擴充功能的所有參考。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL 規則]**。
1. 選取要編輯的規則。
1. 選取動作&#x200B;**[!UICONTROL Adobe Analytics — 設定變數]**
1. 記下此規則內設定的所有Analytics變數。 納入在下拉式功能表中設定的變數，以及在自訂程式碼中設定的變數。
1. 將[!UICONTROL 動作組態]變更為下列設定：
   * [!UICONTROL 擴充功能]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 動作型別]：更新變數
1. 確定已在右側的下拉式清單中選取您的資料物件。
1. 將Analytics變數設定為與其在Analytics擴充功能中設定的相同個別值。
   * 在標籤介面中設定的變數可直接轉譯為相同的值。
   * 在自訂程式碼中設定的字串變數需要調整很小。 不要使用`s`物件，改用`data.__adobe.analytics`。 例如，`s.eVar1`會轉譯為`data.__adobe.analytics.eVar1`。
   * 自訂程式碼中的Analytics設定變數和方法呼叫可能需要修改實作邏輯。 檢視每個個別[變數](/help/implement/vars/overview.md)，以決定如何使用網頁SDK來達成其同等專案。
1. 使用Web SDK擴充功能復寫所有規則邏輯後，請選取&#x200B;**[!UICONTROL 保留變更]**。
1. 對使用Adobe Analytics擴充功能設定值的每個動作設定重複這些步驟。 此步驟包含使用標籤介面設定的變數和使用自訂程式碼設定的變數。 自訂程式碼區塊無法在任何地方參照`s`物件。

上述步驟僅適用於設定值的規則。 下列步驟會取代所有使用[!UICONTROL 動作組態] [!UICONTROL 傳送信標]的動作。

1. 選取傳送信標的規則。
1. 選取動作&#x200B;**[!UICONTROL Adobe Analytics — 傳送信標]**。
1. 記下右側[!UICONTROL 追蹤]選項按鈕目前的值（[`s.t()`](../../vars/functions/t-method.md)或[`s.tl()`](../../vars/functions/tl-method.md)）。
1. 將[!UICONTROL 動作組態]變更為下列設定：
   * [!UICONTROL 擴充功能]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 動作型別]： [!UICONTROL 傳送事件]
1. 在右側，將動作設定變更為下列專案：
   * [!UICONTROL 型別]：對於`s.t()`，請使用&#x200B;**[!UICONTROL 網頁詳細資訊頁面檢視]**。 針對`s.tl()`，使用&#x200B;**[!UICONTROL Web Webinteraction連結點按]**。 如果您使用[`s.tl()`](../../vars/functions/tl-method.md)，您也必須在資料物件中包含下列欄位。 執行[!UICONTROL 更新變數]動作組態時，這些欄位會列在[!UICONTROL 其他屬性]下：
      * [連結名稱](../../vars/functions/tl-method.md)
      * [連結類型 &#x200B;](../../vars/functions/tl-method.md)
      * [連結Url](../../vars/config-vars/linkurl.md)
1. 選取&#x200B;**[!UICONTROL 「保留變更」]**。
1. 對使用Adobe Analytics傳送信標的每個動作設定重複這些步驟。

+++

+++**5.發佈更新的規則**

發佈更新規則的工作流程，與標籤設定的任何其他變更相同。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL 發佈流程]**。
1. 選取「**[!UICONTROL 新增資料庫]**」。
1. 為此標籤認可命名，例如「升級至Web SDK」。
1. 選取&#x200B;**[!UICONTROL 新增所有變更的資源]**。
1. 選取「**[!UICONTROL 儲存]**」。
1. 發佈工作流程會顯示橘色點，表示正在建置。 圓點變成綠色後，您的變更即可在開發環境中使用。
1. 在開發環境中測試您的變更，以確保所有規則皆正確引發，且資料物件會填入預期值。
1. 準備就緒後，請提交程式庫進行核准、建置到測試環境，最後核准並發佈到生產環境。

![發佈流程](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6.停用Analytics擴充功能**

當您的標籤實作完全在網頁SDK上後，您就可以停用Adobe Analytics擴充功能。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL 擴充功能]**。
1. 尋找並選取[!UICONTROL Adobe Analytics]擴充功能。 在右側，選取&#x200B;**[!UICONTROL 停用]**。
1. 依照上述相同的發佈工作流程，發佈移除[!UICONTROL Adobe Analytics]擴充功能。
1. 擴充功能在生產環境中停用後，您就可以完全解除安裝。 選取擴充功能，選取右側的三個點功能表，然後選取&#x200B;**[!UICONTROL 解除安裝]**。
1. 按照上面的相同發佈工作流程，將這些變更發佈到生產環境。

+++

此時，您的Analytics實作已完全上線Web SDK，並已為未來移至Customer Journey Analytics做好充分準備。
