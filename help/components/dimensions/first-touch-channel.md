---
title: 首次接觸管道
description: 訪客參與期限內的第一個行銷管道。
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
TQID: https://experienceleague.adobe.com/1XBUjwxlZXmhXJtQZgpv9yU5Fwhns-bb9Q7BcP5S30Q
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 67%
---
# 首次接觸管道

「首次接觸管道」維度[1&rbrace;會報告訪客在其參與期間（預設為30天）遇到的第一個相符行銷管道。 &#x200B;](overview.md)若要了解哪些行銷管道促進網站的初始流量，此維度非常有用，讓您可將行銷工作聚焦於最有效的領域。

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

首次接觸管道會持續與訪客同時存在，直到對方超過訪客參與期間 (預設為 30 天) 沒有造訪網站。

如果您要將此維度設為特定值，則需執行下列步驟：

* 在「報告套裝設定」下的「行銷管道管理員」中，將所需的維度項目設為管道。
* 設定包含所需點擊條件的行銷管道處理規則。
* 訪客對您網站的點擊必須符合行銷管道處理規則中列出的條件，_且_&#x200B;必須是訪客參與期間內第一個要點擊的行銷管道值。

如果有後續的點擊符合不同行銷管道下的條件，則此維度不會覆寫為新的行銷管道。

## 維度項目

維度項目包含「行銷管道管理員」中的所有管道名稱。 預設情況下，值包括 `"Paid search"`、`"Natural search"`、`"Display"`、`"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"` 和 `"Referring domains"`。 您可以在「行銷管道管理員」中新增或刪除管道，而這會影響此維度的值。
