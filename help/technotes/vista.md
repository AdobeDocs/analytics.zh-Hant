---
title: Adobe Analytics的VISTA規則
description: 深入了解VISTA規則及其功能。
source-git-commit: 1e2284fd4a62816b27b33a91f3bee2575a852107
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# Adobe Analytics的VISTA規則

VISTA規則是自訂資料修改的替代形式，可在資料收集和處理之間套用。 請參閱 [處理順序](processing-order.md) 以取得VISTA規則所套用之資料管道中確切階段的詳細資訊。 VISTA規則只會在收集到目前的資料時影響資料；不會變更現有資料。

VISTA規則的一些常見使用案例包括：

* 將一個報表套裝的Analytics點擊複製到另一個報表套裝，選擇性地變更資料至複製的報表套裝
* 超過所提供使用案例的自訂IP排除 [依IP排除](/help/admin/admin/exclude-ip.md)
* 有條件或全域修改任何變數值
* 將變數值重複至其他變數
* 上傳檔案至可影響變數值的AdobeFTP站台

VISTA規則的許多使用案例已由 [處理規則](/help/admin/admin/c-processing-rules/processing-rules.md), [機器人規則](/help/admin/admin/bot-removal/bot-rules.md), [虛擬報表套裝](/help/components/vrs/vrs-about.md)，或僅更新Adobe Analytics實作。 Adobe建議僅以VISTA規則為最後手段。

>[!IMPORTANT]
>
>VISTA規則需要貴組織與Adobe Professional Services之間達成付費協定。 如果您想要建立或更新VISTA規則，請連絡貴組織的Adobe客戶經理。

## 建立VISTA規則

您必須使用Adobe Professional Services才能建立VISTA規則。 如果您想要建立VISTA規則，請連絡貴組織的Adobe客戶經理。

## 查看現有的VISTA規則

Adobe沒有提供UI來檢視現有的VISTA規則。 請連絡貴組織的Adobe客戶經理或客戶服務，並取得所需的報表套裝，以擷取現有VISTA規則的清單。
