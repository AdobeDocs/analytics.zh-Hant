---
title: 地區資料收集
description: 地區資料收集相關資訊
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 88d6edd99c96d19980464e0f1cfa5cc867baf645
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 38%

---

# 地區資料收集

Adobe Experience Cloud會使用地區資料收集(RDC)，讓訪客與Adobe之間的互動盡可能貼近訪客。 按地區在資料收集中心(DCC)收集資料後，系統會透過安全連線將資料轉送至資料處理中心(DPC)。 處理後，資料便可供Adobe Experience Cloud中的產品使用。

地區資料收集程式使用下列步驟：

1. DNS會自動將收集主機名稱解析為最接近訪客的資料收集中心的IP位址。
1. 訪客將資料傳送至該位置。
1. 系統會透過安全連線立即將資料轉送到資料處理中心，資料經過處理後，便可供 Adobe Experience Cloud 的產品使用。

使用地區資料收集功能可提供幾項優點：

* **效能**:透過RDC，您的訪客可連線至最接近的DCC。 此最佳化可提供最快的回應時間，進而產生更精確的追蹤和更快的載入時間。
* **備援**:如果DCC和您的DPC之間的通訊中斷，Adobe的RDC基礎架構會將資料儲存在本機，然後在通訊還原時將其轉送至DPC。

RDC 目前包括下列位置 (可能隨時變更)：

## 第三方資料收集

| RDC 類型 | 資料收集中心 |
| --- | --- |
| 預設 | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨、中國* |

{style=&quot;table-layout:auto&quot;}

*中國 RDC 需要中國附加元件套件。 請參閱 [中國效能最佳化](#china-performance-optimization) 下方。

>[!NOTE]
>
>請注意：如果您的 Analytics 影像要求傳送至 `adobedc`、`2o7.net` 或 `omtrdc.net` 端點，則表示您使用的是協力廠商資料收集。 如果您在請求的 URL 中看到任一端點，可以判定這點。

## 第一方資料收集

| RDC 類型 | 資料收集中心 |
| --- | --- |
| 全域 (預設值) | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 全球 + 中國* | 中國*、奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 僅限美洲 | 奧勒岡州、維吉尼亞州 |
| 僅限歐洲 | 愛爾蘭、巴黎 |
| 僅限亞太地區 | 孟買、新加坡、東京、雪梨 |
| 僅限中國* | 北京 |

{style=&quot;table-layout:auto&quot;}

*「僅限中國」及「全球 + 中國」RDC 類型需要中國附加元件套件。 全域+中國會將原始於中國的資料路由至Adobe的中國RDC，同時將原始於中國以外的資料路由至最接近的中國境外RDC。 請參閱 [中國效能最佳化](#china-performance-optimization) 下方。

## 中國效能最佳化

中國RDC（中國效能最佳化）附加元件套件是Adobe Analytics的收費附加元件。 Adobe在中國大陸的效能最佳化可讓擁有中國境內使用者的Adobe，將該資料直接傳送至中國境內的資料收集伺服器，而非全球其他位置。 此最佳化可改善頁面載入時間，以及將資料傳送至中國以外位置的資料準確度。 資料最終會傳輸至Adobe的其中一個中國境外資料處理中心(DPC)。 如需詳細資訊，請連絡您的Adobe銷售代表。

>!![NOTE]
不支援的中國RDC附加元件套件 [Web SDK](/help/implement/aep-edge/overview.md).

