---
title: 語言
description: 瀏覽器中的慣用語言設定。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# 語言

「語言」[維度](overview.md)會顯示訪客最常用來檢視內容的語言。 如果您想要瞭解訪客最常使用的語言以利進行當地語系化工作，此維度就十分實用。

>[!NOTE]
>
>此維度不會收集您的網站的語言。如果您想要在某個維度中收集網站的語言，Adobe 建議使用自訂變數，例如 [eVar](evar.md)。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `Accept-Language` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包含訪客慣用語言的好記名稱。範例包括 `"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"` 和 `"Spanish (Spain)"`。如果影像要求在 HTTP 標題中未包含有效語言，則維度項目為 `"None"`。
