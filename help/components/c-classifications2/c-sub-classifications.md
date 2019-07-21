---
description: Adobe Analytics支援單級和多級分類模型。分類階層可以讓您將分類套用到分類。
seo-description: Adobe Analytics支援單級和多級分類模型。分類階層可以讓您將分類套用到分類。
seo-title: 關於子分類
solution: Analytics
subtopic: '分類   '
title: 關於子分類
topic: 管理工具
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 關於子分類

Adobe Analytics支援單級和多級分類模型。分類階層可以讓您將分類套用到分類。

>[!NOTE]
>
>子分類指建立分類分類的能力。然而，它與用來建立[!UICONTROL 階層]報告的[!UICONTROL 分類階層]不同。For more information about Classification hierarchies, see [Classification Hierarchies](classification-hierarchies.md).

<!-- 

<p>Removed sub-classifications in rule builder. Preserve subclass files in project for future reference. </p>

 -->

<!-- 

c_single-level_classifications.xml

 -->

例如:

![](assets/single-level-popup-C.png)

此模式中的每個分類各自獨立，並且與所選報告變數的新子報告相對應。此外，每個分類都是由資料檔案中的一個資料欄所組成，其分類名稱即是欄標題。例如:

| 代碼 | PROPERTY 1 | PROPERTY 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

如需資料檔案的詳細資訊，請參閱[分類資料檔案](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735)。

<!-- 

c_multiple-level_classifications.xml

 -->

多級分類是由父分類和子分類所組成。例如:

![](assets/Multi-Level-Class-popup.png)

**父分類:**&#x200B;父分類是指任何具有相關聯子分類的分類。任何分類都可以是父分類和子分類。與最上層父分類對應的是單級分類 (請參閱 [單級分類](../../components/c-classifications2/c-sub-classifications.md#concept_6B909B54221F4A9BAEA8E30594F06C49)).

**子分類:**&#x200B;子分類是指任何具有其他作為父分類 (而非變數) 的分類。子分類能提供其他有關父分類的資訊。例如，[!UICONTROL 促銷活動]分類可能會有一個促銷活動擁有人子分類。[!UICONTROL 數值]分類還可以作為分類報告中的量度。

不論是父分類或子分類，每個分類都是由資料檔案中的一個資料欄所組成。子分類的欄標題使用以下命名格式:

`<parent_name>^<child_name>`

For more information about the data file format, see [Classification Data Files](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

例如:

| 代碼 | PROPERTY 1 | Property&amp; amp；Hat；屬性1-1 | Property&amp; amp；Hat；Property1-2 | 屬性 2 |
|---|---|---|---|---|
| 123 | ABC | 綠色 | 小 | A12B |
| 456 | DEF | 紅色 | 大 | C3D4 |

儘管多級分類的檔案範本更加複雜，但其優勢在於，可以將獨立層級上傳為獨立檔案。該方法可將隨時間變化和不隨時間變化的資料分入不同的分類，從而減少需定期 (每天、每週等) 上傳的資料量。

>[!NOTE]
>
>If the [!UICONTROL Key] column in a data file is blank, Adobe automatically generates unique keys for each data row. 為了避免在上傳含第二級或更高級分類資料的資料檔案時造成檔案毀損，請在「[!UICONTROL 代碼]」欄中的每一行填入星號 (*)。

如需疑難排解說明，請參閱「[常見的分類上傳問題](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-common-saint-upload-issues)」。

<!-- 

c_classifications_example.xml

 -->

![](assets/sample-product-classifications.png)

>[!NOTE]
產品分類資料僅限於與產品直接相關的資料屬性。資料不受產品在網站上分類或銷售方式的限制。銷售類別、網站瀏覽節點或銷售項目等資料元素並不是產品分類資料。反之，這些元素是在報告轉換變數中擷取的。

上傳這個產品分類的資料檔案時，您可以使用單一的檔案或多個檔案來上傳分類資料 (請參閱下面)。將檔案 1 裡的顏色代碼和檔案 2 裡的顏色名稱分開，則只有在建立新的顏色代碼時，才需要上傳顏色名稱資料 (可能僅有幾列)。這可以消除顏色名稱(Code&amp; amp；Hat；COLOR)欄位來自頻繁更新的檔案，並減少檔案大小和複雜性，產生資料檔案。

## 產品分類 - 單一檔案 {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| 代碼 | 產品名稱 | 產品詳情 | 性別 | 大小 | 代碼 | Code&amp; amp；Hat；顏色 |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | 短袖男性 Polo 衫 (M,01) | M | M | 01 | 石板褐 |
| 410390014 | Polo-SS | 短袖男性 Polo 衫 (L,03) | M | L | 03 | 冷色 |
| 410390015 | Polo-LS | 長袖女性 Polo 衫 (S,23) | F | S | 23 | 青色 |

## 產品分類 - 多重檔案 (檔案 1) {#section_A99F7D0F145540069BA4EEC0597FF13F}

| 代碼 | 產品名稱 | 產品詳情 | 性別 | 大小 | 代碼 |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | 短袖男性 Polo 衫 (M,01) | M | M | 01 |
| 410390014 | Polo-SS | 短袖男性 Polo 衫 (L,03) | M | L | 03 |
| 410390015 | Polo-LS | 長袖女性 Polo 衫 (S,23) | F | S | 23 |

## 產品分類 - 多重檔案 (檔案 2) {#section_19ED95C33B174A9687E81714568D56A3}

| 代碼 | 代碼 | Code&amp; amp；Hat；顏色 |
|---|---|---|
| * | 01 | 石板褐 |
| * | 03 | 冷色 |
| * | 23 | 青色 |
