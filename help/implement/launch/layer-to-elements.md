---
title: 將資料層物件對應至資料元素
description: 設定標記以從資料層讀取。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# 將資料層物件對應至資料元素

當貴組織在網站上建立並實作資料層後，您就可以將資料層物件對應至標記中的資料元素。

## 先決條件

[建立資料層](../prepare/data-layer.md)：請確定您的網站上有資料層。 雖然技術上，您可以對應任何 JavaScript 物件或直接從頁面刮取 CSS 元素，但 Adobe 建議您最後再採取此作法。 如果您的網站版面有所變更，標記中使用的 CSS 選擇器會停止運作，造成資料遺失。

## 使用標記建立資料元素

[資料元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hant)是 Adobe Experience Platform 資料彙集中的元件，可在該工具中使用。 您可以使用資料元素，在 Adobe Analytics 擴充功能中指派變數值。

下列步驟使用[Adobe使用者端資料層擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/client-data-layer/overview)，此擴充功能必須安裝在您的標籤屬性中。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 選取所需的標籤屬性。
1. 選取&#x200B;**[!UICONTROL 資料元素]**&#x200B;索引標籤，然後選取&#x200B;**[!UICONTROL 新增資料元素]**。

   ![建立資料元素](assets/createelement.png)

1. 輸入資料元素的名稱，例如`Page name`。
1. 在&#x200B;**[!UICONTROL 擴充功能]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Adobe使用者端資料層]**。
1. 在&#x200B;**[!UICONTROL 資料元素型別]**&#x200B;下拉式清單下，選取&#x200B;**[!UICONTROL 資料層計算狀態]**。
1. 在&#x200B;**[!UICONTROL 傳回值]**&#x200B;下，選取&#x200B;**[!UICONTROL 特定路徑]**，然後輸入資料層中值的路徑，例如`page.name`。 若要驗證路徑，請在瀏覽器的主控台中執行`adobeDataLayer.getState("page.name")`。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

在擴充功能的&#x200B;**[!UICONTROL 資料層推送]**&#x200B;事件觸發的規則中使用這些資料元素，讓資料層已載入並包含推送的資料。 請參閱[資料元素型別](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state)。

### 物件資料層 {#object-based}

如果您的資料層是JavaScript物件（例如CEDDL `digitalData`物件），請改用來自&#x200B;**[!UICONTROL 核心]**&#x200B;擴充功能的&#x200B;**[!UICONTROL JavaScript變數]**&#x200B;資料元素型別。 輸入值的路徑，例如`digitalData.page.pageInfo.pageName`。 此資料元素型別無法讀取Adobe Client Data Layer，其資料以計算狀態而非物件屬性儲存。

## 後續步驟

[將資料元素對應至 Analytics 變數](elements-to-variable.md)：將資料元素指派給 Analytics 變數，以便在 Analysis Workspace 中將這些元素當成維度使用。
