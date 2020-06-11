---
title: 網站區段
description: 網站區段的名稱。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# 網站區段

「網站區域」維度會列出您網站上網站區域的名稱。 對於大型網站，將頁面分組成區段會很有幫助。 此維度對於查看檢視次數最多或表現最佳的網站區域非常有用。

此維度與「頁面」和「伺 [服器](page.md) 」維 [度相關](server.md) 。 頁面最細微，伺服器最細微，網站區段介於兩者之間。

## 將資料填入此維度

此維度會從影像請求中的 [`ch` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會使用變數收集此 [`channel`](/help/implement/vars/page-vars/channel.md) 資料。

## 維度值

維度值包括網站上網站區域的名稱。 您的組織會決定您要使用的特定維度值。 無論您使用何種方法，請確定其一致性，並將它記錄在解決方案設 [計檔案中](/help/implement/prepare/solution-design.md)。
