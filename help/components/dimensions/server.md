---
title: 伺服器
description: 伺服器的名稱。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---


# 伺服器

「伺服器」維度通常會列出網站的主機名稱。對於結合多個網域或子網域的報表套裝，此維度十分有助於瞭解哪些網域或子網域的效能最佳。

此維度與[頁面](page.md)和[網站區段](site-section.md)維度有關。「頁面」最精細，「伺服器」最不精細，「網站區段」介於兩者之間。

## 將資料填入此維度中

此維度會從影像要求中的 [`server` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 [`server`](/help/implement/vars/page-vars/server.md) 變數收集這項資料。

## 維度項目

維度項目包含您網站上的伺服器。您的組織會決定您要使用的特定維度項目。有些組織會使用 `window.location.hostname`，有些則會制定自訂值。無論您使用何種方法，請確保其一致性，並確實將其記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
