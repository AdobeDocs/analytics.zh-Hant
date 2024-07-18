---
title: 將資料層物件對應至資料元素
description: 設定標記以從資料層讀取。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 94%

---

# 將資料層物件對應至資料元素

當貴組織在網站上建立並實作資料層後，您就可以將資料層物件對應至標記中的資料元素。

## 先決條件

[建立資料層](../prepare/data-layer.md)：請確定您的網站上有資料層。雖然技術上，您可以對應任何 JavaScript 物件或直接從頁面上消除 CSS 元素，但 Adobe 建議您最後再採取此作法。如果您的網站版面有所變更，標記中使用的 CSS 選擇器會停止運作，造成資料遺失。

## 使用標記建立資料元素

[資料元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hant)是 Adobe Experience Platform 資料彙集中的元件，可在該工具中使用。您可以使用資料元素，在 Adobe Analytics 擴充功能中指派變數值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下&#x200B;**[!UICONTROL 「資料元素」]**&#x200B;標記，然後按一下&#x200B;**[!UICONTROL 「新增資料元素」]**。

   ![建立資料元素](assets/createelement.png)

1. 輸入您的資料元素名稱。可為符合您要追蹤之資料層中 JavaScript 變數的簡單標記。
1. 在&#x200B;**[!UICONTROL 擴充功能]**&#x200B;下拉式清單下，選取&#x200B;**[!UICONTROL 核心]**。
1. 在&#x200B;**[!UICONTROL 資料元素型別]**&#x200B;下拉式清單下，選取&#x200B;**[!UICONTROL JavaScript變數]**。 右側會出現一個文字欄位，可讓您輸入 JavaScript 變數以對應至此資料元素。
1. 輸入所需的 Javascript 變數，通常在您的資料層中。例如，如果貴組織的資料層與 Adobe 的建議作法幾乎相符，則值可能是 `digitalData.page.pageInfo.pageName`。您可以使用瀏覽器的主控台，驗證 JavaScript 變數語法和值。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 後續步驟

[將資料元素對應至 Analytics 變數](elements-to-variable.md)：將資料元素指派給 Analytics 變數，以便在 Analysis Workspace 中將這些元素當成維度使用。
