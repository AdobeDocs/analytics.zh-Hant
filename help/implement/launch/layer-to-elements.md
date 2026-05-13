---
title: 將資料層物件對應至資料元素
description: 設定標記以從資料層讀取。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 93%

---

# 將資料層物件對應至資料元素

當貴組織在網站上建立並實作資料層後，您就可以將資料層物件對應至標記中的資料元素。

## 先決條件

[建立資料層](../prepare/data-layer.md)：請確定您的網站上有資料層。 雖然技術上，您可以對應任何 JavaScript 物件或直接從頁面上消除 CSS 元素，但 Adobe 建議您最後再採取此作法。 如果您的網站版面有所變更，標記中使用的 CSS 選擇器會停止運作，造成資料遺失。

## 使用標記建立資料元素

[資料元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hant)是 Adobe Experience Platform 資料彙集中的元件，可在該工具中使用。 您可以使用資料元素，在 Adobe Analytics 擴充功能中指派變數值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下&#x200B;**[!UICONTROL 「資料元素」]**&#x200B;標記，然後按一下&#x200B;**[!UICONTROL 「新增資料元素」]**。

   ![建立資料元素](assets/createelement.png)

1. 輸入您的資料元素名稱。 可為符合您要追蹤之資料層中 JavaScript 變數的簡單標籤。
1. 在&#x200B;**[!UICONTROL 擴充功能]**&#x200B;下拉式清單下，選取&#x200B;**[!UICONTROL 核心]**。
1. 在&#x200B;**[!UICONTROL 資料元素型別]**&#x200B;下拉式清單下，選取&#x200B;**[!UICONTROL JavaScript變數]**。 右側會出現一個文字欄位，可讓您輸入 JavaScript 變數以對應至此資料元素。
1. 輸入所需的 Javascript 變數，通常在您的資料層中。 例如，如果貴組織的資料層與 Adobe 的建議作法幾乎相符，則值可能是 `digitalData.page.pageInfo.pageName`。 您可以使用瀏覽器的主控台，驗證 JavaScript 變數語法和值。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 後續步驟

[將資料元素對應至 Analytics 變數](elements-to-variable.md)：將資料元素指派給 Analytics 變數，以便在 Analysis Workspace 中將這些元素當成維度使用。
