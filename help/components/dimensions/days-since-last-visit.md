---
title: 上次造訪間隔天數
description: 目前點擊與上次造訪的間隔天數。
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
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
source-wordcount: '206'
ht-degree: 64%
---
# 上次造訪間隔天數

「上次造訪間隔天數」維度[維度](overview.md)會測量訪客目前的點選與上次造訪（如果有的話）之間經過的時間量。 此維度可協助您瞭解訪客造訪您的網站後的行為。 例如：

* 使用者回訪網站的頻率為何？
* 回訪頻率與轉換如何產生關聯？ 重複購買者是經常造訪還是不常造訪？
* 點進行銷活動的使用者是否頻繁回訪？

此維度不包含首次訪客。

## 將資料填入此維度中

Adobe會從訪客的造訪記錄中在伺服器端計算此維度。 無可設定的變數；可直接用於所有實施作業。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（由Adobe計算） |
| **網頁SDK / XDM欄位** | 無（由Adobe計算） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含訪客上次造訪與目前點擊的間隔天數。 每個天數都是個別的維度項目，若訪客的上次造訪與目前點擊發生於同一天，則會出現 `"Same day"`。
