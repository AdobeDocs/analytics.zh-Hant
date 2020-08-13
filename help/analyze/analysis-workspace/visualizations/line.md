---
description: 使用線條視覺化來描繪趨勢（以時間為基礎的）資料集
title: 折線圖
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 78ed02b7bb7a4dc042c837817d36fc8ce30dce79
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 17%

---


# 折線圖

此視覺效果使用折線圖表示量度，以顯示一段時間中值的變化。僅可在使用時間當作維度時，才使用折線圖。

## 視覺效果設定

>[!IMPORTANT]
>
> 某些「行」視覺化設定（例如「新增趨勢線」）目前處於有限測試中。 [更多詳情](https://docs.adobe.com/content/help/zh-Hant/analytics/landing/an-releases.html).

按一下「線條」視覺化右上角的齒輪圖示，以存取可用 [**的視覺化設**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) 定。 設定分為：

* 一般——在各種視覺化類型中常見的設定
* Axis —— 將影響線條視覺化的x或y軸的設定
* 覆蓋圖——為線條視覺化中顯示的系列新增其他內容的選項。

### 變更詳細程度

[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B)中的粒度下拉式清單可讓您將趨勢視覺效果 (例如折線圖、長條圖) 從每日變更為每週、每月等。

### 新增趨勢線覆蓋

在「 **視覺化設定>覆蓋圖>新增趨勢線**」下，您可以選擇將回歸趨勢線新增至行系列。 趨勢線有助於描述資料中更清晰的模式。

所有模型都使用普通最小二乘擬合：

| 模型 | 說明 |
|---|---|
| 線性 | 為簡單的線性資料集建立最適合的直線，當資料以穩定速率增加或減少時，此直線非常有用。 等式：y = a + b * x |
| 對數 | 建立最適合的曲線，當資料的變更率快速增加或減少，然後退出等級時，就很有用。 對數趨勢線可使用負值和正值。 等式：y = a + b * log(x) |
| 指數 | 建立曲線，當資料以不斷增加的速率上升或下降時，就很有用。 如果您的資料包含零值或負值，則不應使用此選項。 等式：y = a +<sup>eb * x |
| 電源 | 建立曲線，對於比較以特定速率增加的度量的資料集很有用。 如果您的資料包含零值或負值，則不應使用此選項。 等式：y = a *<sup>xb |
| 二次型 | 尋找形狀為拋物線（向上或向下凹入）的資料集的最佳擬合。 等式：y = a + b * x + c * x<sup>2 |
| 多項式 | 當資料集出現波動時很有用，例如分析大型資料集的得失。 等式：y = a + b * x + ... + k *<sup>xorder |
