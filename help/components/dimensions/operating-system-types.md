---
title: 作業系統類型
description: 作業系統 (不論版本為何)。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 55%

---

# 作業系統類型

「作業系統型別」[維度](overview.md)會顯示訪客使用的總體作業系統（不論特定版本為何）。 此維度不僅有助於了解哪些特定作業系統和版本最常見，也有助於了解訪客使用哪些典型作業系統平台。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。 查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。 Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與作業系統型別之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)時啟用[!UICONTROL 裝置查詢]。

## 維度項目

Dimension專案包含所使用的作業系統型別。 範例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
