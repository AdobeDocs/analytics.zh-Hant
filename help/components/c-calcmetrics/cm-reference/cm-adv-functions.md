---
description: 勾選「函數」下拉式清單中的「顯示進階」即可存取這些函數。
seo-description: 勾選「函數」下拉式清單中的「顯示進階」即可存取這些函數。
seo-title: 參考進階功能
title: 參考進階功能
uuid: 7d1071b9-1737-4b7c-b318-87907deta5619
translation-type: tm+mt
source-git-commit: ff46935f6ec38c8981e4a1fffdbdc637bdf557db

---


# 參考：進階函數

<!-- 

cm_adv_functions.xml

 -->

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## 表格函數和列函數 {#section_8977BE40A47E4ED79EB543A9703A4905}

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

## 「包括零」參數的意義是什麼? {#section_C7A2B05929584C65B308FD372CB8E8E3}

此參數指出是否在計算中包括零。有時候零沒有意義，有時候卻很重要。

例如，如果您有「收入」量度，隨後新增「頁面檢視」量度至報表，您的收入會突然出現許多全都是零的列。您可能不希望這個結果影響到收入欄上的 MEAN、MIN、QUARTILE 等計算。在這種情況下，您可以勾選包括零參數。

另一方面，假設您有兩個感興趣的量度，因為其中一個的部分列是零而造成該量度的平均值或最小值比較高並不合理，這個時候您就不會勾選此參數來包括零。

## 和 {#concept_E14513FE464F4491AD0D4130D4EE621C}

傳回其引數的值。使用 NOT 可確保其值不等於某個特定值。

>[!NOTE]
>
>(零)表示False，且任何其他值為True。

```
AND(logical_test1,[logical_test2],...)
```

| 引數 | 說明 |
|---|---|
| *logical_test1* | 必填。可評估為 TRUE 或 FALSE 的任何值或運算式。 |
| *logical_test2* | 選填。您要評估為 TRUE 或 FALSE 的其他條件 |

## 近似相異計數 (維度) {#concept_000776E4FA66461EBA79910B7558D5D7}

傳回選定維度之維度項目的近似相異計數。此功能使用近似相異計數的 HyperLogLog (HLL) 方法。  其設定可保證值幾乎隨時皆為實際值的 5% 以內。

```
Approximate Count Distinct (dimension)
```

| 引數 |  |
|---|---|
| *dimension* | 您希望近似相異項目計數的維度。 |

## 範例使用案例 {#section_424E3FC5092948F0A9D655F6CCBA0312}

近似相異計數 (客戶 ID eVar) 是此函數的常見使用案例。

新「近似客戶」計算量度的定義:

![](assets/approx-count-distinct.png)

這是可以在報表中使用「近似客戶」量度的方式:

![](assets/approx-customers.png)

## 超出不重複值 {#section_9C583858A9F94FF7BA054D1043194BAA}

就如同 Count() 和 RowCount()，Approximate Count Distinct() 必須隨著[「超出不重複值」限制](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)變動。如果某維度的特定月份已達「超出不重複值」限制，此值將計為 1 個維度項目。

## 比較計數函數 {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() 是改良 Count() 和 RowCount() 函數後的成果。其可將建立的量度用於任何維度報表，藉此演算不同維度項目的近似計數。例如，用於「行動裝置類型」報表中的客戶 ID 計數。

由於使用 HLL 方法，而非像 Count() 與 RowCount() 那樣實際計數，此功能的準確度會稍微降低。

## 反餘弦 (列) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

傳回量度的反餘弦 (或餘弦的反函數)。反餘弦是一種角度，其餘弦是數字。傳回的角度是限制在 0 (零) 到 pi 的弧度。如果您想將結果從弧度轉換為度，請將結果乘以 180/PI( )。

```
ACOS(metric)
```

| 引數 |  |
|---|---|
| *量度* | 您所要擷取之角度的餘弦，從 -1 到 1。 |

