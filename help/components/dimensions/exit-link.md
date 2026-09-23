---
title: 退出連結
description: 退出連結的名稱。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 22%
---
# 退出連結

「退出連結」[維度](overview.md)會報告您的網站上實作的退出連結名稱。 退出連結會追蹤將訪客導覽至離開目前網域的對外點按。 如果您想要瞭解哪些對外連結的點按頻率最高，此維度就十分實用。

## 將資料填入此維度中

此維度由[個連結追蹤呼叫(`tl()`)](/help/implement/vars/functions/tl-method.md)填入。 沒有專用變數可供設定。 請改為傳送連結型別引數為`"e"`的`tl()`影像要求，並將連結名稱引數設定為所要的值。 `pe`查詢字串會將連結名稱路由至正確的連結維度（[個自訂連結](custom-link.md)為`lnk_o`，[個下載連結](download-link.md)為`lnk_d`，[個退出連結](exit-link.md)為`lnk_e`）。 如果未提供連結名稱，則會改用連結URL作為維度值，而URL衍生的值不受位元組限制的約束。

```js
s.tl(true,"e","Example exit link");
```

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **網頁SDK / XDM欄位** | 無 |
| **查詢引數** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 100位元組 |
| **持續性** | 點擊 |

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。 Adobe 建議您根據報告需求，將連結分組成有意義的類別。 如果未提供連結名稱，則維度專案會改為顯示為原始URL。 這些原始URL在報表中較難解譯，因此請儘可能提供描述性連結名稱。
