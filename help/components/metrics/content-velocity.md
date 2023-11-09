---
title: 內容速度
description: 「內容速度」可測量內容對下游內容的影響。
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
source-git-commit: 26e166e065df90cb327fe1106542e17831069141
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 19%

---

# 內容速度

「內容速度」計算量度可協助您測量維度(通常 [[!UICONTROL 頁面]](/help/components/dimensions/page.md))會為使用者在您網站或應用程式上花費的時間做出貢獻。

此量度使用 [參與率歸因](/help/analyze/analysis-workspace/attribution/models.md) 於 [頁面檢視](page-views.md) 量度作為計算的一部分。 透過造訪參與率，每次點選頁面時，先前在同一次造訪期間點選的所有頁面都會獲得頁面檢視的評分。 此公式通常表示造訪期間越早點選頁面，其獲得的評分就越多。 (請參閱 [頁面檢視（參與率） |造訪)或「造訪參與率」](#page-views-participation--visit-or-visit-participation) 以取得詳細資訊。)

## 計算

預設會計算「內容速度」 [量度](overview.md) 而且它使用下列公式 `Page views (Visit participation)` 除以 `Visits`.

![](assets/cont-velo-1.png)

## 常見用法

[!UICONTROL 「內容速度」]常與其他關鍵量度搭配用於內容分析，例如[!UICONTROL 頁面檢視]、[!UICONTROL 造訪]和[!UICONTROL 跳出率]等量度。

![](assets/cont-velo-3.png)

## 範例

下列範例會劃分「內容速度」的2個部分：「頁面檢視（參與率）」 |造訪)&#39;和&#39;造訪&#39;。

### 頁面檢視（參與率） |造訪)或「造訪參與率」

請考量下列造訪參與率如何影響歸因的範例：

在網站上，使用者依此順序造訪下列頁面：

* 頁面 A
* 頁面 B
* 頁面 C
* 頁面 D

在上述範例中，頁面A接收4次點選的評分、頁面B接收3次點選、頁面C接收2次點選，而頁面D接收1次點選。

以下範例說明相同的原則，但有些頁面被多次造訪。

* 頁面 A
* 頁面 B
* 頁面 C
* 頁面 B
* 頁面 D
* 頁面 A

在上述範例中，頁面A接收7次點選、頁面B接收8次點選、頁面C接收4次點選，而頁面D接收2次點選。

### 造訪數

計算造訪參與率後，結果會除以造訪次數。
