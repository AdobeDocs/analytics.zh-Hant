---
description: 瞭解有助於縮短從Data Warehouse擷取資料所需時間的准則。
keywords: 最佳做法；失敗；逾時；疑難排解
title: Data Warehouse最佳作法
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 60%

---

# Data Warehouse 最佳作法

Data Warehouse 提供彈性的介面，可執行自訂報表。 請使用下列准則來協助縮短擷取資料所需的時間：

| 參考效能 | 說明 |
|--- |--- |
| 瞭解您請求的資料量 | 大型報表套裝的多年份報表可能包含幾百億個資料列。 處理和評估這些資料可能要花幾天，甚至幾星期。 評估如何使用報表來判斷是否存有某些多年份資料，或者您是否能將報表切割為多個請求。 |
| 報告時段與顆粒度比對 | 報告顆粒度需要更多的處理時間。 如果您報告整年的每月粒度，而每個月都提交報表請求，報表的處理速度就會快很多。 |
| 已完成資料範圍的報告 | 請求的日期範圍結束後，會產生 Data Warehouse 報表。 例如，您若是在星期三請求本週的報告，則要等到下一週的星期日才會產生報告。 |
| 在Data Warehouse中產生路徑報告 | 路徑量度（登入、退出、退回等） 在data warehouse中無法使用。 |
| 虛擬報告套裝 | 虛擬報表套裝的 Data Warehouse 報表功能可支援虛擬報表套裝所設定的替代時區。 |

