---
title: 瀏覽器類型
description: 製作瀏覽器的組織。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
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
source-wordcount: 156
ht-degree: 69%

---

# 瀏覽器類型

「瀏覽器型別」[維度](overview.md)會列出製作訪客所使用瀏覽器的組織。 若想查看訪客使用的主要瀏覽器，此維度相當實用。 它提供「瀏覽器」維度的值，不會將相同瀏覽器的不同版本列為單獨的維度項目。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。 查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。 Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，共同維護使用者代理程式與瀏覽器之間的查閱。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 裝置查詢]。

## 維度項目

維度項目包括製作瀏覽器的組織。 常見維度項目包含 `"Google"` ([!DNL Chrome] 的製作者)、`"Apple"` ([!DNL Safari] 的製作者)、`"Microsoft"` ([!DNL Edge] 的製作者) 和 `"Mozilla"` ([!DNL Firefox] 的製作者)。
