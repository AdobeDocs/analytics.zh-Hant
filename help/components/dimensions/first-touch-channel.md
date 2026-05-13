---
title: 首次接觸管道
description: 訪客參與期限內的第一個行銷管道。
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
TQID: https://experienceleague.adobe.com/1XBUjwxlZXmhXJtQZgpv9yU5Fwhns-bb9Q7BcP5S30Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 91%

---

# 首次接觸管道

「首次接觸管道」維度[1&rbrace;會報告訪客在其參與期間（預設為30天）遇到的第一個相符行銷管道。 &#x200B;](overview.md)若要了解哪些行銷管道促進網站的初始流量，此維度非常有用，讓您可將行銷工作聚焦於最有效的領域。

## 將資料填入此維度中

此維度會直接參照您在[「行銷管道管理員」](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)中定義的管道名稱。

傳送至 Adobe 資料收集伺服器的每個點擊，都會透過報表套裝的行銷管道處理規則執行。 它會以數值順序反覆每個規則，直到找到相符項目，而該行銷管道會繫結至點擊。 首次接觸管道會持續與訪客同時存在，直到對方超過訪客參與期間 (預設為 30 天) 沒有造訪網站。

如果您要將此維度設為特定值，則需執行下列步驟：

* 在「報表套裝設定」下的「行銷管道管理員」中，將所需的維度項目設為管道。
* 設定包含所需點擊條件的行銷管道處理規則。
* 訪客對您網站的點擊必須符合行銷管道處理規則中列出的條件，_且_&#x200B;必須是訪客參與期間內第一個要點擊的行銷管道值。

如果有後續的點擊符合不同行銷管道下的條件，則此維度不會覆寫為新的行銷管道。

## 維度項目

維度項目包含「行銷管道管理員」中的所有管道名稱。 預設情況下，值包括 `"Paid search"`、`"Natural search"`、`"Display"`、`"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"` 和 `"Referring domains"`。 您可以在「行銷管道管理員」中新增或刪除管道，而這會影響此維度的值。
