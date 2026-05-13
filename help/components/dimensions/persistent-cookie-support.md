---
title: 永久性 Cookie 支援
description: 判斷訪客是否能支援永久性 Cookie。
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 90%

---

# 永久性 Cookie 支援

「永久性Cookie支援」 [維度](overview.md)會顯示該點選是否使用來自永久來源的訪客識別碼。 最常見的永久性來源來自於 Cookie，但也可能使用行動標題和其他來源。

## 將資料填入此維度中

Adobe 會根據點擊的識別碼來源判定此維度伺服器端的值。 無法直接加以設定。 可直接用於所有實作。

## 維度項目

* **`Enabled`**: 該點擊的訪客識別碼來自於通常持續存在的來源。 最常見的範例包括 `aid`、`fid` 或 `mid` 查詢字串參數，因為這些值從 Cookie 衍生而來。
* **`Disabled`**: 該點擊的訪客識別碼來自於 Adobe 未認定為永久性的來源，例如 IP + 使用者代理字串。 此維度項目也包含自訂訪客 ID 所使用的 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 變數。

## 「Cookie 支援」和「永久性 Cookie 支援」之間的差異

* **Cookie 支援**: AppMeasurement 試圖設定通用 Cookie。 此維度項目會依據 Cookie 是否成功設定。
* **永久性 Cookie 支援**: 此維度項目會依據該點擊的識別碼是否來自於永久性來源，例如 Cookie。
