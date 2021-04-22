---
title: 週
description: 量度發生的週別。
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

---

# 週

「週」維度會報告指定的量度發生的週別。第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。此維度可讓您查看量度在一段時間內變化，因此對趨勢報表而言十分重要。

## 將資料填入此維度中

此維度可直接用於所有實施作業。如果報表套裝包含資料，此維度即會運作。

## 維度項目

在 Analysis Workspace 中，維度項目包括一週中第一天的日期 (月、日和年)。

在 Data Warehouse，維度項目會根據請求的日期範圍納入有編號的週。例如，第一個完整週是 `"Week 1"`。如果請求包含一週的一部分，資料會分組到維度項目 `"Week 0"`。
