---
description: 資料摘要中所使用之特殊字元的相關資訊。
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: 資料摘要中的特殊字元
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料摘要中的特殊字元

Adobe 使用逸出邏輯來確保傳送至資料收集伺服器的值不會損壞或對資料摘要檔案產生負面影響。Adobe 在 `hit_data.tsv` 中保留下列字元，目的如下：

## 任何欄中的特殊字元

| 字元 | 說明 |
|--- |--- |
| `\t` | 代表標籤。標示欄或資料欄位的結尾。 |
| `\n` | 代表新行。標示列或點擊的結尾。 |
| `\` | 反斜線.在資料收集過程中傳送時使字元逸出。 |

當這些保留值前面有反斜線時，這些值會在資料收集過程中一併傳送。

| 字元 | 說明 |
|--- |--- |
| `\\t` | 資料收集期間會傳送值「`\t`」，由 Adobe 逸出。 |
| `\\n` | 資料收集期間會傳送值「`\n`」，由 Adobe 逸出。 |
| `\\` | 資料收集期間會傳送值「`\`」，由 Adobe 逸出。 |

例如，您網站的訪客使用內部搜尋並搜尋「search\nstring」。您在 eVar1 中填入「search\nstring」，然後將該值傳送至 Adobe。Adobe 會收到此點擊，然後逸出包含在字串中的新行。原始資料中的實際值為「search\\nstring」。

## 多值變數 (events_list、products_list、mvvars) 中的特殊字元

下列字元在可包含多個值的欄中具有特殊意義。

| 字元 | 說明 |
|--- |--- |
| `,` | 逗號.代表個別值的結尾。分隔產品字串、事件 ID 或其他值。 |
| `;` | 分號。代表 `product_list` 中個別值的結尾。分隔單一產品字串中的欄位。 |
| `=` | 等號。指派值給 `product_list` 中的事件。 |
| `^` | 脫字符號.在資料收集過程中傳送時使字元逸出。 |

當這些保留值前面有脫字符號時，這些值會在資料收集過程中一併傳送。

| 字元 | 說明 |
|--- |--- |
| `^,` | 資料收集期間會傳送值「`,`」，由 Adobe 逸出。 |
| `^;` | 資料收集期間會傳送值「`;`」，由 Adobe 逸出。 |
| `^=` | 資料收集期間會傳送值「`=`」，由 Adobe 逸出。 |
| `^^` | 資料收集期間會傳送值「`^`」，由 Adobe 逸出。 |
