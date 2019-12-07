---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# hierN。

[!UICONTROL 階層]變數會決定某個頁面在您的網站階層中的所在位置。


<!-- 

hierN.xml

 -->

此變數對於擁有超過三層結構的網站尤其實用。例如，媒體網站可能會將「運動」區段分成 4 個層級: 運動、地方運動、棒球、紅襪隊。若有人瀏覽了「棒球」頁面，則「運動」、「地方運動」和「棒球」等層級全都會反映該次瀏覽。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | H1-H5 | 階層 | "" |

可用的[!UICONTROL 階層]變數共有五個，必須由 Adobe 客戶服務啟用。在啟用階層時，您應決定要用於變數的分隔字元，以及該階層的最大層級數。例如，如果分隔字元為逗點，則運動階層可能顯示如下。

```js
s.hier1="Sports,Local Sports,Baseball"
```

請確定您的區段名稱皆未包含分隔字元。例如，若您其中一個區段的名稱為 "Coach Griffin, Jim"，您即應選擇逗號以外的分隔字元。每個階層區段限定使用 255 個位元組，而變數的總限制為 255 位元組。分隔字元在選定 (在建立階層時) 後即不易變更。

請向 Adobe 客戶服務洽詢為現有階層變更分隔字元的相關事宜。分隔字元亦可由多個字元組成，如 || 或 /|\，這些字元較少出現在階層區段中。

**語法和可能的值** {#section_0739948A68A2420DAB1CBEA3115A5A66}

請不要在各個分隔字元之間放置空格。在下列範例語法中，N 是介於一與五之間的數值。

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

除了分隔階層的層級外，請不要使用分隔字元。分隔字元可以是您所選擇的一或多個任何字元。

**範例** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**組態設定** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

無

**缺陷、問題和提示** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* 一旦設定階層後，分隔字元即不可變更。若必須變更階層的分隔字元，請與 Adobe 客戶服務連絡。
* 在設定階層後，層級的數量即不可變更。

> [!NOTE]階層的變更可能需收取服務費。

