---
title: Adobe Analytics中的Edge Network事件型別
description: Adobe Analytics如何解讀從Edge Network收到的事件。
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Adobe Analytics中的Edge Network事件型別

Adobe Analytics會根據您在AppMeasurement中呼叫的函式，以不同方式處理點選。 例如，[`s.t`](/help/implement/vars/functions/t-method.md)和[`s.tl`](/help/implement/vars/functions/tl-method.md)包含或省略某些維度，並以不同方式增加頁面檢視。 Adobe Experience Platform只包含`sendEvent`命令。 `xdm`承載中的特定屬性會決定如何在Adobe Analytics中解譯該資料。

Edge Network會使用以下邏輯來判斷Adobe Analytics頁面檢視和連結事件：

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL` 且無 `xdm.web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.eventType = web.webPageDetails.pageViews` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.url`) | 考慮承載一個&#x200B;**連結事件** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.url`) | 將裝載視為&#x200B;**連結事件** <br/>也將`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`設為`null` |
| 無 `xdm.web.webInteraction.type` 和 (無 `xdm.webPageDetails.name` 和無 `xdm.web.webPageDetails.URL`) | 放棄負載並忽略資料 |

除了區分頁面檢視和連結點選，以下邏輯也可用於判斷某些事件是分類為A4T還是被捨棄。

| XDM 承載包含... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display`或<br/>`xdm.eventType = decisioning.propositionDisplay`或<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`和`xdm._experience.decisioning` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`，但沒有`xdm._experience.decisioning` | 放棄負載並忽略資料 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`，沒有`web.webInteraction.type` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`且沒有`xdm._experience.decisioning`且沒有`web.webInteraction.type` | 會捨棄裝載並忽略資料。 |

請參閱「[Adobe Analytics ExperienceEvent 完整延伸功能結構描述欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多資訊。
