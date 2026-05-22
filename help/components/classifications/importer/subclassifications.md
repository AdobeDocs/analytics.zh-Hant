---
description: Adobe Analytics 支援單層級與多層級分類模式。 分類階層可以讓您將分類套用到分類。
title: 子分類
feature: Classifications
exl-id: 3d22a8c0-743d-47f3-ba15-aaef1ebd4dff
TQID: https://experienceleague.adobe.com/Gla7xVOKKBnfRJu06NOzNsN6IsRr741fDRrd-z8Dy-A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 682
ht-degree: 43%

---

# 子分類

{{classification-importer-deprecation}}

Adobe Analytics 支援單層級與多層級分類模式。 分類階層可以讓您將分類套用到分類。

>[!NOTE]
>
>子分類表示在分類中建立分類的能力。 然而，它與用來建立[!UICONTROL 階層]報告的[!UICONTROL 分類階層]不同。 如需分類階層的詳細資訊，請參閱[分類階層](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)。

例如：

![](../assets/single-level-popup-C.png)

此模型中的每個分類都是獨立的，並與所選報告變數的新子報告相對應。 此外，每個分類構成資料檔案中的一個資料欄，以分類名稱作為欄標題。 例如：

| 索引鍵 | 屬性 1 | 屬性 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

如需資料檔案的詳細資訊，請參閱「[分類資料檔案](/help/components/classifications/importer/c-saint-data-files.md)」。

多級分類是由父分類和子分類所組成。 例如：

![](../assets/Multi-Level-Class-popup.png)

**父分類：**&#x200B;父分類是指任何具有相關聯子分類的分類。 任何分類都可以是父分類和子分類。 與最上層父分類對應的是單級分類。

**子分類：**&#x200B;子分類是指任何具有其他作為父分類 (而非變數) 的分類。 子分類提供其父分類的其他相關資訊。 例如，[!UICONTROL 行銷活動]分類可能會有一個行銷活動擁有人子分類。 [!UICONTROL 數值]分類也可當成分類報表中的量度。

每個分類（父分類或子分類）在資料檔案中構成一個資料欄。 子分類的欄標題使用以下命名格式：

`<parent_name>^<child_name>`

如需資料檔案格式的詳細資訊，請參閱[分類資料檔案](/help/components/classifications/importer/c-saint-data-files.md)。

例如：

| 索引鍵 | 屬性 1 | 屬性 1^屬性 1-1 | 屬性 1^屬性 1-2 | 屬性 2 |
|---|---|---|---|---|
| 123 | ABC | 綠色 | 小 | A12B |
| 456 | DEF | 紅色 | 大 | C3D4 |

雖然多級分類的檔案範本較為複雜，但多級分類的強大功能是可以將不同的層級上傳為單獨的檔案。 此方法可用來將資料分組為隨時間變化的分類層級，而非不隨時間變化的分類層級，將需要定期（每天、每週等）上傳的資料量減至最少。

>[!NOTE]
>
>若資料檔案中的[!UICONTROL 代碼]欄空白，Adobe 會自動為每個資料列產生唯一的代碼。 為了避免在上傳含第二級或更高級分類資料的資料檔案時造成檔案毀損，請在「[!UICONTROL 代碼]」欄中的每一行填入星號 (*)。

## 範例

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

>[!NOTE]
>
>產品分類資料限於直接與產品相關的資料屬性。 此資料不限於產品在網站上的分類或銷售方式。 銷售類別、網站瀏覽節點或銷售專案等資料元素並非產品分類資料。 這些元素則是擷取至報告轉換變數中。

上傳此產品分類的資料檔案時，您可以將分類資料上傳為單一檔案或多個檔案（請參閱下文）。 藉由分隔檔案1中的色彩代碼和檔案2中的色彩名稱，只有在建立新的色彩代碼時，才需要更新色彩名稱資料（可能只有幾列）。 這會從更新較頻繁的檔案1中排除顏色名稱(CODE^COLOR)欄位，並減少檔案大小和產生資料檔案時的複雜性。

### 產品分類 - 單一檔案 {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| 索引鍵 | 產品名稱 | 產品詳細資料 | 性別 | 大小 | 程式碼 | 代碼^色彩 |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | 男式Polo襯衫，短袖(M，01) | M | M | 01 | 石頭 |
| 410390014 | Polo-SS | 男士Polo恤，短袖(L，03) | M | L | 03 | Heather |
| 410390015 | Polo-LS | 女子Polo恤，長袖(S，23) | F | S | 23 | 淺綠色 |

### 產品分類 — 多個檔案（檔案1） {#section_A99F7D0F145540069BA4EEC0597FF13F}

| 索引鍵 | 產品名稱 | 產品詳細資料 | 性別 | 大小 | 程式碼 |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | 男式Polo襯衫，短袖(M，01) | M | M | 01 |
| 410390014 | Polo-SS | 男士Polo恤，短袖(L，03) | M | L | 03 |
| 410390015 | Polo-LS | 女子Polo恤，長袖(S，23) | F | S | 23 |

### 產品分類 — 多個檔案（檔案2） {#section_19ED95C33B174A9687E81714568D56A3}

| 索引鍵 | 程式碼 | 代碼^色彩 |
|---|---|---|
| &#42; | 01 | 石頭 |
| &#42; | 03 | Heather |
| &#42; | 23 | 淺綠色 |
