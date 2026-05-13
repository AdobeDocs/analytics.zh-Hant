---
title: 作業系統
description: 訪客的作業系統。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 45%

---

# 作業系統

「作業系統」[維度](overview.md)會顯示訪客使用的作業系統和版本。 如果您的 Web 屬性中有作業系統專屬的功能，此維度可協助您了解哪些作業系統最常見。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。 查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。 Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與作業系統之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 裝置查詢]。

## 維度項目

維度項目包括訪客使用的作業系統。 範例包括 `"Windows 10"`、`"OS X 10.15.7"`、 和 `"Android 9"`。

## 追蹤準確的作業系統版本

隨著產業走向使用者端提示，某些作業系統版本可能會變得混亂。 例如，如果您未收集高平均資訊量使用者端提示，「Windows 10」和「Windows 11」都可以分組到「Windows 10」下。 如需詳細資訊，請參閱Technotes指南中的[使用者端提示](/help/technotes/client-hints.md)。
