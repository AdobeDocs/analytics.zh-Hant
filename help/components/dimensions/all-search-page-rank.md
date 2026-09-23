---
title: 所有搜尋頁面排名
description: 判斷訪客在搜尋引擎的哪一頁上點進您的網站。
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 62%
---
# 所有搜尋頁面排名

「所有搜尋頁面排名」[維度](overview.md)會提供訪客在搜尋結果的哪個頁面上點進您的網站的insight。 例如，若您的網站出現在搜尋引擎搜尋結果的第二頁，此變數的維度項目則為「搜尋頁面 2」。

## 將資料填入此維度中

Adobe從每個點選的搜尋引擎[反向連結](referrer.md)衍生此維度，以決定訪客在搜尋結果中點進的頁面。 沒有可設定的變數。 報表套裝必須正確設定[內部 URL 篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)，此維度才能運作。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自搜尋引擎反向連結） |
| **網頁SDK / XDM欄位** | 無（衍生自搜尋引擎反向連結） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

如果訪客從搜尋引擎點進您的網站，則此維度的值是「搜尋頁面」，後面接著訪客點進的頁碼。 如果點擊並非源自於搜尋引擎，那麼此維度的值為「未指定」。
