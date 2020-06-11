---
title: 頁面
description: 頁面名稱。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# 頁面

「頁面」維度會列出您網站上的頁面名稱。 這是Adobe Analytics中最常使用的維度之一，因為它可讓您分析網站上哪些頁面表現最佳。

此維度與「網站」區 [段和](site-section.md) 「伺 [服器](server.md) 」維度。 頁面最細微，伺服器最細微，網站區段介於兩者之間。

## 將資料填入此維度

此維度會從影像請求中的 [`pageName` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會使用變數收集此 `pageName` 資料。 如果未 `pageName` 定義變數，則會回到使用頁面的URL。

## 維度值

維度值包括您網站上的頁面名稱。 您的組織會決定您要使用的特定維度值。 有些組織會直接使 `document.title`用，而有些則會制定自訂的網站導覽路徑標示。 無論您使用何種方法，請確定其一致性，並將它記錄在解決方案設 [計檔案中](/help/implement/prepare/solution-design.md)。

>[!NOTE] 在「報告與分析」中，轉換度量會使用此維度的線性歸因。 For example, revenue is split between all pages viewed in a visit before a `purchase` event. 分析工作區預設會使用最後一個歸因，並提供使用任何歸因模型的選項。
