---
title: 排除Adobe Analytics中的資料
description: 了解如何在資料收集前後排除資料的各種方法。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 排除Adobe Analytics中的資料

排除資料通常用於防止貴組織的測試工作填入生產資料，或防止不想要的資料不實膨脹報表。 根據您的使用案例，使用下列任何方法從Adobe Analytics中排除資料。

## 排除資料後收集

下列方法是在Adobe資料收集伺服器收到影像要求後，在Analytics報表中排除資料的方法。 使用這些方法排除的資料仍會計入計費伺服器呼叫。

* **依IP排除**:Adobe Analytics提供基本功能，可排除報表套裝中IP位址或範圍的資料。 請參閱 [依IP排除](/help/admin/admin/exclude-ip.md) （在管理員使用手冊中）。
* **機器人規則**:機器人規則會從已知機器人使用者代理字串中擷取流量，並從Analytics報表中排除。 透過機器人規則排除的資料會放置在機器人報表中。 可建立自訂機器人規則來排除其他資料。 請參閱 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) （在管理員使用手冊中）。
* **VISTA規則**:會根據您的組織需求，將符合您需求的點擊傳送至另一個專用於接收排除資料的報表套裝。 VISTA規則通常用於IP位址，但不限於這些位址。 您可以使用任何維度在報表套裝中包含或排除資料。 VISTA規則需支付額外費用；如需詳細資訊，請連絡貴組織的客戶經理。
* **退出Cookie**:您網站的所有訪客都可瀏覽您追蹤伺服器的特定頁面，以自動選擇退出Adobe Analytics追蹤。 請參閱 [實作退出連結](/help/implement/js/opt-out.md) 中。

>[!TIP]
>
>處理規則無法排除資料或傳送資料至其他報表套裝。 不過，某些變數可有條件地設定，而區段可用來從報表中排除該資料。

## 排除資料前資料收集

如果您想要防止某些點擊傳至Analytics資料收集伺服器，請使用 [`abort`](/help/implement/vars/config-vars/abort.md) 變數。 此標幟可防止傳送影像要求。 因為中止的影像請求未送達Adobe資料收集伺服器，因此計費伺服器呼叫不會遞增。
