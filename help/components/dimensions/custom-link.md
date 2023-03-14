---
title: 自訂連結
description: 自訂連結的名稱。
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 100%

---

# 自訂連結

「自訂連結」維度會報告您的網站上實施作業的自訂連結名稱。當您想了解訪客點擊次數最多的連結類型時，此維度就很實用。

## 將資料填入此維度中

此維度會針對同時具有 `pe` 查詢字串且字串值為 `lnk_o` 的點擊，從影像要求中的 [`pev2` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。如果 `pe` 查詢字串在點擊中有不同的值，則此維度不會收集資料。

如果您想使用 AppMeasurement 將資料傳送至此維度，請傳送連結類型引數為 `"o"` 的 [`tl()`](/help/implement/vars/functions/tl-method.md) 影像要求。將所需的值填入連結名稱引數。

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。Adobe 建議您根據報告需求，將連結分組成有意義的類別。
