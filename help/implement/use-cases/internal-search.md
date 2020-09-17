---
title: 擷取內部搜尋詞
description: 使用自訂變數來擷取內部搜尋詞。
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# 擷取內部搜尋詞

內部搜尋報告是許多組織不可或缺的一部分，而且不是Adobe Analytics的現成可用維度。 不過，只要實作的力度不大，內部搜尋詞報告就可輕鬆擷取。

## 必要條件

[驗證開發實作並發佈至生產環境](../launch/validate-publish-prod.md):本頁假設您有基本的工作實作，並在Adobe除錯程式中查看Adobe Analytics影像要求。

## 建立eVar以容納內部搜尋

依循 [轉換變數管理](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) ，建立專用於內部搜尋的新eVar。 為eVar提供可輕易辨識的名稱（例如「內部搜尋詞」），並在您組織的解決方案設計檔案中記錄新 [的eVar](../prepare/solution-design.md)。

## 確定內部搜尋關鍵字

大部分的內部搜尋都使用查詢字串在頁面之間傳遞關鍵字資料。 使用您網站的內部搜尋，並記下搜尋結果頁面上的URL:

`https://example.com/search.html?q=kittens`

如果您網站的內部搜尋不使用URL，請在其他位置尋找搜尋詞，例如資料層或Cookie。 如果您不確定要在何處尋找內部搜尋詞，請與網站開發團隊合作。

## 將查詢字串參數指派給資料元素

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). 選取「資料 **[!UICONTROL 元素類型」時]**，請選取「 **[!UICONTROL 查詢字串參數]** 」，而非 **[!UICONTROL JavaScript變數]**。 將所需的查詢字串參數(通 `q`常)放入文字欄位。

## 將資料元素對應至eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). 請確定您選取的eVar與您在報表套裝設定中建立的eVar相同。

## 啟動部署程式

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). 一旦您確認它在您的開發環境中運作，您就可以 [驗證開發實作並發佈至生產環境](../launch/validate-publish-prod.md)。

## 工作區中的報表功能

為實作提供一些時間來收集資料，然後您就可以開始在分析工作區中使用維度。

1. 使用您的 AdobeID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您未自動登入Adobe Analytics，請按一下右上角的9格線圖示，然後選取「 **[!UICONTROL Analytics」]**。
3. 按一下「 **[!UICONTROL 工作區]** 」標籤，然後建立新專案。
4. 找出您在「維度」下建立的eVar名稱，並拖曳至工作區畫布。
