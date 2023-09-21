---
title: 網域
description: 訪客用來存取網際網路的組織或 ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 89%

---

# 網域

「網域」 [維度](overview.md) 報告訪客用來存取網際網路的存取點。

## 將資料填入此維度中

Adobe 與 [Digital Element](https://www.digitalelement.com/) 合作，以決定存取點網域。有幾種方法 (包括反向 DNS 查詢) 是用來確定存取點網域。不需要任何設定，也沒有變數需填入。可直接用於所有 AppMeasurement 實施作業。

## 維度項目

範例維度項目包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。請注意，這些網域是存取點，不一定是代表 ISP 或組織的網域。

`None` 的維度值表示存取點 IP 位址的所有者未提供網域。
