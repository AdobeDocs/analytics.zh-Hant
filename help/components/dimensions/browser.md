---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 202
ht-degree: 59%

---

# 瀏覽器

&#39;[!UICONTROL 瀏覽器]&#39; [維度](overview.md)會報告傳送點選的瀏覽器名稱和版本。 如果您想要測量訪客最常使用的瀏覽器，此維度就十分實用。 測試新版網站時，您可以在此維度的前幾大瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。 查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。 Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與瀏覽器之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant)時啟用[!UICONTROL 裝置查詢]。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。 相同瀏覽器的不同版本是分別的維度項目。

部分維度項目包含 `"(unknown version)"`，而不是版本號碼。 此維度專案會參考Adobe尚未新增至其查閱表格的最新瀏覽器版本。 由於瀏覽器經常更新，所以特定瀏覽器的 `"(unknown version)"` 為通用且暫時。 Adobe 一般會在每月維護版本更新查閱表格。