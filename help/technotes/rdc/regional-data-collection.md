---
title: 地區資料收集
description: 地區資料收集相關資訊
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: a4dd138f0f2198da66caa272dd62b46f24b578b2
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 90%

---

# 地區資料收集

Adobe 使用地區資料收集 (RDC) 功能，可讓您的訪客與 Adobe Experience Cloud 之間的互動，盡可能貼近訪客的需求。一旦資料在資料收集中心（DCC，也稱為Edge網站）進行地區性收集後，資料會透過安全連線轉送到資料處理中心（DPC，也稱為Core網站）。 資料經過處理後，便可供 Adobe Experience Cloud 的產品使用。若要變更您的RDC型別，請聯絡Adobe客戶服務。

區域資料收集流程使用以下步驟：

1. DNS 會自動將收集主機名稱解析為最接近訪客的資料收集中心的 IP 位址。
1. 訪客將資料傳送至該位置。
1. 系統會透過安全連線立即將資料轉送到資料處理中心，資料經過處理後，便可供 Adobe Experience Cloud 的產品使用。

使用區域資料收集有幾個優點：

* **效能**：透過 RDC，訪客可連接至最近的 DCC。 此最佳化可提供最快的回應時間，進而實現更準確的追蹤並加快載入時間。
* **備援**：如果 DCC 與 DPC 之間的通訊發生中斷，Adobe 的 RDC 基礎結構會在本機儲存資料，然後在通訊還原時將資料轉送至 DPC。

RDC 目前包括下列位置 (可能隨時變更)：

## 第三方資料收集

| RDC 類型 | 資料收集中心 |
| --- | --- |
| 預設 | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨、中國* |

{style="table-layout:auto"}

*中國 RDC 需要中國附加元件套件。 請參閱下方的[中國效能最佳化](#china-performance-optimization)。

>[!NOTE]
>
>請注意：如果您的 Analytics 影像要求傳送至 `adobedc.net`、`2o7.net` 或 `omtrdc.net` 端點，則表示您使用的是協力廠商資料收集。 如果您在請求的 URL 中看到任一端點，可以判定這點。

## 第一方資料收集

| RDC 類型 | 資料收集中心 |
| --- | --- |
| 全域 (預設值) | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 全球 + 中國* | 中國*、奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 僅限美洲 | 奧勒岡州、維吉尼亞州 |
| 僅限歐洲 | 愛爾蘭、巴黎 |
| 僅限亞太地區 | 孟買、新加坡、東京、雪梨 |
| 僅限中國* | 北京 |

{style="table-layout:auto"}

*「僅限中國」及「全球 + 中國」RDC 類型需要中國附加元件套件。 「全球 + 中國」會將源自於中國境內的資料路由傳送到 Adobe 的中國 RDC，同時將源自於中國境外的資料路由傳送到中國境外最接近的 RDC。請參閱下方的[中國效能最佳化](#china-performance-optimization)。

## 中國效能最佳化

中國 RDC (中國效能最佳化) 附加元件套件是 Adobe Analytics 的計費附加元件。 Adobe 在中國大陸的效能最佳化元件可讓擁有中國境內使用者的客戶直接傳送該資料給中國境內 Adobe 資料收集伺服器，而不是世界上的其他地方。比起將資料傳送至中國境外的位置，此最佳化可縮短頁面載入時間，並提升資料準確度。資料最終會傳輸到中國境外的 Adobe 資料處理中心 (DPC)。如需詳細資訊，請聯絡 Adobe 業務代表。

>[!NOTE]
>
>[Web SDK ](/help/implement/aep-edge/overview.md)不支援中國 RDC 附加元件套件。

