---
title: 在Adobe Analytics中排除資料
description: 瞭解在資料收集前後如何排除資料的各種方法。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 在Adobe Analytics中排除資料

排除資料通常用於防止組織的測試作業填入生產資料，或防止不需要的資料誤填報表。 根據您的使用案例，使用下列任何方法從Adobe Analytics排除資料。

## 排除資料後資料收集

下列方法可讓您在Analytics資料收集伺服器收到影像要求後，在Adobe報表中排除資料。 使用這些方法排除的資料仍會計入計費伺服器呼叫。

* **依IP排除**：Adobe Analytics提供基本功能，可在報表套裝中排除IP位址或範圍的資料。 另請參閱 [依IP排除](/help/admin/admin/exclude-ip.md) 在管理員使用手冊中。
* **機器人規則**：機器人規則會從已知機器人使用者代理字串中取得流量，並從Analytics報表中將其排除。 透過機器人規則排除的資料會放在「機器人」報表中。 可建立自訂機器人規則來排除其他資料。 另請參閱 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) 在管理員使用手冊中。
* **VISTA規則**：根據您組織的需求，符合您需求的點選會傳送至專用於接收已排除資料的其他報表套裝。 VISTA規則通常針對IP位址使用，但不限於此IP位址。 您可以使用任何維度在報表套裝中包含或排除資料。 VISTA規則可能會產生額外成本；如需詳細資訊，請聯絡您的Adobe客戶團隊。
* **選擇退出Cookie**：您網站的所有訪客都可以造訪追蹤伺服器的特定頁面，自願選擇退出Adobe Analytics的追蹤功能。 另請參閱 [實作選擇退出連結](/help/implement/js/opt-out.md) （在實施使用手冊中）。

>[!TIP]
>
>處理規則無法排除資料，或傳送資料至其他報表套裝。 不過，某些變數可有條件地設定，而區段可用來將該資料從報表中排除。

## 排除資料前資料收集

如果您想要防止某些點選連線至Analytics資料收集伺服器，請使用 [`abort`](/help/implement/vars/config-vars/abort.md) 變數中。 此旗標可防止影像要求的傳送。 可計費伺服器呼叫不會因中止的影像要求而增加，因為它們不會連線至Adobe資料收集伺服器。
