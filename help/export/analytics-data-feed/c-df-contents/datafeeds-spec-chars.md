---
description: 資料摘要中所使用之特殊字元的相關資訊。
keywords: 資料饋送；工作；特殊字元；hit_ data；多值變數；events_ list；products_ list；mvvars
seo-description: 資料摘要中所使用之特殊字元的相關資訊。
seo-title: 特殊字元
solution: Analytics
subtopic: 資料饋送
title: 特殊字元
topic: Reports & Analytics
uuid: 5efe019b-39e6-4226-a9326-88202 a02 f5 e6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 特殊字元

資料摘要中所使用之特殊字元的相關資訊。

* [hit_data 檔案中的特殊字元](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [多值變數 (events_list、products_list、mvvars) 中的特殊字元](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [工作流程範例](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## hit_data 檔案中的特殊字元 {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

下列字元在 hit_data 檔案中有特殊含義:

| 字元 | 含義 | 說明 |
|--- |--- |--- |
| \t (定位字元) | 欄的結尾 | 標示資料欄位的結尾。 |
| \n (新行字元) | 行的結尾 | 標示資料行的結尾。 |
| \  (反斜線字元) | 逸出字元 | 當資料收集期間傳送的值包含定位、新行和反斜線字元時，逸出這些字元。 |

當任一特殊字元前面加上反斜線，即代表常值字元。

| 字元 | 含義 | 說明 |
|--- |--- |--- |
| \\t | 定位 | 常值定位字元。此字元是資料收集期間所傳送值的一部分。 |
| \\n | 新行 | 常值新行。此字元是資料收集期間所傳送值的一部分。 |
| \\ | 反斜線 | 常值反斜線字元。此字元是資料收集期間所傳送值的一部分。 |

## 多值變數 (events_list、products_list、mvvars) 中的特殊字元 {#section_056F8D540FFC4F24A001DC74331C2AAC}

下列字元在多值變數中有特殊含義:

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字元 </th> 
   <th colname="col02" class="entry"> 含義 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> , </code> (逗號字元) </td> 
   <td colname="col02"> 值的結尾 </td> 
   <td colname="col2"> <p>分隔多值變數中的產品字串、事件 ID 或其他值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (分號字元) </td> 
   <td colname="col02"> 個別產品值中子值的結尾 </td> 
   <td colname="col2"> <p>分隔 <code>product_list</code> 中個別產品的相關值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (等號字元) </td> 
   <td colname="col02"> 值指派 </td> 
   <td colname="col2"> <p>指派值給 <code>event_list</code> 中的事件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

當任一特殊字元前面加上脫字符號，即代表常值字元。

| 字元 | 含義 | 說明 |
|--- |--- |--- |
| ^, | 逗號 | 常值逗號字元。此字元是資料收集期間所傳送值的一部分。 |
| ^; | 分號 | 常值分號字元。此字元是資料收集期間所傳送值的一部分。 |
| ^= | 等號 | 常值等號字元。此字元是資料收集期間所傳送值的一部分。 |
| ^^ | 脫字符號 | 常值脫字符號字元。此字元是資料收集期間所傳送值的一部分。 |

## 工作流程範例 {#section_97F8C2925A35433DA2E7E8BE60037E37}

如果您的資料饋送中某些欄包含使用者提交的資料，在使用 `split`、`readLine` 或類似指令分離資料前，應先檢查是否有特殊字元。

假設有下列資料:

| 瀏覽器寬度 | 瀏覽器高度 | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

在匯出期間，eVar1 值中的新行和定位字元已逸出。這些行的資料饋送顯示如下:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

若要避免此狀況，請採用類似下列的解決方案:

1. 從檔案的開頭開始讀取，直到發現定位、新行、反斜線或脫字符號字元。
1. 根據所遇到的特殊字元，執行相關動作:

   * 定位 - 將該點前面的字串插入至資料存放儲存格並繼續。
   * 新行 - 結束資料存放行。
   * 反斜線 - 讀取下一個字元、插入適當的字串常值，然後繼續。
   * 脫字符號 - 讀取下一個字元、插入適當的字串常值，然後繼續。

