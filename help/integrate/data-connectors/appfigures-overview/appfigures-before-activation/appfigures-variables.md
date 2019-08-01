---
description: AppFigures的資料連接器整合使用Analytics變數來追蹤各種AppFigures量度。
seo-description: AppFigures的資料連接器整合使用Analytics變數來追蹤各種AppFigures量度。
seo-title: Analytics整合變數
title: Analytics整合變數
uuid: 08d5b714-1c97-4be6-ae8-1f8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Integration Variables{#analytics-integration-variables}

AppFigures的資料連接器整合使用Analytics變數來追蹤各種AppFigures量度。

下表說明自動啓動appFigures整合的Analytics變數。

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>此整合會使用專用變數來儲存應用程式商店資料，因此您不需要指派自訂商務變數和事件。

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| eVar | 應用程式商店物件 ID | 從appFigures匯入。 | 使用瀏覽有效期、最近配置和基本子關聯設定此eVar。 |
| event(數值) | App Store 下載數 | 從appFigures匯入。 | 行動應用程式下載次數。 |
| event(數值) | App Store購買(在應用程式中) | 從appFigures匯入。 | 應用程式內購買項目和訂閱的數目。 |
| event(數值) | 應用程式商店排名 | 從appFigures匯入。 | 用於定義平均appFigures計算量度。不直接使用。 |
| event(數值) | 應用程式商店排名除數 | 從appFigures匯入。 | 用於定義平均appFigures計算量度。不直接使用。 |
| event(數值) | 應用程式商店評等 | 從appFigures匯入。 | 用於定義平均appFigures計算量度。不直接使用。 |
| event(數值) | 應用程式商店評等除數 | 從appFigures匯入。 | 用於定義平均appFigures計算量度。不直接使用。 |
| event(貨幣) | App Store收入(在應用程式中) | 從appFigures匯入。 | 應用程式內收入金額減去商店費用。 |
| event(貨幣) | App Store收入(一次關閉) | 從appFigures匯入。 | 應用程式購買總收入減去商店費用。 |
| event(貨幣) | App Store版稅(在應用程式中) | 從appFigures匯入。 | 未使用 |
| event(貨幣) | App Store版稅(一次推出) | 從appFigures匯入。 | 未使用 |

