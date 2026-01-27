---
title: Adobe Analytics 中的 Edge Network 事件類型
description: Adobe Analytics 如何解讀從 Edge Network 接收到的事件。
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# Adobe Analytics 中的 Edge Network 事件類型

Adobe Analytics 會根據您在 AppMeasurement 中呼叫的函式，以不同方式處理點擊。例如，[`s.t`](/help/implement/vars/functions/t-method.md) 與 [`s.tl`](/help/implement/vars/functions/tl-method.md) 會包含或省略特定的維度，並以不同方式遞增[頁面檢視次數](/help/components/metrics/page-views.md)。Adobe Experience Platform 僅包含 [`sendEvent`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/collection/js/commands/sendevent/overview) 指令。[`xdm`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/collection/js/commands/sendevent/xdm) 或 [`data`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/collection/js/commands/sendevent/data) 承載中的特定屬性，會決定 Adobe Analytics 如何解讀該資料。

Edge Network 會使用以下邏輯來判定 Adobe Analytics 的[頁面檢視次數](/help/components/metrics/page-views.md)與[連結事件](/help/components/metrics/page-events.md)：

## 使用 `xdm` 物件的頁面檢視次數與連結事件

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL` 且無 `xdm.web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.eventType = web.webpagedetails.pageViews` | 考慮承載一個&#x200B;**頁面檢視** |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webPageDetails.name` 或 `xdm.web.webPageDetails.URL`) | 將承載視為&#x200B;**連結事件**，<br/>同時也將 `xdm.web.webPageDetails.name` 與 `xdm.web.webPageDetails.URL` 設為 `null` |
| `xdm.web.webInteraction.type` 和 (`xdm.web.webInteraction.name` 或 `xdm.web.webInteraction.URL`) | 將承載視為&#x200B;**連結事件** <br/>同時也將 `xdm.web.webPageDetails.name` 與 `xdm.web.webPageDetails.URL` 設為 `null`，若有 |
| 無 `xdm.web.webInteraction.type` 和無 `xdm.web.webPageDetails.name` 和無 `xdm.web.webPageDetails.URL` | 放棄承載並忽略資料 |

>[!TIP]
>
>承載中的 XDM 欄位名稱會區分大小寫 (例如：`webPageDetails.URL`)。`xdm.eventType` 欄位是一個字串值，自有一組可接受的值，而這些值的大小寫可能與 XDM 欄位名稱不一致。如需了解可接受的值，請參閱 [XDM ExperienceEvent 類別](https://experienceleague.adobe.com/tw/en/docs/experience-platform/xdm/classes/experienceevent#eventType)中的 `eventType` 欄位。

+++使用 `xdm` 欄位的最低頁面檢視次數

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

+++使用 `xdm.eventType` 的最低頁面檢視次數

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++使用建議欄位的最少連結事件

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

## 使用 `data` 物件的頁面檢視次數與連結事件

| 資料物件承載包含… | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` 或 `data.__adobe.analytics.pageURL` 且無 `data.__adobe.analytics.linkType` | 考慮承載一個&#x200B;**頁面檢視** |
| `data.__adobe.analytics.linkType` 和 (`data.__adobe.analytics.linkName` 或 `data.__adobe.analytics.linkURL`) | 將承載視為&#x200B;**連結事件** <br/>同時也將 `data.__adobe.analytics.pageName` 與 `data.__adobe.analytics.pageURL` 設為 `null` |
| 無 `data.__adobe.analytics.linkType` 和無 `data.__adobe.analytics.pageName` 和無 `data.__adobe.analytics.pageURL` | 放棄承載並忽略資料 |

+++使用 `data` 欄位的最低頁面檢視次數

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

+++使用 `data` 欄位的最少連結事件

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
>如果您在同一個承載中同時包含 `xdm` 物件與 `data` 物件，Adobe Analytics 會檢查這兩個物件各自對應的欄位。

## A4T 與決策相關事件

除了區分頁面檢視次數與連結事件之外，以下邏輯也會判定特定的決策事件是否歸類為 A4T，或是予以捨棄。

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` 與 `xdm._experience.decisioning` | 將承載視為 **A4T** 呼叫。 |
| `xdm.eventType = decisioning.propositionDisplay` 且沒有 `xdm._experience.decisioning` | 放棄承載並忽略資料 |
| `xdm.eventType = decisioning.propositionInteract` 和 `xdm._experience.decisioning`，並且沒有 `xdm.web.webInteraction.type` | 將承載視為 **A4T** 呼叫。 |
|  `xdm.eventType = decisioning.propositionInteract` 和無 `xdm._experience.decisioning` 和無 `xdm.web.webInteraction.type` | 放棄承載並忽略資料。 |
| `xdm.eventType = decisioning.propositionFetch` | 放棄承載並忽略資料 |

>[!TIP]
>
>以下 `eventType` 值已淘汰。請注意，這些值對邏輯的影響方式，與其目前對應的值相同：
>
>* 事件類型 `display` 已淘汰。請改用 `decisioning.propositionDisplay`。
>* 事件類型 `click` 已淘汰。請改用 `decisioning.propositionInteract`。
>* 事件類型 `personalization.request` 已淘汰。請改用 `decisioning.propositionFetch`。

+++最小 A4T 顯示

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

+++最少 A4T 互動

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

請參閱 [Adobe Analytics ExperienceEvent 完整擴充功能結構描述欄位群組](https://experienceleague.adobe.com/tw/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)，了解更多資訊。
