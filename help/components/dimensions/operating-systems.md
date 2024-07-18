---
title: 作業系統
description: 訪客的作業系統。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# 作業系統

「作業系統」[維度](overview.md)會顯示訪客使用的作業系統和版本。 如果您的 Web 屬性中有作業系統專屬的功能，此維度可協助您了解哪些作業系統最常見。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。Adobe與[DeviceAtlas](https://deviceatlas.com/)合作，以維持使用者代理程式與作業系統之間的查閱。

* 對於AppMeasurement實作，此維度可立即運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 裝置查詢]。

## 維度項目

維度項目包括訪客使用的作業系統。範例包括 `"Windows 10"`、`"OS X 10.15.7"`、 和 `"Android 9"`。

## 追蹤準確的作業系統版本

隨著產業走向使用者端提示，某些作業系統版本可能會變得混亂。 例如，如果您未收集高平均資訊量使用者端提示，「Windows 10」和「Windows 11」都可以分組到「Windows 10」下。 如需詳細資訊，請參閱Technotes指南中的[使用者端提示](/help/technotes/client-hints.md)。
