---
title: 網域
description: 訪客用來存取網際網路的組織或 ISP。
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# 網域

「網域」維度會報告訪客用來存取網際網路的存取點。

## 將資料填入此維度中

Adobe與 [Digital Element合作](https://www.digitalelement.com/) ，以決定存取點網域。 有幾種方法（包括反向DNS查閱）用於確定接入點域。 不需要任何設定，也沒有變數需填入。可直接用於所有 AppMeasurement 實作。

## 維度項目

範例維度項目包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。請注意，這些網域是接入點，不一定是代表ISP或組織的網域。

維值表 `None` 示接入點IP地址的所有者未提供域。
