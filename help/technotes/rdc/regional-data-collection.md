---
title: 地區資料收集
description: 地區資料收集相關資訊
translation-type: tm+mt
source-git-commit: 731209e28dab9f17e06948614149a4c99938fdae
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 57%

---


# 地區資料收集

Adobe Experience Cloud 使用地區資料收集 (RDC) 功能，可讓您的使用者與 Adobe Experience Cloud 之間的互動，盡可能貼近使用者的需求。這能改善您網站/應用程式效能，並確保資料能儘快收集齊全，落實使用者體驗最佳化。按地區在 Data Collection Center (DCC) 收集您數位財產中的資料後，系統會透過安全連線將資料轉送到資料處理中心 (DPC)，資料經過處理後，便可供 Adobe Experience Cloud 的產品使用。

>[!IMPORTANT]
>
>「中國RDC（中國效能最佳化）附加元件套件」是Adobe Analytics的收費附加元件。 Adobe在中國大陸的效能最佳化可讓中國境內客戶將資料直接傳送至China edge節點，而非全球其他位置。 這可改善頁面載入時間和資料正確性，而非將資料傳送至中國境外的節點。 如需詳細資訊，請連絡您的Adobe銷售代表。

RDC 目前包括下列位置 (可能隨時變更)：

## 協力廠商和 HTTP 資料收集

| RDC 類型 | 資料收集中心 |
|---------------------|-------------------|
| 預設 | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨, 中國* |

Note: If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. 如果您在請求的 URL 中看到任一端點，即可判定出此結論。

*中國RDC需要China Add-On套件。 請參閱上述「重要」附註。

## 第一方 HTTPS 資料收集

| RDC 類型 | 資料收集中心 |
|---------------------|-------------------|
| 全域 (預設值) | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 僅限美洲 | 奧勒岡州、維吉尼亞州 |
| 僅限歐洲 | 愛爾蘭、巴黎 |
| 僅限亞太地區 | 孟買、新加坡、東京、雪梨 |
| 僅限中國* | 北京 |

*中國RDC需要China Add-On套件。 請參閱上述「重要」附註。

請注意：Experience Edge Global 可為您的使用者提供最佳效能。如果您想要使用替代的RDC類型，請聯絡Adobe客戶服務以取得協助。

## RDC 的優點

| 好處 | 說明 |
| --- | --- |
| 效能 | 透過RDC，您的訪客將連線至最接近的DCC。 如此可提供最快的回應時間，進而產生更精確的追蹤和更快的載入時間。 |
| 備援 | 如果與DCC的通訊中斷，資料收集會自動路由至最近的DCC，以確保服務的連續性。 |
| 備援 | 如果DCC與DPC之間的通訊中斷，Adobe的RDC基礎架構會將資料儲存在本機，然後在通訊恢復時將其轉送至DPC。 |

## RDC 的運作方式

下列清單說明 Adobe 使用的資料收集程序：

1. DNS 會自動將收集主機名稱解析為最接近訪客的資料收集中心的 IP 位址。
1. 訪客將資料傳送至該位置。
1. 系統會透過安全連線立即將資料轉送到資料處理中心，資料經過處理後，便可供 Adobe Experience Cloud 的產品使用。
