---
description: 資料摘要中所使用之特殊字元的相關資訊。
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
solution: Analytics
subtopic: data feeds
title: 資料饋送中的特殊字元
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# 資料饋送中的特殊字元

Adobe使用逸出邏輯來確保傳送至資料收集伺服器的值不會損壞或產生負面資料饋送檔案。 Adobe保留下列字元的目的如下 `hit_data.tsv`:

## 任何欄中的特殊字元

| 字元 | 說明 |
|--- |--- |
| `\t` | 代表標籤。 標籤列或資料欄位的結尾。 |
| `\n` | 代表新行。 標籤列或點擊的結尾。 |
| `\` | 反斜線. 當以資料收集的方式傳送時，逸出字元。 |

當這些保留值前面有反斜線時，這些值會作為資料收集的一部分傳送。

| 字元 | 說明 |
|--- |--- |
| `\\t` | 值'`\t`'是在資料收集期間傳送，由Adobe逸出。 |
| `\\n` | 值'`\n`'是在資料收集期間傳送，由Adobe逸出。 |
| `\\` | 值'`\`'是在資料收集期間傳送，由Adobe逸出。 |

例如，您網站的訪客使用內部搜尋並搜尋「search\nstring」。 您在eVar1中填入「search\nstring」，然後將該值傳送給Adobe。 Adobe會收到此點擊，並逸出字串中包含的新行。 原始資料中的實際值為「search\\nstring」。

## 多值變數 (events_list、products_list、mvvars) 中的特殊字元

下列字元在可包含多個值的欄中具有特殊含義。

| 字元 | 說明 |
|--- |--- |
| `,` | 逗號. 代表個別值的結尾。 分隔產品字串、事件ID或其他值。 |
| `;` | 分號。 表示中的單個值的結尾 `product_list`。 分隔單一產品字串中的欄位。 |
| `=` | 等號。 Assigns a value to an event in `product_list`. |
| `^` | 脫字符號. 當以資料收集的方式傳送時，逸出字元。 |

當這些保留值前面加上脫字元號時，這些值會作為資料收集的一部分傳送。

| 字元 | 說明 |
|--- |--- |
| `^,` | 值'`,`'是在資料收集期間傳送，由Adobe逸出。 |
| `^;` | 值'`;`'是在資料收集期間傳送，由Adobe逸出。 |
| `^=` | 值'`=`'是在資料收集期間傳送，由Adobe逸出。 |
| `^^` | 值'`^`'是在資料收集期間傳送，由Adobe逸出。 |
