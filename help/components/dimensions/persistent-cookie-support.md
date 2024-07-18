---
title: 永久性 Cookie 支援
description: 判斷訪客是否能支援永久性 Cookie。
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 90%

---

# 永久性 Cookie 支援

「永久性Cookie支援」 [維度](overview.md)會顯示該點選是否使用來自永久來源的訪客識別碼。 最常見的永久性來源來自於 Cookie，但也可能使用行動標題和其他來源。

## 將資料填入此維度中

Adobe 會根據點擊的識別碼來源判定此維度伺服器端的值。無法直接加以設定。可直接用於所有實作。

## 維度項目

* **`Enabled`**: 該點擊的訪客識別碼來自於通常持續存在的來源。最常見的範例包括 `aid`、`fid` 或 `mid` 查詢字串參數，因為這些值從 Cookie 衍生而來。
* **`Disabled`**: 該點擊的訪客識別碼來自於 Adobe 未認定為永久性的來源，例如 IP + 使用者代理字串。此維度項目也包含自訂訪客 ID 所使用的 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 變數。

## 「Cookie 支援」和「永久性 Cookie 支援」之間的差異

* **Cookie 支援**: AppMeasurement 試圖設定通用 Cookie。此維度項目會依據 Cookie 是否成功設定。
* **永久性 Cookie 支援**: 此維度項目會依據該點擊的識別碼是否來自於永久性來源，例如 Cookie。
