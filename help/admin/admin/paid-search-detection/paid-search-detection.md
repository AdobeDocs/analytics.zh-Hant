---
description: '「付費搜尋偵測」可區分「搜尋引擎」與「搜尋關鍵字」報表中的付費與免費搜尋。 '
title: 付費搜尋偵測
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 71%

---

# 付費搜尋偵測

[!UICONTROL 「付費搜尋偵測」可區分「搜尋引擎」與「搜尋關鍵字」報表中的付費與免費搜尋。]您可以指定您在其中使用付費廣告的搜尋引擎，並指定可在付費廣告瀏覽的 URL 中找到的字元字串。

## 設定選項 {#section_0C2CFA0AF77B47098BE37CB024665D0D}

下表說明可供您[設定付費搜尋偵測](/help/admin/admin/paid-search-detection/t-paid-search-detection.md)的欄位和選項。

| 選項 | 說明 |
| --- | --- |
| [!UICONTROL 搜尋引擎] | 從下拉式清單中選取搜尋引擎。若您對不同的搜尋引擎使用不同的查詢字串參數，您可以指定引擎。通常， `Any` 足夠了。 |
| [!UICONTROL 查詢字串] | 為與查詢字串參數的任何部分（即「？」之後的url的一部分）區分大小寫的匹配指定字串。 <br>**注釋**: [!UICONTROL 付費搜索檢測] 區分大小寫。 例如，將「PID」指定為查詢字串參數的規則將與「pid」不匹配。 若您的組織混用大小寫，請將各個確切值設為個別規則，以便能擷取到所有需要的查詢字串參數。 |
