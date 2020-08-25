---
title: 排除Adobe Analytics中的資料
description: 瞭解如何排除資料收集前後的資料的各種方法。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# 排除Adobe Analytics中的資料

排除資料通常用於防止貴組織的測試工作填入生產資料，或防止不想要的資料不實膨脹報表。 根據您的使用案例，使用下列任何方法來排除Adobe Analytics中的資料。

## 排除資料後收集

以下方法是在Adobe資料收集伺服器收到影像要求後，在Analytics報表中排除資料的方式。 使用這些方法排除的資料仍會計入可計費伺服器呼叫。

* **依IP排除**:Adobe Analytics提供基本功能，可排除報表套裝中IP位址或範圍的資料。 請參 [閱「管理員使用指南](/help/admin/admin/exclude-ip.md) 」中的「依IP排除」。
* **機器人規則**:機器人規則會從已知機器人使用者代理字串擷取流量，並從Analytics報表排除這些流量。 透過機器人規則排除的資料會放在「機器人」報表中。 可建立自訂機器人規則以排除其他資料。 See [Bot Rules](/help/admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
* **VISTA規則**:視您組織的需求而定，符合您需求的點擊會傳送至另一個專用於接收排除資料的報表套裝。 VISTA規則通常用於IP位址，但不限於這些規則。 您可以使用任何維度在報表套裝中包含或排除資料。 VISTA規則需支付額外費用；如需詳細資訊，請洽詢您組織的客戶經理。
* **退出Cookie**:造訪您網站的所有訪客都可自願選擇退出Adobe Analytics中的追蹤，方法是造訪您追蹤伺服器的特定頁面。 請參 [閱「實作使用指南](/help/implement/js/opt-out.md) 」中的「實作退出連結」。

>[!TIP]
>
>處理規則無法排除資料或傳送資料至其他報表套裝。 但是，某些變數可有條件設定，而區段可用來排除該資料不進行報告。

## 排除資料前資料收集

如果您想要防止某些點擊到達Analytics資料收集伺服器，請使用變 [`abort`](/help/implement/vars/config-vars/abort.md) 數。 此標幟可防止傳送影像要求。 中止的影像要求不會增加計費伺服器呼叫，因為這些呼叫無法到達Adobe資料收集伺服器。
