---
description: 「分類設定」支援的檔案格式
title: 分類設定檔案格式
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
source-git-commit: c642664ecca24d9fc555944fb2b449f30eac879d
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---

# 分類設定檔案格式

分類集支援多種檔案格式來大量上傳分類資料。 每種格式對於成功上傳資料都有特定要求。

一旦您的檔案根據這些規格正確格式化，您就可以透過「分類設定」介面或API上傳它。 如需詳細的上傳指示：

* **瀏覽器上傳**：請參閱[結構描述](manage/schema.md)
* **API上傳**：請參閱[Analytics分類API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

分類設定支援下列檔案格式：

* **JSON**： JavaScript Object Notation檔案包含結構化資料
* **CSV**：逗號分隔值檔案
* **TSV/TAB**：以Tab分隔的值檔案

## 一般檔案需求

所有檔案格式都必須符合下列要求：

* **檔案編碼**：使用不含位元組順序標籤的UTF-8。 也支援Latin1編碼。
* **字元限制**：個別分類值的上限為255個位元組。
* **索引鍵需求**：索引鍵值不可為空白或僅包含空格。 如果出現重複的索引鍵，則會使用最後一個出現的專案。

+++**JSON格式詳細資料**

JSON檔案格式遵循JSON行(JSONL)的慣例。 檔案的每行必須包含一個JSON物件，其中每個物件代表單一分類記錄。

>[!NOTE]
>
>儘管JSON行有以下慣例，所有上傳仍使用`.json`副檔名。 使用`.jsonl`延伸可能會導致錯誤。

### JSON結構

每個JSON物件都必須包含：

* `key` （必要）：分類記錄的唯一識別碼
* `data` （更新所需）：包含分類欄名稱及其值的物件
* `action` （選用）：要執行的動作。 支援的值包括：
   * `update` （預設）
   * `delete-field`
   * `delete-key`
* `enc` （選用）：資料編碼規格。 支援的值包括：
   * `utf8`或`UTF8` （預設）
   * `latin1` 或 `LATIN1`

所有JSON欄位名稱(`key`、`data`、`action`、`enc`)都區分大小寫，且必須為小寫。

### JSON範例

**基本更新記錄：**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**使用指定的編碼更新：**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**刪除特定欄位：**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**刪除整個金鑰：**

```json
{"key": "product999", "action": "delete-key"}
```

### JSON驗證規則

* `key`欄位為必填，不能為Null或空白。
* 對於`update`動作，`data`欄位為必要項，不得為空白。
* 針對`delete-field`動作，`data`欄位必須包含要刪除的欄位。
* 對於`delete-key`動作，`data`欄位不得存在。
* 支援的編碼值不區分大小寫，並包含標準字元集名稱。

+++

+++**CSV格式詳細資料**

CSV （逗號分隔值）檔案使用逗號來分隔分類資料欄位。

### CSV結構

* **標題列**：第一列必須包含欄標題，第一欄必須是索引鍵欄。 後續欄應該符合分類集結構描述中的名稱
* **資料列**：每個後續列都包含分類資料
* **分隔符號**：欄位以逗號分隔
* **引號**：包含逗號、引號或新行的欄位應該包含在雙引號中

### CSV範例

**基本分類資料：**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**刪除整個金鑰：**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**刪除特定欄位（混合更新內容）：**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### CSV格式規則

* 包含逗號的欄位必須括在雙引號中
* 包含雙引號的欄位必須藉由加倍(`""`)來逸出引號
* 空白欄位代表該分類的null值
* 欄位周圍的前置和尾端空格會自動被裁剪
* 系統會保留引號欄位內的特殊字元（定位字元、新行）

**刪除作業：**
* 在任何欄位中使用`~deletekey~`來刪除整個索引鍵及其所有分類資料
* 在特定欄位中使用`~empty~`以僅刪除那些分類值（保留其他欄位不變）
* 使用`~empty~`時，您可以在相同檔案中混合刪除與更新

+++

+++**TSV/TAB格式詳細資料**

TSV （定位字元分隔值）和TAB檔案使用定位字元來分隔分類資料欄位。

### TSV/TAB結構

* **標題列**：第一列必須包含欄標題，第一欄必須是索引鍵欄。 後續欄應該符合分類集結構描述中的名稱
* **資料列**：每個後續列都包含分類資料
* **分隔符號**：欄位是以定位字元分隔(`\t`)
* **引號**：一般不需要引號，但有些實作支援引號欄位

### TSV/TAB範例

**基本分類資料：**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**刪除整個金鑰：**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**刪除特定欄位（混合更新內容）：**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### TSV/TAB格式規則

* 欄位以單一定位字元分隔
* 空白欄位（連續索引標籤）代表null值
* 通常不需要特別報價
* 前置和尾端空格會保留
* 應避免在欄位中使用新行字元

**刪除作業：**
* 在任何欄位中使用`~deletekey~`來刪除整個索引鍵及其所有分類資料
* 在特定欄位中使用`~empty~`以僅刪除那些分類值（保留其他欄位不變）
* 使用`~empty~`時，您可以在相同檔案中混合刪除與更新

+++

## 錯誤處理

常見的上傳問題和解決方案：

### 一般檔案格式錯誤

* **無效的檔案格式**：確認您的副檔名符合內容格式(.json、.csv、.tsv或.tab)。
* **「未知的標題」**：欄名稱必須符合您的分類集結構描述（適用於所有格式）。

### csv/TSV特定錯誤

* **「第一欄必須是索引鍵」**：請確定您的CSV/TSV檔案具有適當的標頭列，且索引鍵欄在前。
* **「至少需要兩個標頭專案」**： CSV/TSV檔案必須至少有一個「索引鍵」欄和一個分類欄。
* **「第一個標頭欄必須稱為&#39;Key&#39;」**：第一個欄標頭必須完全是&#39;Key&#39; （大寫K，區分大小寫）。
* **「不允許空白標頭」**：所有CSV/TSV欄標頭都必須有名稱。
* **「欄數不符合標頭」**：每個CSV/TSV資料列的欄位數必須與標頭列相同。
* **「格式錯誤的檔案」**：檢查CSV引號、TSV檔案中的適當索引標籤分隔等。

### JSON錯誤

* **「索引鍵為必填欄位」**：所有JSON記錄都必須有非空白的`"key"`欄位（小寫，區分大小寫）。
* **&quot;使用action=update&quot;**&#x200B;時，資料為必填欄位： JSON更新動作必須包含`"data"`欄位。
* **&quot;使用action=delete-field&quot;**&#x200B;時，資料為必填欄位： JSON刪除欄位動作必須在`"data"`欄位中指定要刪除的欄位。
* **&quot;使用action=delete-key&quot;**&#x200B;時資料不得存在： JSON delete-key動作不能包含`"data"`欄位。
* **「不支援的編碼」**：僅在`"enc"`欄位(utf8、UTF8、latin1、LATIN1)中使用支援的編碼值。
* **無效的JSON語法**：請確定JSON檔案的格式正確符合JSONL慣例。 同時檢查一般JSON格式、缺少引號、逗號、方括弧等。

### 大小限制錯誤

* **「金鑰超過大小上限」**：個別金鑰不能超過255個位元組。
* **「資料行值超過大小上限」**：個別分類值不能超過255個位元組。

## 最佳做法

* **檔案大小**： 50MB是瀏覽器和API上傳的檔案大小上限。
* **批次處理**：對於大型資料集，請考慮分割成較小的檔案。
* **資料驗證**：請先以小型範例檔案進行測試，然後再上傳大型資料集。
* **備份**：保留來源資料檔案的復本。
* **增量更新**：使用JSON格式精確控制個別記錄的更新與刪除。
