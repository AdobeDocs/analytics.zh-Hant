---
title: 階層
description: （已淘汰）可用於報表的自訂維度。
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# 階層

>[!IMPORTANT]
>
>此維度已遭到淘汰，在Analysis Workspace中不是可用的[維度](overview.md)。 Adobe 建議改用 [eVar](evar.md) 和分類。

階層是自訂變數，您可以視需要使用。 這類變數在其設定所在的點擊過後即不存在。 在您的 Adobe 合約支援的前提下，最多可使用 5 個階層。

## 將資料填入階層中

每個階層會分別從影像要求中的 [`h1` - `h5` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。 例如，`h1` 查詢字串參數會收集階層 1 的資料，而 `h4` 查詢字串參數則會收集階層 4 的資料。

AppMeasurement (會將 JavaScript 變數編譯為影像要求以進行資料收集) 會使用變數 `hier1` - `hier5`。 如需實作準則，請參閱「實作」使用手冊中的 [階層](/help/implement/vars/page-vars/hier.md)。

## 維度項目

由於階層包含您實作中的自訂字串，因此您的組織會決定每個階層的維度項目。 請務必將每個階層的用途和常用的維度項目記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
