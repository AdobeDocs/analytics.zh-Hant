---
description: 篩選條件可以縮小報告的範圍來包含或排除符合篩選條件的行項目。
title: 篩選報表資料
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 篩選報表資料 {#concept_09DC5B986A644738B12204DAC76A90E1}

篩選條件可以縮小報告的範圍來包含或排除符合篩選條件的行項目。

## 簡單篩選 {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

簡單篩選出現在大多數報告上，可以讓您快速找出特定的行項目。簡單篩選不使用任何特殊字元，因此 `-, ", ', +` 和其他特殊字元將會比對報表中的常值。您可以使用空格來尋找包含多個詞語的行項目。

例如：

```
help search
```

比對下列頁面：

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## 進階篩選 {#section_E016626C084640E8A066B2FDA5B932BF}

進階篩選可讓您使用一組篩選器來控制搜尋範圍。 您可以選取以符合所有篩選器或任何篩選器。

![](assets/advanced_filter.png)

**包含**

相符項目：如果詞語在行項目中的任何位置都找到。 這與簡單篩選器的運作相同。

>[!NOTE]篩選條件中不可使用空格，因為搜尋功能會將空格視為分隔符號

**不包含**

相符項目：如果詞語在行項目中的任何位置都找不到。 您可以使用「不包含」來篩選報表中的「未指定」、「無」、「沒有關鍵字」和其他[特殊值](https://marketing.adobe.com/resources/help/zh_TW/reference/none-unspecified-unknown-other.html)。

不包含： `none`

如需更精準的篩選，您可以使用進階 (特殊字元) 篩選：

* 進階 (特殊字元)：`-^none$`
* 進階 (特殊字元)：`-"keyword unavailable"`

例如，下列行項目是以「不包含」條件篩選而得，而非以「進階 (特殊字元)」條件篩選而得：

```
help:Rename the None classification key
```

**包含其中一個**

相符項目：如果行項目中有任何以空格分隔的詞語。 下列篩選條件顯示包含「mens」或「sale」的所有頁面：

包含其中一個: `mens sale`

比對下列頁面：

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**等於**

如果整個行項目（包括空格和其他字元）符合指定的片語，則相符。

等於: `mens:desk & travel`

`Mens:Desk & Travel`

**開頭為**

如果行項目（包括空格和其他字元）以指定的片語開頭，則相符項目。

開頭為: `mens`

比對下列頁面：

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**結尾為**

相符項目：行項目（包括空格和其他字元）以指定的片語結尾。

結尾為: `jean`

比對下列頁面：

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## 進階 (特殊字元) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

進階可讓您執行萬用字元和其他複雜搜尋。

| 進階 (特殊字元) | 說明 |
|--- |--- |
| `" "` | 比對完整的字句。 |
| `*` | 萬用字元是無所不包的比對方式。<br>例如，`r*p` 會比對出「Registration Signup」。 |
| `^` | 開始於<br>請勿在特殊字元與搜尋字句之間加上空格。 |
| `$` | 終止於<br>請勿在特殊字元與搜尋字句之間加上空格。 |
| `-` | 否<br>請勿在特殊字元與搜尋字句之間加上空格。 |
| `|` | 或者，<br>附註：您必須在直線字元 `" | "` 的兩側加上空格。 |

## 建立報告特定篩選器 {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

說明如何建立報表篩選的步驟。

<!-- 

t_reports_filter_specific.xml

 -->

某些報表包含特定於該報表的篩選器。 例如，可讓 [!UICONTROL Purchase Conversion Funnel Report] 您依網頁篩選。 A可 [!UICONTROL Geosegmentation Report] 讓您依地理區域篩選。 其他報表具有這些報表專屬的其他篩選器。

當您存取這些篩選時，可以看到清單中指定項目的報表度量。

**若要建立報表特定篩選**

1. 產生報表，例如 [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**)。
1. In the report header, click the **[!UICONTROL Filter]** link.
1. 在頁面上 [!UICONTROL Filter Selector] ，按一下 **[!UICONTROL Apply a Filter]**，然後選取篩選類型。
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. 按一下 **[!UICONTROL OK]**.

## 新增關聯篩選器 {#task_065042E384DA4BF3864C58AF2B88D6E2}

說明如何新增關聯篩選的步驟。

<!-- 

t_reports_correlation_filter.xml

 -->

某些報表可讓您新增自訂關聯篩選。 例如，如果您檢視的報表套裝的「網站區域」與 [!UICONTROL Pages Report] 「女性」頁面相關聯，則可建立篩選規則，以產生顯示「網站區域=女性」時最受歡迎頁面的報表。

您可以使用任何可用的關聯來篩選關聯報表中顯示的資料。 此範例顯示如何新增搜尋引擎關聯篩選。

**若要新增關聯篩選**

1. 執行支援關聯的報告(請參閱[執行劃分報表](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69))。
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. 在下 [!UICONTROL Filter Rule Creator]方，選擇要與項目關聯的類別。
1. 按一下 **[!UICONTROL OK.]**
