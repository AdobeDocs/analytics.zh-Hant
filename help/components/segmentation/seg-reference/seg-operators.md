---
description: 「區段產生器」可讓您使用選取的運算子來比較和限制值。
title: 區段的比較運算子
feature: Segmentation
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 95%

---

# 區段的比較運算子

「區段產生器」可讓您使用選取的運算子來比較和限制值。 運算子分為三類：標準、Data Warehouse 和不重複計數。

唯一支援的萬用字元是星號： &#42;。 如果您需要搜尋&#42;，可以使用反斜線將其逸出。

**範例**：假設您的頁面名稱為「My cool product」。區段規則「頁面名稱與My&#42;product相符」將會符合上述頁面名稱。 但是，規則「頁面名稱符合My\\&#42;product」只符合頁面名稱「My&#42;Product」。

## 標準運算子

| 運算元 | 選取的維度、區段或量度事件... |
|--- |--- |
| 等於 | 傳回完全符合數值或字串值的項目。注意：如果有使用萬用字元，請改為使用「符合」運算子。 |
| 不等於 | 傳回所有不含輸入值的項目。注意：如果有使用萬用字元，請改為使用「不符合」運算子。 |
| 等於任何 | 傳回與輸入欄位中任何值完全相符的項目 (最多 500 個項目)。例如，使用此運算子輸入「Search Results, Homepage」會比對「Search Results」和「Homepage」，並計為 2 個項目。此運算子的輸入欄位採用逗號分隔方式。 |
| 不等於任何 | 識別與輸入欄位中任何值完全相符的項目目 (最多 500 個項目)，然後只傳回不含這些值的項目。例如，使用此運算子輸入「Search Results, Homepage」會識別「Search Results」和「Homepage」，然後將它們排除在傳回的項目之外。此範例會計為 2 個項目。此運算子的輸入欄位採用逗號分隔方式。 |
| 包含 | 傳回含有輸入值字串的項目。 例如，如果「頁面」的規則為包含 &quot;Search&quot;，該規則便會比對到任何含有 &quot;Search&quot; 字串的頁面，包括 &quot;Search Results&quot;、&quot;Search&quot; 和 &quot;Searching&quot;。 &quot;contains&quot; 子句在 Adobe Analytics 中不區分大小寫，但在 Customer Journey Analytics 中區分大小寫。 |
| 不包含 | 傳回和「包含」規則相反的結果。具體而言，所有符合輸入值的項目都將從輸入值中排除。例如，如果「頁面」的規則為不包含 &quot;Search&quot;，該規則便不會比對到任何含 &quot;Search&quot; 字串的頁面，包括 &quot;Search Results&quot;、&quot;Search&quot; 和 &quot;Searching&quot;。這些值都將從結果中排除。 |
| 包含全部 | 傳回包含子字串的項目，包括多個連結在一起的值。例如，使用此運算子輸入 &quot;Search Results&quot; 將會比對到 &quot;Search Results&quot; 和 &quot;Results of Search&quot;，但不會單獨比對到 &quot;Search&quot; 或 &quot;Results&quot;。它會用 AND 比對到一起出現的 Search 和 Results。此運算子的輸入欄位採用空格分隔方式 (100 個字)。 |
| 不包含任何 | 與子字串 (包括多個值連結在一起) 比較以識別項目，然後只傳回不含這些值的項目。例如，使用此運算子輸入 &quot;Search Results&quot; 將會識別 &quot;Search Results&quot; 和 &quot;Results of Search&quot; (但不會單獨識別 &quot;Search&quot; 或 &quot;Results&quot;)，接著排除這些項目。此運算子的輸入欄位採用空格分隔方式 (100 個字)。 |
| 包含任何 | 傳回包含子字串的項目，包括多個相互連結或獨立存在的值。例如，使用此運算子輸入 &quot;Search Results&quot; 將會比對到 &quot;Search Results&quot;、&quot;Results of Search&quot;、&quot;Search&quot; 和 &quot;Results&quot;。它會用 OR 比對到一起出現或單獨出現的 &quot;Search&quot; 或 &quot;Results&quot;。此運算子的輸入欄位採用空格分隔方式 (100 個字)。 |
| 不包含任何 | 依據子字串識別項目，接著傳回不包含這些子字串的值。可以有多個連接值或例如，輸入 &quot;Search Results&quot; 將會比對到 &quot;Search Results&quot;、&quot;Results of Search&quot;、&quot;Search&quot; 和 &quot;Results&quot;，無論 &quot;Search&quot; 和 &quot;Results&quot; 是同時存在或單獨存在。接著會排除包含這些子字串的項目。此運算子的輸入欄位採用空格分隔方式 (100 個字)。 |
| 開始於 | 傳回以輸入值的字元或字串開頭的項目。 |
| 不開始於 | 傳回未以輸入值的字元或字串開頭的項目。這是「開始於」運算子的反面。 |
| 終止於 | 傳回以輸入值的字元或字串結尾的項目。 |
| 不終止於 | 傳回未以輸入值的字元或字串結尾的項目。這是「終止於」運算子的反面。 |
| matches | 根據給定的數值或字串值，傳回完全符合的項目。&quot;matches&quot; 子句在 Adobe Analytics 和 Customer Journey Analytics 中都區分大小寫。 **注意**：使用萬用字元功能時請使用此運算子。 「萬用字元」範例：<ul><li>`a*e` 會符合 `ae`、`abcde`、`adobe` 和 `a whole sentence`</li><li>`adob*` 會符合 `adobe`、`adobe analytics` 和 `adobo recipe`</li><li>`*dobe` 會符合 `dobe`、`adobe` 和 `cute little dobe`</li></ul> |
| 不符合 | 傳回所有不含輸入值的項目。注意：使用萬用字元功能時請使用此運算子。 |
| 存在 | 傳回存在的項目數。例如，如果您使用「存在」運算子評估「頁面找不到」維度，則會傳回存在的錯誤頁面數。 |
| 不存在 | 傳回不存在的所有項目。例如，如果您使用「不存在」運算子評估「頁面找不到」維度，則會傳回不存在此錯誤頁面的頁面數。 |

## Data Warehouse 運算子

| 運算元 | 選取的維度、區段或量度事件... |
| --- | --- |
| 小於 | 傳回數值計數小於輸入值的項目。 |
| 小於或等於 | 傳回數值計數小於或等於輸入值的項目。 |
| 大於 | 傳回數值計數大於輸入值的項目。 |
| 大於或等於 | 傳回數值計數大於或等於輸入值的項目。 |

## Distinct Count 運算子

您可以劃分維度內項目不重複計數的區段。例如：「曾檢視 5 個以上不重複產品的訪客」或「曾檢視 5 個以上不重複頁面的造訪」。

| 運算元 | 選取的維度、區段或量度事件... |
| --- | --- |
| 等於 | 傳回唯一計數等於輸入值的維度項目。 |
| 不等於 | 傳回唯一計數不等於輸入值的維度項目。 |
| 大於 | 傳回唯一計數大於輸入值的維度項目。 |
| 小於 | 傳回唯一計數小於輸入值的維度項目。 |
| 大於或等於 | 傳回唯一計數大於或等於輸入值的維度項目。 |
| 小於或等於 | 傳回唯一計數小於或等於輸入值的維度項目。 |

以下是有關不同維度數分段的影片：

>[!VIDEO](https://video.tv.adobe.com/v/27257/?quality=12)