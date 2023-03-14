---
description: Data Warehouse 提供彈性的介面，可執行自訂報表。遵循這些指引可以縮短擷取資料的時間。
keywords: 最佳實務；失敗；逾時；疑難排解
title: Data Warehouse 最佳作法
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 98%

---

# Data Warehouse 最佳作法

Data Warehouse 提供彈性的介面，可執行自訂報表。遵循這些指引可以縮短擷取資料的時間。



| 指引 | 說明 |
|--- |--- |
| 在 Reports &amp; Analytics 中執行頁面檢視、瀏覽、訪客和其他標準報表 | 建立 Data Warehouse 報表之前，請查看報表中是否已有您在尋找的資訊。如果有，則由於 Reports &amp; Analytics 已針對常用量度執行預先處理，因此可更快地提供報表。 |
| 瞭解您所請求的資料量 | 大型報表套裝的多年份報表可能包含幾百億個資料列。處理和評估這些資料可能要花幾天，甚至幾星期。評估如何使用報表來判斷是否存有某些多年份資料，或者您是否能將報表切割為多個請求。 |
| 精細地匹配報表時段 | 報表粒度需要更多的處理時間。如果是報告一整年的每月粒度，若是針對每個月提交一個報告請求，報告的處理速度會快很多。 |
| 完整資料範圍的報告 | 請求的日期範圍結束後，會產生 Data Warehouse 報表。例如，您若是在星期三請求本週的報告，則要等到下一週的星期日才會產生報告。 |
| 在 Data Warehouse 中產生路徑分析報表 | 在 Data Warehouse 中無法使用路徑分析量度 (登入點、退出點、彈回數等)。 |
| 虛擬報表套裝 | 虛擬報表套裝的 Data Warehouse 報表功能可支援虛擬報表套裝所設定的替代時區。 |
