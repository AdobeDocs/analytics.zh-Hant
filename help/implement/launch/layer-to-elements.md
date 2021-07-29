---
title: 將資料層物件對應至資料元素
description: 設定要從資料層讀取的標籤。
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 57%

---

# 將資料層物件對應至資料元素

在您的組織建立並實作網站上的資料層後，您就可以將資料層物件對應至標籤內的資料元素。

>[!NOTE]
>Adobe Experience Platform Launch已重新命名為Experience Platform中的資料收集技術套件。 因此，產品檔案中已推出數個術語變更。 有關術語更改的綜合參考，請參閱以下[document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

## 先決條件

[建立資料層](../prepare/data-layer.md)：請確定您的網站上有資料層。雖然技術上，您可以對應任何 JavaScript 物件或直接從頁面上消除 CSS 元素，但 Adobe 建議您最後再採取此作法。如果您的網站版面有所變更，標籤中使用的CSS選取器將停止運作，造成資料遺失。

## 使用標籤建立資料元素

[資](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) 料元素是資料收集UI中的元件，可在整個工具中使用。您可以使用資料元素，在 Adobe Analytics 擴充功能中指派變數值。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下&#x200B;**[!UICONTROL 「資料元素」]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL 「新增資料元素」]**。

   ![建立資料元素](assets/createelement.png)

1. 輸入您的資料元素名稱。可為符合您要追蹤之資料層中 JavaScript 變數的簡單標籤。
1. 在&#x200B;**[!UICONTROL 「擴充功能」]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 「核心」]**。
1. 在&#x200B;**[!UICONTROL 「資料元素類型」]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 「JavaScript 變數」]**。右側會出現一個文字欄位，可讓您輸入 JavaScript 變數以對應至此資料元素。
1. 輸入所需的 Javascript 變數，通常在您的資料層中。例如，如果貴組織的資料層與 Adobe 的建議作法幾乎相符，則值可能是 `digitalData.page.pageInfo.pageName`。您可以使用瀏覽器的主控台，驗證 JavaScript 變數語法和值。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 後續步驟

[將資料元素對應至 Analytics 變數](elements-to-variable.md)：將資料元素指派給 Analytics 變數，以便在 Analysis Workspace 中將這些元素當成維度使用。
