---
title: 使用 Adobe Experience Platform Edge 實施 Adobe Analytics
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料 - 概觀
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 0ea86e7628e3cebe6f5fe1c4f584da1186b8cb83
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 16%

---

# 使用 Adobe Experience Platform Edge Network 實施 Adobe Analytics

Adobe Experience Platform Edge Network 可讓您將預計要送給多個產品的資料傳送到一個集中位置。Edge Network 會將適當的資訊轉送給所需的產品。此概念可讓您整合實作工作，尤其是橫跨多個資料解決方案時。 Adobe Analytics是可透過Edge Network將資料傳送至的產品之一。

## Adobe Analytics 如何處理 Edge Network 資料

由於傳送至Edge Network的資料與AppMeasurement資料的運作方式不同，Edge Network裝載會決定Adobe Analytics如何處理點選。 如需詳細資訊，請參閱Adobe Analytics[中的](hit-types.md)Edge Network事件型別。

傳送至Adobe Experience Platform Edge Network的資料可遵循三種格式： **XDM物件**、**資料物件**&#x200B;和&#x200B;**內容資料**。 當資料流將資料轉送到Adobe Analytics時，資料會轉換為Adobe Analytics可以處理的格式。

## `xdm`物件

符合您根據[XDM](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home) （體驗資料模型）建立的結構描述。 XDM 讓您在定義哪些欄位為事件一部分時更具靈活性。如果您想要使用Adobe Analytics專屬的預先定義結構描述，您可以將[Adobe Analytics ExperienceEvent結構描述欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)新增到您的結構描述。 新增後，您可以使用Web SDK中的`xdm`物件填入此結構描述，以傳送資料至報表套裝。 資料到達Edge Network時，會將XDM物件轉譯為Adobe Analytics可瞭解的格式。

如需有關XDM欄位以及如何對應到Adobe Analytics變數的完整參考，請參閱[XDM物件變數對應到Analytics](xdm-var-mapping.md)。

>[!TIP]
>
>如果您日後打算改用[Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing)，Adobe建議您不要使用Adobe Analytics結構描述欄位群組。 Adobe建議[建立您自己的結構描述](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect)，並使用資料流對應來填入所需的Analytics變數。 當您準備好移至Customer Journey Analytics時，此策略不會將您鎖定在prop和eVar的結構描述。

## `data`物件

除了使用`xdm`物件之外，您也可以改用`data`物件。 此資料物件適合目前使用AppMeasurement的實作，讓您更輕鬆地升級至Web SDK。 Edge Network會偵測Adobe Analytics專屬欄位的存在，而不需要符合結構描述。

如需資料物件欄位的完整參考資料，以及資料物件與Adobe Analytics變數的對應方式，請參閱[資料物件變數對應至Analytics](data-var-mapping.md)。

## 上下文資料變數

以您想要的任何格式傳送資料至Edge Network。 任何未自動對應至`xdm`或`data`物件欄位的欄位，在轉送至Adobe Analytics時會包含為[內容資料變數](/help/implement/vars/page-vars/contextdata.md)。 然後您必須使用[處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)將所需的欄位對應到它們各自的Analytics變數。

例如，如果您的自訂XDM結構描述如下所示：

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

然後，這些欄位將是「處理規則」介面中可供您使用的內容資料索引鍵：

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```
