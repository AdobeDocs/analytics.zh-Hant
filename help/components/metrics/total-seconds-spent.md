---
title: 總逗留秒數
description: 維度項目的彙總逗留秒數。
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 90%

---

# 總逗留秒數

「總逗留秒數」[量度](overview.md)會顯示訪客在指定的維度專案上逗留的彙總秒數。 如果您想要了解指定維度項目的原始逗留時間量，而不是其他逗留時間量度提供的那種平均值，此量度就十分實用。

在 Report Builder 中，此量度名為「總逗留時間」。

## 此量度的計算方式

此量度使用下列步驟來測量計算：

1. 對於指定的點擊，查看時間戳記。
2. 將此點擊與造訪的下次點擊時間戳記進行比較。 頁面檢視和連結追蹤點擊都會計入。
3. 兩次點擊之間經過的秒數計為維度項目。

持續存在的變數 (例如 [eVar](../dimensions/evar.md)) 會計為總逗留秒數。 流量變數 (例如 [Prop](../dimensions/prop.md)) 包含後續連結追蹤呼叫所花費的秒數。

>[!TIP]
>
>對於造訪的最後一次點擊不會測量逗留時間，因為沒有後續影像要求可測量經過的時間。 此概念也適用於包含單一點擊 (跳出) 的造訪。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](time-spent.md)。
