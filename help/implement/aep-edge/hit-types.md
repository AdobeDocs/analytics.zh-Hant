---
title: Adobe Analytics中的Edge Network事件型別
description: Adobe Analytics如何解讀從Edge Network收到的事件。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 6e500007e10086c0ff8108856a3563d7702f1130
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Adobe Analytics中的Edge Network事件型別

Adobe Analytics會根據您在AppMeasurement中呼叫的函式，以不同方式處理點選。 例如，[`s.t`](/help/implement/vars/functions/t-method.md)和[`s.tl`](/help/implement/vars/functions/tl-method.md)包含或省略某些維度，並以不同方式增加頁面檢視。 Adobe Experience Platform只包含`sendEvent`命令。 `xdm`承載中的特定屬性會決定如何在Adobe Analytics中解譯該資料。

Edge Network會使用以下邏輯來判斷Adobe Analytics頁面檢視和連結事件：

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL` 且無 `xdm.web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.eventType = web.webPageDetails.pageViews` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.url`) | 將裝載視為&#x200B;**連結事件** <br/>也將`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`設為`null` |
| 沒有`xdm.web.webInteraction.type`且沒有`xdm.webPageDetails.name`且沒有`xdm.web.webPageDetails.URL` | 放棄負載並忽略資料 |

| 資料物件承載包含…… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` 或 `data.__adobe.analytics.pageURL` 且無 `data.__adobe.analytics.linkType` | 考慮承載一個&#x200B;**頁面檢視** |
| `data.__adobe.analytics.linkType` 和 (`data.__adobe.analytics.linkName` 或 `data.__adobe.analytics.linkURL`) | 將裝載視為&#x200B;**連結事件** <br/>也將`data.__adobe.analytics.pageName`和`data.__adobe.analytics.pageURL`設為`null` |
| 沒有`data.__adobe.analytics.linkType`且沒有`data.__adobe.analytics.pageName`且沒有`data.__adobe.analytics.pageURL` | 放棄負載並忽略資料 |

>[!NOTE]
>
>如果您在相同承載中同時包含`xdm`物件和`data`物件，Adobe Analytics會檢查這兩個物件的個別欄位。

除了區分頁面檢視和連結點選，以下邏輯也可用於判斷某些事件是分類為A4T還是被捨棄。

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.eventType = display`或<br/>`xdm.eventType = decisioning.propositionDisplay`或<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`和`xdm._experience.decisioning` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = display`、<br/>`xdm.eventType = decisioning.propositionDisplay`、<br/>`xdm.eventType = personalization.request`或<br/>`xdm.eventType = decisioning.propositionFetch`，但沒有`xdm._experience.decisioning` | 放棄負載並忽略資料 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`，沒有`web.webInteraction.type` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = click`或`xdm.eventType = decisioning.propositionInteract`且沒有`xdm._experience.decisioning`且沒有`web.webInteraction.type` | 會捨棄裝載並忽略資料。 |

請參閱「[Adobe Analytics ExperienceEvent 完整延伸功能結構描述欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多資訊。
