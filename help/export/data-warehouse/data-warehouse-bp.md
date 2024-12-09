---
description: 瞭解有助於縮短從Data Warehouse擷取資料所需時間的准則。
keywords: 最佳做法；失敗；逾時；疑難排解
title: Data Warehouse 最佳作法
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 79%

---

# Data Warehouse 最佳作法

Data Warehouse 提供彈性的介面，可執行自訂報表。請使用下列准則來協助縮短擷取資料所需的時間：

| 指引 | 說明 |
|--- |--- |
| 瞭解您所請求的資料量 | 大型報表套裝的多年份報表可能包含幾百億個資料列。處理和評估這些資料可能要花幾天，甚至幾星期。評估如何使用報表來判斷是否存有某些多年份資料，或者您是否能將報表切割為多個請求。 |
| 精細地匹配報表時段 | 報表粒度需要更多的處理時間。如果是報告一整年的每月粒度，若是針對每個月提交一個報告請求，報告的處理速度會快很多。 |
| 完整資料範圍的報告 | 請求的日期範圍結束後，會產生 Data Warehouse 報表。例如，您若是在星期三請求本週的報告，則要等到下一週的星期日才會產生報告。 |
| 在 Data Warehouse 中產生路徑分析報表 | Data Warehouse中不提供路徑量度（登入、退出、跳出等）。 |
| 虛擬報表套裝 | 虛擬報表套裝的 Data Warehouse 報表功能可支援虛擬報表套裝所設定的替代時區。 |

