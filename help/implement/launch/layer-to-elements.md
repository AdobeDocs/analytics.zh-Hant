---
title: 將資料層物件對應至資料元素
description: 設定「啟動」以從資料層讀取。
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# 將資料層物件對應至資料元素

在您的組織建立並實作網站上的資料層後，您就可以將資料層物件對應至Launch中的資料元素。

## 必備條件

[建立資料層](../prepare/data-layer.md):請確定您的網站上有資料層。 雖然從技術上講，您可以直接對應任何JavaScript物件或從頁面上刮取CSS元素，但Adobe建議您最後採取此作法。 如果您的網站版面變更，Launch中使用的CSS選擇器會停止運作，造成資料遺失。

## 使用Adobe Experience Platform Launch建立資料元素

[資料元素](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) 是Launch中的元件，您可在工具間使用。 您可以使用資料元素，在Adobe Analytics擴充功能中指派變數值。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下所要的「啟動」屬性。
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![建立資料元素](assets/createelement.png)

1. 輸入您的資料元素名稱。 它可以是與您要追蹤之資料層中的JavaScript變數相對應的簡單標籤。
1. 在下拉式清 [!UICONTROL Extension] 單下，選取 [!UICONTROL Core]。
1. 在下拉式清 [!UICONTROL Data Element Type] 單下，選取 [!UICONTROL JavaScript Variable]。 右側會出現一個文字欄位，可讓您輸入JavaScript變數以對應至此資料元素。
1. 輸入所要的Javascript變數，通常在您的資料層中。 例如，如果貴組織的資料層與Adobe的建議做法緊密相符，則值可能是 `digitalData.page.pageInfo.pageName`。 您可以使用瀏覽器的主控台來驗證JavaScript變數語法和值。
1. 按一下 [!UICONTROL Save].

## 後續步驟

[將資料元素對應至Analytics變數](elements-to-variable.md):將資料元素指派給Analytics變數，以便在分析工作區中將它們當做維度使用。
