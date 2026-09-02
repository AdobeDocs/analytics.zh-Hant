---
description: 說明如何刪除或移除分類資料的步驟。
title: 刪除分類資料
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
TQID: https://experienceleague.adobe.com/NZhXTXSwpA-E-6JaGRInMf3TMwHp5A1uMSjaAU1whts
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 85%

---

# 刪除分類資料

{{classification-importer-deprecation}}

在分類資料完成上傳後，有時候您必須移除該資料。 視您要移除的項目而定，請使用 `~empty~` 或 `~deletekey~`。

## 移除分類資料的步驟

移除分類資料時，會上傳位於相關儲存格中包含 `~empty~` 或 `~deletekey~` 的分類檔案。

1. 按一下&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 分類匯入工具」]**。
1. 按一下&#x200B;**[!UICONTROL 「瀏覽器匯出」]**。
1. 選取您要移除其中之分類資料的報告套裝和資料集。
1. 調整任何可選的設定，以篩選您在尋找的特定資料，然後按一下&#x200B;**[!UICONTROL 「匯出檔案」]**。
1. 下載檔案後，請開啟檔案並以 `~empty~` 或 `~deletekey~` 取代任何分類值。
1. 將檔案儲存為以定位點分隔的文字檔案。
1. 按一下&#x200B;**[!UICONTROL 匯入檔案]**，然後將儲存的分類檔案上傳回 Adobe Analytics。

## 刪除個別分類值

有多個分類可同屬於相同變數。 舉例來說，您可以有 2 種不同的 eVar1 分類。 如果您只想移除單一分類值，請以 `~empty~` 取代該分類值。 例如：

| 庫存 SKU (eVar8) | 庫存名稱 | 庫存類別 |
| --- | --- | --- |
| 857467 | V 領毛衣 | 女裝 |
| 948203 | 腳踝鏈 | 珠寶 |
| 174391 | 白色燈芯絨褲 | `~empty~` |

在庫存類別分類下使用 `~empty~`，庫存名稱分類的資料仍會保留。 `~empty~` 值只會刪除該儲存格的分類資料。

## 刪除整個分類列

在任何欄中使用 `~deletekey~` 可刪除整個分類列。 例如：

| 庫存 SKU (eVar8) | 庫存名稱 | 庫存類別 |
| --- | --- | --- |
| 857467 | V 領毛衣 | 女裝 |
| 948203 | 腳踝鏈 | 珠寶 |
| 174391 | 白色燈芯絨褲 | `~deletekey~` |

在庫存類別分類下使用 `~deletekey~` 會刪除關鍵值 `174391` 的所有分類資料， 就像資料列從未經過分類一樣。

## 缺陷與訣竅

* 使用 `~deletekey~` 時，分類檔案中的每列只需使用一次。
* `~empty~` 和 `~deletekey~` 必須為&#x200B;*完全*&#x200B;比對。 不允許使用空格或大寫字母。
* 您無法刪除索引鍵欄中的值，這些值會直接傳遞至變數，且成為永久值。
* 如果您移除具有子分類的分類值，則也會移除這些子分類。 沒有索引鍵值就無法存在分類，而且子分類的父級是其索引鍵值。
* 可以移除子分類資料，同時將其父分類保持完整。