## 反正弦 (列) {#concept_90F00DEC46BA47F8A21493647D9668CD}

傳回數字的反正弦。反正弦是一種角度，其正弦是數字。傳回的角度是限制在 -pi/2 到 pi/2 的弧度。若想以度表示反正弦，請將結果乘以 180/PI( )。

```
ASIN(metric) 
```

| 引數 |  |
|---|---|
| *量度* | 您所要擷取之角度的餘弦，從 -1 到 1。 |

## 反正切 (列) {#concept_3408520673774A10998E9BD8B909E90C}

傳回數字的反正切。反正切是一種角度，其正切是數字。傳回的角度是限制在 -pi/2 到 pi/2 的弧度。若想以度表示反正切，請將結果乘以 180/PI( )。

```
ATAN(metric)
```

| 引數 |  |
|---|---|
| *量度* | 您所要擷取之角度的餘弦，從 -1 到 1。 |

## 指數迴歸: 預計 Y (列) {#concept_25615693312B4A7AB09A2921083502AD}

已知 x 值 (metric_X)，計算預計 y 值 (metric_Y)，根據  ) 使用「最小平方」方法計算最佳配適線。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

傳回值在 Student 的 t 分布中的百分比，其中自由度為 n，z 分數小於 x。

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

傳回值在常態分布中的百分比，其中 z 分數小於 x。

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## 上限 (列) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

傳回不小於給定值的最小整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 CEILING(*Revenue*) 可將收入無條件進位至最接近的美金 $570。

