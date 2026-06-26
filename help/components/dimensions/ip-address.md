---
title: IP 位址
description: 每次點選的傳送來源IP位址，可在Data Warehouse中使用。
feature: Dimensions
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
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 17%

---

# IP 位址

「IP位址」[維度](overview.md)會列出每次點選傳送來源的IP位址。

>[!IMPORTANT]
>
>此維度僅適用於 Data Warehouse。

## 將資料填入此維度中

AppMeasurement會自動從每個影像要求的HTTP標題收集IP位址。 它對應至資料摘要中的`ip`欄。 如需詳細資訊，請參閱[資料行參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

如果報表套裝的[一般帳戶設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)中啟用了[!UICONTROL IP模糊化]，Analytics中每一處的IP位址都會模糊化或移除，包括Data Warehouse。

## 維度項目

Dimension專案包含傳送點選的IP位址。
