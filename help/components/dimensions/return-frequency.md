---
title: 回訪頻率
description: 目前造訪與上次造訪之間的分段時間量。
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 94%

---

# 回訪頻率

「回訪頻率」[維度](overview.md)顯示回訪訪客的兩次造訪之間經過的時間長度。 當訪客回訪您的網站時，Adobe 會查看上次造訪是多久之前，並將點擊儲存在適當的維度項目中。 此維度十分有助於評估網站在一段時間內對訪客的吸引力和相關性。 此外也有助於識別您的網站內容和行銷活動對訪客的影響。

>[!TIP]
>
>此維度不包含首次訪客。

## 將資料填入此維度中

此維度可直接用於所有實施作業。 如果報告套裝包含資料，此維度即會運作。

此維度的資料會設定於造訪的第一次點擊，並持續存在於整個造訪期間。 值無法在造訪期間變更。

## 維度項目

維度項目包含以時間為基礎的貯體，具體取決於上次造訪後經過的時間。

* 少於 1 天
* 1 至 3 天
* 3 至 7 天
* 7 至 14 天
* 14 天至 1 個月
* 多於 1 個月

## 維度項目會顯示在專案日期範圍以外的貯體下

當您設定專案的日期範圍時，常會在日期範圍以外看到造訪的維度項目屬性。 例如，假設某個訪客於 7 月前往您的網站，然後在 9 月同一天返回您網站兩次。 9 月份的「回訪頻率」維度會在「多於 1 個月」下顯示一次造訪，並在「少於 1 天」下顯示一次造訪。
