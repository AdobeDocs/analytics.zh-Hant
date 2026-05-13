---
title: 頁面 URL
description: 頁面的 URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 95%

---

# 頁面 URL

「頁面URL」[維度](overview.md)會列出您網站上的URL。

>[!IMPORTANT]
>
>此維度僅適用於 Data Warehouse。 如果您想要在其他 Analytics 解決方案中使用 URL 維度，請考慮在每次點擊時將數值複製到 [eVar](evar.md)。

## 將資料填入此維度中

此維度會擷取在[頁面檢視呼叫 (`t()`)](/help/implement/vars/functions/t-method.md)來自 [`g` 和 `-g` 查詢字串](/help/implement/validate/query-parameters.md)的資料。 [連結追蹤呼叫 (`tl()`)](/help/implement/vars/functions/tl-method.md) 一律會移除此維度，即使 `g` 查詢字串存在也一樣。

有時 URL 的長度會超過 255 個位元組。 AppMeasurement 會針對影像要求中 URL 的前 255 個位元組使用 `g` 查詢字串參數。 如果 URL 的長度超過 255 個位元組，其餘的 URL 會儲存在 `-g` 查詢字串參數中。 此變數包含 URL 中的通訊協定和查詢字串。

AppMeasurement 會根據頁面的 URL 自動收集此資料。 您可以覆寫使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 變數收集的數值。

## 將 URL 填入 eVar 中

Adobe 建議將 eVar 設為串連字串 `window.location.hostname + window.location.pathname`。 此字串的效用通常會優於 `window.location.href`，因為它省略了通訊協定、查詢字串和錨點標記。

如果您想要讓 eVar 完全符合 Data Warehouse 中的「頁面 URL」維度，您可以使用[動態變數](/help/implement/vars/page-vars/dynamic-variables.md)，並將 eVar 設為每個點擊上的 `D=g`。

## 維度項目

維度項目包含您網站上的頁面 URL。
