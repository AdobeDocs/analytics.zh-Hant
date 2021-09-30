---
title: 永久性 Cookie 支援
description: 判斷訪客是否能支援永久性 Cookie。
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 11%

---

# 永久性 Cookie 支援

「永久性Cookie支援」維度會顯示點擊是否使用源自永久性來源的訪客識別碼。 最常見的永久性來源是來自Cookie，但也可使用行動標題和其他來源。

## 將資料填入此維度中

Adobe會根據點擊識別碼的來源，在伺服器端決定此維度的值。 無法直接設定。 它可立即用於所有實施。

## 維度項目

* **`Enabled`**:點擊的訪客識別碼來自通常持續存在的來源。最常見的範例包括`aid`、`fid`或`mid`查詢字串參數，因為它們是從Cookie衍生其值。
* **`Disabled`**:點擊的訪客識別碼來自Adobe無法辨識為永久性的來源，例如IP +使用者代理字串。此維度項目也包含使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)變數的自訂訪客ID。

## 「Cookie支援」與「永久性Cookie支援」之間的差異

* **Cookie支援**:AppMeasurement會嘗試設定一般Cookie。維度項目是根據Cookie是否成功設定。
* **永久性Cookie支援**:維度項目是根據點擊的識別碼是否源自永久性來源（例如Cookie）。
