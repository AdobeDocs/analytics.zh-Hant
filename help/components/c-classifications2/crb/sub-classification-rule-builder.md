---
description: 您可結合「分類規則產生器」和子分類，以簡化分類管理並減少所需的規則數目。若您的追蹤程式碼包含想要個別分類的程式碼，則您可能會想要執行此動作。
seo-description: 您可結合「分類規則產生器」和子分類，以簡化分類管理並減少所需的規則數目。若您的追蹤程式碼包含想要個別分類的程式碼，則您可能會想要執行此動作。
seo-title: 子分類與規則產生器 - 使用案例
solution: Analytics
subtopic: 分類
title: 子分類與規則產生器 - 使用案例
topic: 管理工具
uuid: 6db6a4a9-b93c-413b-8049-1e6cc1ba4a38
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 子分類與規則產生器 - 使用案例

您可結合「分類規則產生器」和子分類，以簡化分類管理並減少所需的規則數目。若您的追蹤程式碼包含想要個別分類的程式碼，則您可能會想要執行此動作。

## 子分類與規則產生器 - 使用案例 {#concept_6C8672C242544D7487E82886BBFABE6E}

您可結合「分類規則產生器」和子分類，以簡化分類管理並減少所需的規則數目。若您的追蹤程式碼包含想要個別分類的程式碼，則您可能會想要執行此動作。

See [Sub-Classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE) for conceptual information about sub-classifications.

**範例**

假設使用下列追蹤程式碼:

`channel:broad_campaign:creative`

分類階層可以讓您將分類套用到分類 (稱為 *`sub-classification`*). 亦即，您可將諸如關聯式資料庫等匯入工具，與多個表格搭配使用。其中一個表格會將完整追蹤程式碼對應至索引鍵，而另外的表格則會將這些索引鍵對應至其他表格。

![](assets/sub_class_table.png)

一旦設定好此架構後，即可使用[分類規則產生器](../../../components/c-classifications2/crb/classification-rule-builder.md)，上傳只會更新查詢表格 (亦即上圖中的綠色與紅色表格) 的小型檔案。之後，您即可使用規則產生器讓主要分類表格維持在最新狀態。

下列工作說明完成此動作的方式。

## Set up Sub-Classifications using the Rule Builder{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

說明如何使用「規則產生器」上傳子分類的範例步驟。

>[!NOTE]
>
>這些步驟說明如何完成子分類和規則產 [生器中所述的使用案例](../../../components/c-classifications2/crb/sub-classification-rule-builder.md)。

1. 在「[分類管理員](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)」中建立分類和子分類。

   範例:

   ![Step Info](assets/sub_class_create.png)

1. In the [Classifications Rule Builder](../../../components/c-classifications2/crb/classification-rule-builder.md#concept_C1F219E622044D43852EF5168FF7192A), classify the sub-classification key from the original tracking code.

   您可使用規則運算式執行此動作。在此範例中，填入 *`Broad Campaign code`* 會使用此規則運算式:

   | `#` | 規則類型 | 符合 | 設定分類 | 收件者 |
   |---|---|---|---|---|
   |  | 規則運算式 | `[^\:]:([^\:]):([^\:]`) | 廣泛促銷活動代碼 | `$1` |
   |  | 規則運算式 | `[^\:]:([^\:]):([^\:]`) | 創作代碼 | `$2` |

   >[!NOTE]
   >
   >At this point, you do not populate the sub-classifications *`Campaign Type`* and *`Campaign Director`*.

1. 上傳僅含指定子分類的分類檔案。

   See Multiple-Level Classifications.[](../../../components/c-classifications2/c-sub-classifications.md#concept_35AD906CDDC4441DAAF70664CF76AA0A)

   範例:

   | 代碼 | 管道 | 廣泛促銷活動代碼 | Broad Campaign code&amp;Hat;Campaign type | 廣泛促銷活動代碼&amp;Hat；促銷活動主管 | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | 品牌 | Suzanne |  |
   | * |  | 222 | 品牌 | Frank |  |

1. 若要維護查詢表格，請上傳小型檔案 (如以上所示)。

   You would upload this file, for example, when a new *`Broad Campaign code`* is introduced. 此檔案會套用至先前已分類的值。同樣地，若您建立新的子分類 (例如 子 *`Creative Theme`**`Creative code`*&#x200B;分類)時，您只會上傳子分類檔案，而不會上傳整個分類檔案。

   針對報告，這些子分類的功用與最上層分類完全相同。這可減輕使用分類所產生的管理負擔。
