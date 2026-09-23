---
title: 語言
description: 瀏覽器中的慣用語言設定。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 65%
---
# 語言

「語言」[維度](overview.md)會顯示訪客最常用來檢視內容的語言。 如果您想要瞭解訪客最常使用的語言以利進行當地語系化工作，此維度就十分實用。

>[!NOTE]
>
>此維度不會收集您的網站的語言。 如果您想要在某個維度中收集網站的語言，Adobe 建議使用自訂變數，例如 [eVar](evar.md)。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。 查閱值以影像要求中 `Accept-Language` 的 HTTP 標題為基礎。 可直接用於任何AppMeasurement或Web SDK （標籤）實作，且沒有變數可供設定。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（HTTP標頭） |
| **網頁SDK / XDM欄位** | 無（HTTP標頭） |
| **查詢引數** | 無（使用`Accept-Language`標頭） |
| **XML標籤** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含訪客慣用語言的易記名稱。 範例包括 `"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"` 和 `"Spanish (Spain)"`。 如果影像要求在 HTTP 標題中未包含有效語言，則維度項目為 `"None"`。
