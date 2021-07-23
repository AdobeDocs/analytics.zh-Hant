---
title: 擷取內部搜尋詞
description: 使用自訂變數來擷取內部搜尋詞。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# 擷取內部搜尋詞

內部搜尋報表是許多組織不可或缺的一部分，並非Adobe Analytics的現成維度。 不過，只要將實作工作減到最少，就可輕鬆擷取內部搜尋詞報告。

## 先決條件

[驗證開發實施並發佈至生產環境](../launch/validate-publish-prod.md):本頁假設您具備基本的運作實作，並在Adobe Analytics除錯程式中查看Adobe影像要求。

## 建立eVar以容納內部搜索

請依照[轉換變數admin](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)建立專用於內部搜尋的新eVar。 為eVar提供易於識別的名稱（例如「內部搜尋詞」），並將新eVar記錄在貴組織的[解決方案設計檔案](../prepare/solution-design.md)中。

## 確定內部搜索關鍵字

大部分的內部搜尋都使用查詢字串來傳遞頁面之間的關鍵字資料。 使用您網站的內部搜尋，並在搜尋結果頁面上記下URL:

`https://example.com/search.html?q=kittens`

如果您網站的內部搜尋未使用URL，請在其他位置（例如資料層或Cookie）中尋找搜尋詞。 如果您不確定要在何處尋找內部搜尋詞，請與您的網站開發團隊合作。

## 將查詢字串參數指派給資料元素

請遵循[將資料層物件對應至資料元素](../launch/layer-to-elements.md)。 選取&#x200B;**[!UICONTROL 資料元素類型]**&#x200B;時，請選取&#x200B;**[!UICONTROL 查詢字串參數]**，而非&#x200B;**[!UICONTROL JavaScript變數]**。 將所需的查詢字串參數（通常`q`）放入文字欄位中。

## 將資料元素對應至eVar

請依照[將資料元素對應至Analytics變數](../launch/elements-to-variable.md)操作。 請務必選取與您在報表套裝設定中建立的eVar相同。

## 開始部署標籤

請依照[將Analytics實施部署至開發環境](../launch/deploy-dev.md)操作。 一旦您確認其在開發環境中運作正常，即可[驗證開發實作並發佈至生產環境](../launch/validate-publish-prod.md)。

## 工作區中的報表

請給您的實作一些時間來收集資料，然後您就可以開始使用Analysis Workspace中的維度。

1. 使用您的 AdobeID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您未自動登入Adobe Analytics，請按一下右上方的9格線圖示，然後選取&#x200B;**[!UICONTROL Analytics]**。
3. 按一下&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後建立新專案。
4. 找出在「Dimension」下建立的eVar名稱，並將其拖曳至工作區畫布。
