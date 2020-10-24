---
title: 網站區段
description: 網站區段的名稱。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---


# 網站區段

「網站區段」維度會列出您網站上的網站區段名稱。對於大型網站，將頁面分組成區段會有所幫助。此維度可協助您查看檢視次數最多或表現最佳的網站區段。

此維度與[頁面](page.md)和[伺服器](server.md)維度有關。「頁面」最精細，「伺服器」最不精細，「網站區段」介於兩者之間。

## 將資料填入此維度中

此維度會從影像要求中的 [`ch` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 [`channel`](/help/implement/vars/page-vars/channel.md) 變數收集這項資料。

## 維度項目

維度項目包含您網站上的網站區段名稱。您的組織會決定您要使用的特定維度項目。無論您使用何種方法，請確保其一致性，並確實將其記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