```
CEILING(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要四捨五入的量度。 |

## 餘弦 (列) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

傳回給定角度的餘弦。如果角度是以度表示，請將角度乘以 PI( )/180。

```
COS(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取餘弦的角度 (以弧度為單位)。 |

## 立方根 {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

傳回數字的正立方根。數字的立方根是該數字的 1/3 乘冪值。

```
CBRT(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取立方根的量度。 |

## 累積 {#concept_3D3347797B6344CE88B394C3E39318ED}

傳回最後 N 列 x 的總和 (依維度排序，使用字串型欄位的雜湊值)。

如果 N &lt;= 0 則使用所有先前列。由於是依據維度排序，因此只適用於根據日期或路徑長度等自然順序排列的維度。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## 累積平均值 {#concept_ABB650962DC64FD58A79C305282D3E61}

傳回最後 N 列的平均值。

如果 N &lt;= 0 則使用所有先前列。由於是依據維度排序，因此只適用於根據日期或路徑長度等自然順序排列的維度。

>[!NOTE]
>
>這無法像您預期的收入/訪客等比率度量來運作：它會平均比率，而非將最後N個收入相加，並將過去N個訪客相加，然後再加以分隔。請改為使用

```
cumul(revenue)/cumul(visitor)
```

## 等於 {#concept_A3B97152B5F74E04A97018B35734BEEB}

傳回完全符合數值或字串值的項目。

## 指數迴歸_ 相關係數 (表格) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想與 *metric_Y* 建立關聯的量度。 |
| *metric_Y* | 您想與 *metric_X* 建立關聯的量度。 |

## 指數迴歸: 截距 (表格) {#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 指數迴歸: 斜率 (表格) {#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 下限 (列) {#concept_D368150EC3684077B284EE471463FC31}

傳回不大於給定值的最大整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 FLOOR(*Revenue*) 可將收入無條件捨去至最接近的美金 $569。

```
FLOOR(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要四捨五入的量度。 |

## 大於 {#concept_A83734A0C0C14646B76D2CC5E677C644}

傳回數值計數大於輸入值的項目。

## 大於或等於 {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

傳回數值計數大於或等於輸入值的項目。

## 雙曲餘弦 (列) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

傳回數字的雙曲餘弦。

```
COSH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想找出雙曲餘弦的角度 (以弧度為單位)。 |

## 雙曲正弦 (列) {#concept_96230731600C45E3A4E823FE155ABA85}

傳回數字的雙曲正弦。

```
SINH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想找出雙曲正弦的角度 (以弧度為單位)。 |

## 雙曲正切 (列) {#concept_BD249013732F462B9863629D142BCA6A}

傳回數字的雙曲正切。

```
TANH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想找出雙曲正切的角度 (以弧度為單位)。 |

## IF (列) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

如果您指定的條件評估為 TRUE 則 IF 函數會傳回某個值，如果條件評估為 FALSE 則傳回另一個值。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 引數 | 說明 |
|---|---|
| *logical_test* | 必填。可評估為 TRUE 或 FALSE 的任何值或運算式。 |
| *[value_if_true]* | 您想在 *logical_test* 引數評估為 TRUE 時傳回的值。(若未指定則此引數預設為 0。) |
| *[value_if_false]* | 您想在 *logical_test* 引數評估為 FALSE 時傳回的值。(若未指定則此引數預設為 0。) |

## 小於 {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

傳回數值計數小於輸入值的項目。

## 小於或等於 {#concept_99D12154DE4848B1B0A6327C4322D288}

傳回數值計數小於或等於輸入值的項目。

## 線性迴歸_ 相關係數 {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b。傳回相關係數

## 線性迴歸_ 截距 {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b。傳回 b。

## 指數迴歸_ 預計 Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b。傳回 Y。

## 線性迴歸_ 斜率 {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b。傳回 a。

## 以 10 為底的對數 (列) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

傳回數字的以 10 為底的對數。

```
LOG10(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取以 10 為底之對數的正實數。 |

## 對數迴歸: 相關係數 (表格) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 會使用 CORREL 方程式進行計算。

```
CORREL.LOG(metric_X,metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想與 *metric_Y* 建立關聯的量度。 |
| *metric_Y* | 您想與 *metric_X* 建立關聯的量度。 |

## 對數迴歸: 截距 (表格) {#concept_75A3282EDF54417897063DC26D4FA363}

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，迴歸方程式 *的截距* b[!DNL Y = a ln(X) + b] 做為最小平方迴歸。會使用 INTERCEPT 方程式進行計算。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 對數迴歸: 預計 Y (列) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. 會使用 ESTIMATE 方程式進行計算。

在迴歸分析中，已知 [!DNL y] 值 (*metric_X*)，此函數會計算預計 [!DNL x] 值 (*metric_Y*)，使用對數計算迴歸方程式 [!DNL Y = a ln(X) + b] 的最佳配適線。[!DNL a] 值對應到每個 x 值，而 [!DNL b] 是常數值。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 對數迴歸: 斜率 (表格) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 會使用 SLOPE 方程式進行計算。

```
SLOPE.LOG(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_A* | 您要指定做為相依資料的量度。 |
| *metric_B* | 您要指定做為獨立資料的量度。 |

## 自然對數 {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

傳回數字的自然對數。自然對數是以常數 *e* (2.71828182845904) 為底數。LN 是 EXP 函數的反函數。

```
LN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取自然對數的正實數。 |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

如果數字為 0 則傳回 1，若為其他數字則傳回 0。

```
NOT(logical)
```

| 引數 | 說明 |
|---|---|
| *logical* | 必填。可評估為 TRUE 或 FALSE 的值或運算式。 |

使用 NOT 需要知道運算式 (&lt;、&gt;、=、&lt;&gt; 等)是傳回 0 還是 1 值。

## 不等於 {#concept_EC010B7A9D2049099114A382D662FC16}

傳回所有不含輸入值的項目。

## 或 (列) {#concept_AF81A33A376C4849A4C14F3A380639D2}

如果任何引數為 TRUE 則傳回 TRUE，若所有引數為 FALSE 則傳回 FALSE。

>[!NOTE]
>
>(零)表示False，且任何其他值為True。

```
OR(logical_test1,[logical_test2],...)
```

| 引數 | 說明 |
|---|---|
| *logical_test1* | 必填。可評估為 TRUE 或 FALSE 的任何值或運算式。 |
| *logical_test2* | 選填。您要評估為 TRUE 或 FALSE 的其他條件 |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

傳回常數 PI 3.14159265358979，精確至小數點第 15 位。

```
PI()
```

[!DNL PI] 函數沒有引數。

## 乘冪迴歸: 相關係數 (表格) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想與 *metric_Y* 建立關聯的量度。 |
| *metric_Y* | 您想與 *metric_X* 建立關聯的量度。 |

## 乘冪迴歸: 截距 (表格) {#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 乘冪迴歸: 預計 Y (列) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 乘冪迴歸: 斜率 (表格) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 二次迴歸: 相關係數 (表格) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想與 *metric_Y* 建立關聯的量度。 |
| *metric_Y* | 您想與 *metric_X* 建立關聯的量度。 |

## 二次迴歸: 截距 (表格) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 二次迴歸: 預計 Y (列) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_A* | 您要指定做為相依資料的量度。 |
| *metric_B* | 您要指定做為相依資料的量度。 |

## 二次迴歸: 斜率 (表格) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 倒數迴歸: 相關係數 (表格) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*的相關係數* r[!DNL Y = a/X+b]。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想與 *metric_Y* 建立關聯的量度。 |
| *metric_Y* | 您想與 *metric_X* 建立關聯的量度。 |

## 倒數迴歸: 截距 (表格) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 倒數迴歸: 預計 Y (列) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 倒數迴歸: 斜率 (表格) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您要指定做為相依資料的量度。 |
| *metric_Y* | 您要指定做為獨立資料的量度。 |

## 正弦 (列) {#concept_21C8C3AA835947A28B53A4E756A7451E}

傳回給定角度的正弦。如果角度是以度表示，請將角度乘以 PI( )/180。

```
SIN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取正弦的角度 (以弧度為單位)。 |

## T 分數 {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Z 分數的別名，即平均值偏差除以標準差

## T 檢定 {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

執行 m 尾 t 檢定，使用 col 的 t 分數和 n 自由度。

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

在此，`m` 是反面的數目，而 `n` 是自由度。這些應該為數字 (在整個報表中為常數，例如，不會逐列變更)。

`X` 是 t 檢定的統計資料，且經常會是基於度量的公式 (例如 zscore)，並在每列進行評估。

傳回值是在給定自由度和反面的數目下，出現檢定統計資料 x 的機率。

**範例:**

1. 用其找出極端值:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. 將其與 `if` 合併，以便忽略非常高或非常低的反彈率，然後統計其他項目上的造訪率:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## 正切 {#concept_C25E00CB17054263AB0460D9EF94A700}

傳回給定角度的正切。如果角度是以度表示，請將角度乘以 PI( )/180。

```
TAN (metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取正切的角度 (以弧度為單位)。 |

## Z 分數 (列) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

根據常態分布傳回 Z 分數 (常態計分)。Z 分數是觀察值偏離平均值之標準差的數字。Z 分數為 0 (零) 表示分數與平均值相同。Z 分數可為正或負，代表其高於或低於平均值多少標準差。

Z 分數的方程式為:

![](assets/z_score.png)

其中 [!DNL x] 是原始分數、[!DNL μ] 是族群平均值，[!DNL σ] 是族群標準差。

>[!NOTE]
>
>[!DNL μ] (mu)和[!DNL σ] (sigma)會自動從度量計算。

Z分數(量度)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> <p> 傳回其第一個非零引數的值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z 檢定 {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

執行 n 尾 Z 檢定，使用 A 的 Z 分數。

傳回可在欄中看到目前列的機率。

>[!NOTE]
>
>假設值通常是分布的。

