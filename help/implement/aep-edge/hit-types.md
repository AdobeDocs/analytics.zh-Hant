---
title: Adobe Analytics中的Edge Network事件型別
description: Adobe Analytics如何解讀從Edge Network收到的事件。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Adobe Analytics中的Edge Network事件型別

Adobe Analytics會根據您在AppMeasurement中呼叫的函式，以不同方式處理點選。 例如，[`s.t`](/help/implement/vars/functions/t-method.md)和[`s.tl`](/help/implement/vars/functions/tl-method.md)包含或省略某些維度，並以不同方式增加[頁面檢視](/help/components/metrics/page-views.md)。 Adobe Experience Platform只包含[`sendEvent`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/commands/sendevent/overview)命令。 [`xdm`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/commands/sendevent/xdm)或[`data`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/commands/sendevent/data)裝載中的特定屬性會決定資料在Adobe Analytics中的解譯方式。

Edge Network使用以下邏輯來判斷Adobe Analytics [頁面檢視次數](/help/components/metrics/page-views.md)和[連結事件](/help/components/metrics/page-events.md)：

## 使用`xdm`物件的頁面檢視和連結事件

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL` 且無 `xdm.web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.eventType = web.webpagedetails.pageViews` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`) | 將裝載視為&#x200B;**連結事件** <br/>也將`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`設為`null` |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.URL`) | 將裝載視為&#x200B;**連結事件** <br/>同時將`xdm.web.webPageDetails.name`和`xdm.web.webPageDetails.URL`設定為`null` （如果存在） |
| 沒有`xdm.web.webInteraction.type`且沒有`xdm.web.webPageDetails.name`且沒有`xdm.web.webPageDetails.URL` | 放棄負載並忽略資料 |

>[!TIP]
>
>承載中的XDM欄位名稱區分大小寫（例如，`webPageDetails.URL`）。 `xdm.eventType`欄位是字串值，具有自己的一組接受值，且這些值中的大小寫可能與XDM欄位名稱不符。 如需接受的值，請參閱`eventType`XDM ExperienceEvent類別[中的](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/experienceevent#eventType)欄位。

+++使用`xdm`欄位的最小頁面檢視

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++使用`xdm.eventType`的最小頁面檢視

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++使用建議欄位的最小連結事件

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## 使用`data`物件的頁面檢視和連結事件

| 資料物件承載包含…… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` 或 `data.__adobe.analytics.pageURL` 且無 `data.__adobe.analytics.linkType` | 考慮承載一個&#x200B;**頁面檢視** |
| `data.__adobe.analytics.linkType` 和 (`data.__adobe.analytics.linkName` 或 `data.__adobe.analytics.linkURL`) | 將裝載視為&#x200B;**連結事件** <br/>也將`data.__adobe.analytics.pageName`和`data.__adobe.analytics.pageURL`設為`null` |
| 沒有`data.__adobe.analytics.linkType`且沒有`data.__adobe.analytics.pageName`且沒有`data.__adobe.analytics.pageURL` | 放棄負載並忽略資料 |

+++使用`data`欄位的最小頁面檢視

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++使用`data`欄位的最小連結事件

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>如果您在相同承載中同時包含`xdm`物件和`data`物件，Adobe Analytics會檢查這兩個物件的個別欄位。

## A4T和決定相關事件

除了區分頁面檢視和連結事件外，下列邏輯還會判斷某些決策事件是分類為A4T還是被捨棄。

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` 與 `xdm._experience.decisioning` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = decisioning.propositionDisplay`且沒有`xdm._experience.decisioning` | 放棄負載並忽略資料 |
| `xdm.eventType = decisioning.propositionInteract`和`xdm._experience.decisioning`且沒有`xdm.web.webInteraction.type` | 將裝載視為&#x200B;**A4T**&#x200B;呼叫。 |
| `xdm.eventType = decisioning.propositionInteract`且沒有`xdm._experience.decisioning`且沒有`xdm.web.webInteraction.type` | 會捨棄裝載並忽略資料。 |
| `xdm.eventType = decisioning.propositionFetch` | 放棄負載並忽略資料 |

>[!TIP]
>
>已棄用下列`eventType`個值。 請注意，這些值影響邏輯的方式與目前的對應值相同：
>
>* 事件型別`display`已過時。 請改用 `decisioning.propositionDisplay`。
>* 事件型別`click`已過時。 請改用 `decisioning.propositionInteract`。
>* 事件型別`personalization.request`已過時。 請改用 `decisioning.propositionFetch`。

+++最小化A4T顯示

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++最小的A4T互動

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

請參閱「[Adobe Analytics ExperienceEvent 完整延伸功能結構描述欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多資訊。
