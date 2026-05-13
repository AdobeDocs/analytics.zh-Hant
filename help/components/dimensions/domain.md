---
title: 網域
description: 訪客用來存取網際網路的組織或 ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 54%

---

# 網域

「網域」[維度](overview.md)會報告訪客用來存取網際網路的存取點。

## 將資料填入此維度中

Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，以決定存取點網域。 有幾種方法 (包括反向 DNS 查詢) 是用來確定存取點網域。 不需要任何設定，也沒有變數需填入。

* 對於AppMeasurement實作，此維度可直接運作。
* 針對Web SDK實作，請在[設定資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)時啟用[!UICONTROL 網路查詢]。

## 維度項目

範例維度項目包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。 這些網域是存取點，不一定是代表ISP或組織的網域。

`None` 的維度值表示存取點 IP 位址的所有者未提供網域。
