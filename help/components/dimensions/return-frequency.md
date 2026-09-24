---
title: 回訪頻率
description: 目前造訪與上次造訪之間的分段時間。
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 76%
---
# 回訪頻率

「回訪頻率」[維度](overview.md)顯示回訪訪客的兩次造訪之間經過的時間長度。 當訪客回訪您的網站時，Adobe 會查看上次造訪是多久之前，並將點擊歸入適當的維度項目中。 此維度十分有助於評估網站在一段時間內對訪客的吸引力和相關性。 此外也有助於識別您的網站內容和行銷活動對訪客的影響。

>[!TIP]
>
>此維度不包含首次訪客。

## 將資料填入此維度中

Adobe會透過比較目前造訪與訪客上次造訪來計算此維度伺服器端。 無可設定的變數；可直接用於所有實施作業。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由Adobe計算） |
| **網頁SDK / XDM欄位** | 無（由Adobe計算） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 造訪 |

## 維度項目

維度項目包含以時間為基礎的分段，具體取決於自上次造訪後經過的時間。

* 少於 1 天
* 1 至 3 天
* 3 至 7 天
* 7 至 14 天
* 14 天至 1 個月
* 多於 1 個月

## 維度項目會顯示在專案日期範圍以外的貯體下

當您設定專案的日期範圍時，常會看到維度項目歸因於日期範圍以外的造訪。 例如，假設某個訪客於 7 月前往您的網站，然後在 9 月同一天返回您網站兩次。 9 月份的「回訪頻率」維度會在「多於 1 個月」下顯示一次造訪，並在「少於 1 天」下顯示一次造訪。
