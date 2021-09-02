---
title: 擷取內部搜尋字詞
description: 使用自訂變數來擷取內部搜尋字詞。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# 擷取內部搜尋字詞

內部搜尋報告是許多組織不可或缺的功能，但它並不是 Adobe Analytics 提供的現成維度。 然而，只需最少的實作工作，就可以輕鬆擷取內部搜尋字詞報告。

## 先決條件

[驗證開發實作並發佈至生產環境](../launch/validate-publish-prod.md)：此頁面假設您有基本的有效實作，而且您在 Adobe Debugger 中看到 Adobe Analytics 影像要求。

## 建立 eVar 來因應內部搜尋

依照「[轉換變數管理員](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)」中的指示來建立內部搜尋專屬的全新 eVar。 為 eVar 提供可輕鬆辨識的名稱 (例如「Internal search term」)，並在貴組織的[解決方案設計文件](../prepare/solution-design.md)中記錄新的 eVar。

## 決定內部搜尋關鍵字

大多數內部搜尋都會使用查詢字串來傳遞頁面之間的關鍵字資料。 請使用您網站的內部搜尋，並記下搜尋結果頁面上的 URL：

`https://example.com/search.html?q=kittens`

如果您網站的內部搜尋不使用 URL，請在其他位置尋找搜尋字詞，例如資料層或 Cookie。 如果您不確定該從哪裡尋找內部搜尋字詞，請洽詢您的網站開發團隊。

## 為資料元素指派查詢字串參數

請依照「[將資料層物件對應至資料元素](../launch/layer-to-elements.md)」中的指示進行。 在設定「**[!UICONTROL 資料元素類型]**」時，請選取「**[!UICONTROL 查詢字串參數]**」，而不是「**[!UICONTROL JavaScript 變數]**」。 將所需的查詢字串參數 (通常是 `q`) 放入文字欄位中。

## 將資料元素對應至 eVar

請依照「[將資料元素對應至 Analytics 變數](../launch/elements-to-variable.md)」中的指示進行。 務必選取您在報表套裝設定中所建立的相同 eVar。

## 開始部署標記

請依照「[將 Analytics 實作部署至開發環境](../launch/deploy-dev.md)」中的指示進行。 在您確認它可在您的開發環境中使用後，您可以[驗證開發實作並發佈至生產環境](../launch/validate-publish-prod.md)。

## Workspace 中的報告

讓您的實作有一些時間可以收集資料，然後您可以開始在 Analysis Workspace 中使用維度。

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您未自動登入 Adobe Analytics，請按一下右上方的 9 格線圖示，然後選取「**[!UICONTROL Analytics]**」。
3. 按一下「**[!UICONTROL Workspace]**」索引標籤，然後建立新專案。
4. 找出您在「維度」底下建立的 eVar 名稱，然後將它拖曳到 Workspace 畫布。
