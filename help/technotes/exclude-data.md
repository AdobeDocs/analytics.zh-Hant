---
title: 在Adobe Analytics中排除資料
description: 瞭解各種方法，瞭解如何在資料收集前後排除資料。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 在Adobe Analytics中排除資料

排除資料通常用於防止組織的測試工作填入生產資料，或防止不需要的資料虛假膨脹報表。 根據您的使用案例，使用下列任何方法從Adobe Analytics排除資料。

## 排除資料後資料收集

下列方法可讓您在Adobe資料收集伺服器收到影像要求後，在Analytics報表中排除資料。 使用這些方法排除的資料仍會計入計費伺服器呼叫。

* **依IP排除**：Adobe Analytics提供基本功能，可在報表套裝中排除IP位址或範圍的資料。 另請參閱 [依IP排除](/help/admin/admin/exclude-ip.md) （在管理員使用手冊中）。
* **機器人規則**：機器人規則會從已知的機器人使用者代理字串中取得流量，並將其從Analytics報表中排除。 透過機器人規則排除的資料會放入「機器人」報表中。 可建立自訂機器人規則來排除其他資料。 另請參閱 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) （在管理員使用手冊中）。
* **VISTA規則**：根據您組織的需求，符合您需求的點選會傳送至另一個專用於接收已排除資料的報表套裝。 VISTA規則通常針對IP位址使用，但不限於此IP位址。 您可以使用任何維度在報表套裝中包含或排除資料。 VISTA規則可能會產生額外成本；如需詳細資訊，請聯絡您的Adobe客戶團隊。
* **選擇退出Cookie**：您網站的所有訪客都可以自願造訪您的追蹤伺服器特定頁面，選擇退出Adobe Analytics的追蹤功能。 另請參閱 [實作選擇退出連結](/help/implement/js/opt-out.md) （在實作使用手冊中）。

>[!TIP]
>
>處理規則無法排除資料或將資料傳送至其他報表套裝。 不過，某些變數可有條件地設定，而區段可用來將該資料從報表中排除。

## 排除資料預先資料收集

如果您想要防止某些點選到達Analytics資料收集伺服器，請使用 [`abort`](/help/implement/vars/config-vars/abort.md) 變數。 此旗標會防止影像要求傳送。 可計費伺服器呼叫不會因中止的影像要求而遞增，因為它們無法連線Adobe資料收集伺服器。
