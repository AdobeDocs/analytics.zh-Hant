---
title: AMO Meta廣告點選ID
description: Adobe Media Optimizer Meta廣告點選ID，用於Adobe Advertising整合。
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 3%

---

# AMO Meta廣告點選ID

**[!UICONTROL AMO Meta廣告點按識別碼]**&#x200B;是用於Adobe Advertising整合的廣告點按識別碼。 啟用[Analytics for Advertising](https://experienceleague.adobe.com/zh-hant/docs/advertising/integrations/analytics/overview)整合時，會自動建立維度。 它主要是當作原始追蹤識別碼，而非人類看得懂的報表維度來使用。

## 將資料填入此維度中

此維度會以多種方式收集其值：

* 針對點進流量，資料會從[頁面URL](page-url.md)中的`fbclid`查詢字串引數收集，通常是在廣告驅動流量進入網站的頁面上。
* 當URL不包含追蹤程式碼，但Adobe Advertising JavaScript在前兩分鐘內偵測到點選時，也可擷取點進流量。

## 維度項目

Dimension專案包含由Meta (Facebook)廣告網路產生的廣告點選識別碼。 這些雜湊值的長度可能有所不同，但通常會有數百個字元長。 範例（截斷）值包括：

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
