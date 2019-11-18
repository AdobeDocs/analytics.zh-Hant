---
description: 說明如何刪除或移除分類資料的步驟。
solution: Analytics
subtopic: Classifications
title: 刪除分類資料
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: e526a38415135440f666ecadd73c34920c0c4c1d

---


# 刪除分類資料

有時候，在上傳分類資料後，必須移除該資料。 使用 `~empty~` 或 `~deletekey~`，視您要移除的項目而定。

## 移除分類資料的步驟

移除分類資料時，會上傳包含或位於 `~empty~` 適當儲 `~deletekey~` 存格中的分類檔案。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. 選取您要移除其中之分類資料的報表套裝和資料集。
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. 下載檔案後，請開啟檔案並以或取代任何分 `~empty~` 類值 `~deletekey~`。
1. 將檔案儲存為以Tab分隔的文字檔案。
1. 按一 **[!UICONTROL 下「匯入檔案]**」，然後將儲存的分類檔案上傳回Adobe Analytics。

## 刪除個別分類值

多個分類可以屬於相同的變數。 例如，您可以有2種不同的eVar1分類。 如果您只想移除單一分類值，請將分類值取代為 `~empty~`。 例如:

| 庫存SKU(eVar8) | 庫存名稱 | 庫存類別 |
| --- | --- | --- |
| 857467 | V領毛衣 | 女裝 |
| 948203 | 踝鏈 | 珠寶 |
| 174391 | 白燈芯絨褲 | `~empty~` |

在「 `~empty~` 庫存類別」分類下使用仍會保留「庫存名稱」分類的資料。 此值 `~empty~` 只會刪除該儲存格的分類資料。

## 刪除整個分類列

在任 `~deletekey~` 何欄中使用可刪除整個分類列。 例如:

| 庫存SKU(eVar8) | 庫存名稱 | 庫存類別 |
| --- | --- | --- |
| 857467 | V領毛衣 | 女裝 |
| 948203 | 踝鏈 | 珠寶 |
| 174391 | 白燈芯絨褲 | `~deletekey~` |

在「 `~deletekey~` 庫存類別」分類下使用會刪除關鍵值的所有分類資料 `174391`。 這就像從未對行分類一樣。

## 陷阱與秘訣

* 如果使 `~deletekey~`用，分類檔案中每列只需要一列。
* `~empty~` 且必 `~deletekey~` 須完全 *相符* 。 不允許空格或大寫。
* 您無法刪除索引鍵欄中的值，這些值會直接傳遞至變數且為永久值。
* 如果您要移除具有子分類的分類值，這些子分類也會被移除。 分類不能沒有索引鍵值，而子分類的父級是其索引鍵值。
* 可以移除子分類資料，但保留其父級分類的完整。
