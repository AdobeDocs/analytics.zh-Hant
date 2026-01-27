---
title: 使用 Adobe Experience Platform Edge 實施 Adobe Analytics
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料 - 概觀
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9845f1bc73b6cf5fd932c6896a50379ddd008c20
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 100%

---

# 使用 Adobe Experience Platform Edge Network 實施 Adobe Analytics

Adobe Experience Platform Edge Network 可讓您將預計要送給多個產品的資料傳送到一個集中位置。Edge Network 會將適當的資訊轉送給所需的產品。此概念可讓您整合實施工作，特別是橫跨多個資料解決方案時。Adobe Analytics 是您可以使用 Edge Network 對其傳送資料的其中一項產品。

## Adobe Analytics 如何處理 Edge Network 資料

由於傳送至 Edge Network 的資料與 AppMeasurement 資料的運作方式不同，Edge Network 的承載會決定 Adobe Analytics 如何處理該點擊。如需更多資訊，請參閱 [Adobe Analytics 中的 Edge Network 事件類型](hit-types.md)。

傳送至 Adobe Experience Platform Edge Network 的資料可遵循三種格式：**XDM 物件**、**資料物件**&#x200B;以及&#x200B;**情境資料**。當資料流將資料轉送至 Adobe Analytics 時，這些資料會被轉換為 Adobe Analytics 可處理的格式。

## `xdm` 物件

符合您根據 [XDM](https://experienceleague.adobe.com/tw/en/docs/experience-platform/xdm/home) (體驗資料模型) 所建立的結構描述。XDM 讓您可以自由定義哪些欄位屬於事件的一部分。如果您想要使用專屬於 Adobe Analytics 的預先定義結構描述，您可以將 [Adobe Analytics ExperienceEvent 結構描述欄位群組](https://experienceleague.adobe.com/tw/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)新增至您的結構描述。新增後，您可以在 Web SDK 中使用 `xdm` 物件填入此結構描述，將資料傳送至報告套裝。當資料抵達 Edge Network 時，系統會將 XDM 物件轉換為 Adobe Analytics 能夠理解的格式。

請參閱 [XDM 物件變數對應至 Adobe Analytics](xdm-var-mapping.md)，以取得 XDM 欄位及其如何對應至 Analytics 變數的完整參考資料。

>[!TIP]
>
>如果您計畫未來移轉至 [Customer Journey Analytics](https://experienceleague.adobe.com/tw/en/docs/analytics-platform/using/cja-landing)，Adobe 建議不要使用 Adobe Analytics 結構描述欄位群組。相反地，Adobe 建議[建立您自己的結構描述](https://experienceleague.adobe.com/tw/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect)，並使用資料流對應來填入所需的 Analytics 變數。透過此策略，在您準備移轉至 Customer Journey Analytics 時，便不會限制在 Prop 與 eVar 的結構描述中。

## `data` 物件

作為使用 `xdm` 物件的替代方式，您可以改用 `data` 物件。資料物件是針對目前使用 AppMeasurement 的實施所設計，讓升級至 Web SDK 變得更加容易。Edge Network 可偵測 Adobe Analytics 專屬欄位的存在，而無需符合結構描述。

請參閱[資料物件變數對應至 Adobe Analytics](data-var-mapping.md)，以取得物件變數欄位及其如何對應至 Analytics 變數的完整參考資料。

## 情境資料變數

您可以使用任何您想要的格式將資料傳送至 Edge Network。任何未自動對應至 `xdm` 或 `data` 物件欄位的欄位，在轉送至 Adobe Analytics 時，皆會以[情境資料變數](/help/implement/vars/page-vars/contextdata.md)的形式包含其中。接著，您必須使用[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，將所需的欄位對應至各自的 Analytics 變數。

例如，如果您有一個如下所示的自訂 XDM 結構描述：

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

接著，這些欄位將成為您在處理規則介面中可用的情境資料索引鍵：

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

特定的情境資料變數的承載大小上限 (包含索引鍵和值) 為 32 KB。您可以透過調整相關欄位，讓 Adobe Analytics 在 [`xdm`](xdm-var-mapping.md) 或 [`data`](data-var-mapping.md) 物件中能夠識別，藉此減少此承載的大小。
