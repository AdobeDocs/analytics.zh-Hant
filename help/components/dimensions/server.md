---
title: 伺服器
description: 伺服器的名稱。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# 伺服器

「伺服器」維度通常會列出網站的主機名稱。 對於結合多個網域或子網域的報表套裝，此維度對於查看哪些網域或子網域的效能最佳而言十分有用。

此維度與「頁面」和「網 [站](page.md) 」區 [段維度相關](site-section.md) 。 頁面最細微，伺服器最細微，網站區段介於兩者之間。

## 將資料填入此維度

此維度會從影像請求中的 [`server` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會使用變數收集此 [`server`](/help/implement/vars/page-vars/server.md) 資料。

## 維度值

維度值包括您網站上的伺服器。 您的組織會決定您要使用的特定維度值。 有些組織 `window.location.hostname`會使用，而有些則會制定自訂值。 無論您使用何種方法，請確定其一致性，並將它記錄在解決方案設 [計檔案中](/help/implement/prepare/solution-design.md)。
