---
title: 手動將 XDM 資料對應至 Analytics
description: 手動將 XDM 資料從 Experience Platform 對應至 Adobe Analytics
exl-id: 6d973b35-1558-435c-9ae5-80c012d4e7ba
source-git-commit: 73161e10a2f70cd0e874d2c1de6d4f418b25aefb
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 93%

---

# 手動將 XDM 資料對應至 Analytics

Adobe Experience Platform (AEP) Web SDK 的輔助工具可協助您在 Platform 與 Analytics 之間手動對應資料。

對於未自動對應至 Analytics 的 XDM 資料，您可以新增[內容資料](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html?lang=zh-Hant)以比對您的[結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hant)。隨後，Analytics [處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=zh-Hant)將可用它來填入 Analytics 變數。

此外，您也可以使用一組預設的動作和產品清單，以透過[AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)傳送或擷取資料。

## 內容資料

為了供 Analytics 使用，XDM 資料會使用點標記法扁平化，並成為可用的 `contextData`。下列值配對清單顯示 `context data` 的範例：

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "http://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## 處理規則

邊緣網路收集的所有資料都可透過[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html)來存取。在 Analytics 中，您可以使用處理規則將內容資料併入 Analytics 變數中。

以下列規則為例，Analytics 設為會在&#x200B;**內部搜尋詞彙 (eVar2)** 中填入與 **a.x_atag.search.term (內容資料)** 相關聯的資料。

![](assets/examplerule.png)


## XDM 結構

Experience Platform 會使用結構，以一致且可重複使用的方式說明資料結構。藉由定義跨系統的一致資料，將可輕易保留意義，而發揮資料應有的價值。Analytics 內容資料可與結構 (schema) 定義的結構 (structure) 搭配使用。

下列範例說明 [`event` 命令](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant)如何與 `xdm` 選項搭配使用，以透過 AEP Web SDK 傳送和擷取資料。在此範例中，`event` 命令與 [ExperienceEvent 商務詳細資料結構](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md)相符，因此會追蹤 productListItems `name` 和 `SKU` 值：


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

如需使用 AEP Web SDK 追蹤事件的詳細資訊，請參閱[追蹤事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html)。
