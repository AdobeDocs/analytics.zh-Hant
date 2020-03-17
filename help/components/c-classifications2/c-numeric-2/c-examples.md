---
description: 提供數值 2 分類匯入指引的範例。
subtopic: Classifications
title: 範例
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 範例

提供數值 2 分類匯入指引的範例。

<!-- 

c_example_1__rate.xml

 -->

在此案例中，您在「[!UICONTROL 分類轉換]」管理員建立了分類，並且要匯入 1 月的值：

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

在 1 月，Product1 的成本為其收入的 20% (如 `~MyCost^~value~` 所示)，而 Product2 的成本為其收入的 30%。由於您正要匯入新的列，因此 `~MyCost^~id~` 是空白的。

## 結果 {#section_E0569289C9B34C479C7D2CD9ECBF866E}

此報告的範例輸入如下所示：

期間：2010 年 1 月

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

在 2 月，使用者的 Product1 成本減少為收入的 15%，而 Product2 則減少為收入的 25%。

## 結果 {#section_23DF5353AC1B478C88647F222703352C}

此報告的範例輸入如下所示：

期間：2010 年 1 月

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

期間：2010 年 2 月

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

期間：2010 年 1 月 1 日 - 2010 年 2 月 28 日

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

因為您會匯入以下資料：

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 結果 {#section_674B57ADB8284B878F9E670038C31464}

此報告的範例輸入如下所示：

期間：2010 年 3 月

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

在此範例中，您在 Product1 的 1 月加入 $500 的運費，在 2 月加入 $600 的運費。

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fixed | none |

先前匯入的資料行均有 ID，這表示它們不是新的成本。

## 結果 {#section_2096084176614B9AA60F97D5853CB9EA}

此報告的範例輸入如下所示：

期間：2010 年 1 月

報告：產品

| 產品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

> [!NOTE] 進階使用者能利用此功能來略估值。但請勿將產生的資訊視為精確的值。

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

此範例的說明如下：

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## 結果 {#section_39E24ECCC3B34C9AADC25572662750E5}

此報告的範例輸入如下所示：

期間：2010 年 3 月

報告：產品 (依頁面分組)

| 產品 (依頁面分組) | 訂購 | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| 首頁 | 600 | $600 |
| 購物車 | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 結果 {#section_7F5F5970077D4E14A5DC91495E23540D}

此報告的範例輸入如下所示：

期間：2010 年 3 月

報告：產品 (依頁面分組)

| 產品 (依頁面分組) | 訂購 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首頁 | 600 | 0 |
| 購物車 | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

在此案例中，您會匯入以下資料：

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | revenue |
| 2010/03/01 - 2010/03/31 | fixed | revenue |

## 結果 {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

此報告的範例輸入如下所示：

期間：2010 年 3 月

報告：產品 (依頁面分組)

| 產品 (依頁面分組) | 訂購 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首頁 | 600 | $1800.00 |
| 購物車 | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

在此案例中，您會匯入以下檔案資料：

| 金鑰 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## 結果 {#section_6E2604D9A3B0455585EFF0F80FF54127}

此報告的範例輸入如下所示：

期間：2010 年 3 月

報告：產品 (依頁面分組)

| 產品 (依頁面分組) | 訂購 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首頁 | 600 | $1,000.00 |
| 購物車 | 400 | $2,000.00 |

