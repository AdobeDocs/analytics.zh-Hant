---
description: Adobe Analytics 支援單層級與多層級分類模式。分類階層可以讓您將分類套用到分類。
title: 子分類
feature: Classifications
exl-id: 3d22a8c0-743d-47f3-ba15-aaef1ebd4dff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 97%

---

# 子分類

{{classification-importer-deprecation}}

Adobe Analytics 支援單層級與多層級分類模式。分類階層可以讓您將分類套用到分類。

>[!NOTE]
>
>子分類表示在分類中建立分類的能力。 然而，它與用來建立[!UICONTROL 階層]報告的[!UICONTROL 分類階層]不同。如需分類階層的詳細資訊，請參閱[分類階層](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)。

例如：

![](../assets/single-level-popup-C.png)

此模式中的每個分類各自獨立，並且與所選報告變數的新子報告相對應。此外，每個分類都是由資料檔案中的一個資料欄所組成，其分類名稱即是欄標題。例如：

| 代碼 | 屬性 1 | 屬性 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

如需資料檔案的詳細資訊，請參閱「[分類資料檔案](/help/components/classifications/importer/c-saint-data-files.md)」。

多級分類是由父分類和子分類所組成。例如：

![](../assets/Multi-Level-Class-popup.png)

**父分類：**&#x200B;父分類是指任何具有相關聯子分類的分類。任何分類都可以是父分類和子分類。與最上層父分類對應的是單級分類。

**子分類：**&#x200B;子分類是指任何具有其他作為父分類 (而非變數) 的分類。子分類能提供其他有關父分類的資訊。例如，[!UICONTROL 行銷活動]分類可能會有一個行銷活動擁有人子分類。[!UICONTROL 數值]分類還可以作為分類報告中的量度。

不論是父分類或子分類，每個分類都是由資料檔案中的一個資料欄所組成。子分類的欄標題使用以下命名格式：

`<parent_name>^<child_name>`

如需資料檔案格式的詳細資訊，請參閱[分類資料檔案](/help/components/classifications/importer/c-saint-data-files.md)。

例如：

| 代碼 | 屬性 1 | 屬性 1^屬性 1-1 | 屬性 1^屬性 1-2 | 屬性 2 |
|---|---|---|---|---|
| 123 | ABC | 綠色 | 小 | A12B |
| 456 | DEF | 紅色 | 大 | C3D4 |

儘管多級分類的檔案範本更加複雜，但其優勢在於，可以將獨立層級上傳為獨立檔案。該方法可將隨時間變化和不隨時間變化的資料分入不同的分類，從而減少需定期 (每天、每週等) 上傳的資料量。

>[!NOTE]
>
>若資料檔案中的[!UICONTROL 代碼]欄空白，Adobe 會自動為每個資料列產生唯一的代碼。為了避免在上傳含第二級或更高級分類資料的資料檔案時造成檔案毀損，請在「[!UICONTROL 代碼]」欄中的每一行填入星號 (*)。

## 範例

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

>[!NOTE]
>
>產品分類資料限於直接與產品相關的資料屬性。資料不受產品在網站上分類或銷售方式的限制。銷售類別、網站瀏覽節點或銷售項目等資料元素並不是產品分類資料。反之，這些元素是在報告轉換變數中擷取的。

上傳這個產品分類的資料檔案時，您可以使用單一的檔案或多個檔案來上傳分類資料 (請參閱下面)。將檔案 1 裡的顏色代碼和檔案 2 裡的顏色名稱分開，則只有在建立新的顏色代碼時，才需要上傳顏色名稱資料 (可能僅有幾列)。這可以免除較常更新之檔案 1 裡的顏色名稱 (CODE^COLOR) 欄位，並減少檔案大小和產生資料檔案時的複雜性。

### 產品分類 - 單一檔案 {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| 代碼 | 產品名稱 | 產品詳情 | 性別 | 大小 | 代碼 | CODE^COLOR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | 短袖男性 Polo 衫 (M,01) | M | M | 01 | 石板褐 |
| 410390014 | Polo-SS | 短袖男性 Polo 衫 (L,03) | M | L | 03 | 冷色 |
| 410390015 | Polo-LS | 長袖女性 Polo 衫 (S,23) | F | S | 23 | 青色 |

### 產品分類 - 多重檔案 (檔案 1) {#section_A99F7D0F145540069BA4EEC0597FF13F}

| 代碼 | 產品名稱 | 產品詳情 | 性別 | 大小 | 代碼 |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | 短袖男性 Polo 衫 (M,01) | M | M | 01 |
| 410390014 | Polo-SS | 短袖男性 Polo 衫 (L,03) | M | L | 03 |
| 410390015 | Polo-LS | 長袖女性 Polo 衫 (S,23) | F | S | 23 |

### 產品分類 - 多重檔案 (檔案 2) {#section_19ED95C33B174A9687E81714568D56A3}

| 代碼 | 代碼 | CODE^COLOR |
|---|---|---|
| &#42; | 01 | 石板褐 |
| &#42; | 03 | 冷色 |
| &#42; | 23 | 青色 |
