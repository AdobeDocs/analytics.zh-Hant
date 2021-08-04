---
description: '「付費搜尋偵測」可區分「搜尋引擎」與「搜尋關鍵字」報表中的付費與免費搜尋。 '
title: 付費搜尋偵測
feature: 管理工具
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: b88f9d373d715b295dc4982a6ee05bd982f5bae7
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 72%

---

# 付費搜尋偵測

[!UICONTROL 「付費搜尋偵測」可區分「搜尋引擎」與「搜尋關鍵字」報表中的付費與免費搜尋。]您可以指定您在其中使用付費廣告的搜尋引擎，並指定可在付費廣告瀏覽的 URL 中找到的字元字串。

## 設定選項 {#section_0C2CFA0AF77B47098BE37CB024665D0D}

下表說明可供您[設定付費搜尋偵測](/help/admin/admin/paid-search-detection/t-paid-search-detection.md)的欄位和選項。

| 選項 | 說明 |
| --- | --- |
| [!UICONTROL 搜尋引擎] | 從下拉式清單中選取搜尋引擎。若您對不同的搜尋引擎使用不同的查詢字串參數，您可以指定引擎。值`Any`通常足夠。 |
| [!UICONTROL 查詢字串] | 指定字串，以區分大小寫，並搭配查詢字串參數的任何部分（在「？」之後是url的一部分）。 <br>**注意**: [!UICONTROL 付費搜尋偵] 測會區分大小寫。例如，將「PID」指定為查詢字串參數的規則將不符合「pid」。 若您的組織混用大小寫，請將各個確切值設為個別規則，以便能擷取到所有需要的查詢字串參數。 |
