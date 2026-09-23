---
title: 上次接觸管道
description: 訪客參與期限內最近的行銷管道。
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 49%
---
# 上次接觸管道

「上次接觸管道」維度[維度](overview.md)會報告訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。 若要了解哪些行銷管道促進網站流量進而發生轉換，此維度非常有用，讓您可將行銷工作聚焦於最有效的領域。

## 將資料填入此維度中

此維度衍生自行銷管道處理規則。 它直接參照您在[行銷管道管理員](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)中定義的管道名稱。 每次點選都會以數值順序執行報表套裝的行銷管道處理規則，直到找到相符專案為止，這會將該行銷管道繫結至點選。 沒有可設定的變數。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自行銷管道處理規則） |
| **網頁SDK / XDM欄位** | 無（衍生自行銷管道處理規則） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 可設定 |

上次接觸管道會隨訪客持續保留，直到其超過訪客參與期間 (預設為 30 天) 未造訪網站。

如果您要將此維度設為特定值，則需執行下列步驟：

* 在「報告套裝設定」下的「行銷管道管理員」中，將所需的維度項目設為管道。
* 設定包含所需點擊條件的行銷管道處理規則。
* 訪客對您網站的點擊必須符合行銷管道處理規則中列出的條件。

>[!TIP]
>
>如果將此維度與使用[參與率歸因](/help/analyze/analysis-workspace/attribution/models.md)的量度搭配使用，則當其他歸因模型未使用時，可將評分歸因於`None`。 參與率量度需要在報告時段內使用行銷管道[執行個體](../metrics/instances.md)來接收評分。 如果行銷管道最初設定在報表回溯期之外，而報表回溯期內只存在持續值，則參與度量會將點數歸因於`None`。 其他歸因模型會將評分歸因於持續值。 若要避免在此案例中歸因至`None`，請考慮使用非參與歸因模型。

## 維度項目

維度項目包含「行銷管道管理員」中的所有管道名稱。 預設情況下，值包括 `"Paid search"`、`"Natural search"`、`"Display"`、`"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"` 和 `"Referring domains"`。 您可以在「行銷管道管理員」中新增或刪除管道，而這會影響此維度的值。
