---
title: AMO Meta 廣告點按 ID
description: Adobe Media Optimizer Meta廣告點選ID，用於Adobe Advertising整合。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# AMO Meta 廣告點按 ID

**[!UICONTROL AMO Meta廣告點按識別碼]**&#x200B;是用於Adobe Advertising整合的廣告點按識別碼。 啟用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)整合時，會自動建立維度。 它主要是當作原始追蹤識別碼，而非人類看得懂的報表維度來使用。

## 將資料填入此維度中

此維度會以多種方式收集其值：

* 針對點進流量，資料會從`fbclid`頁面URL[中的](page-url.md)查詢字串引數收集，通常是在廣告驅動流量進入網站的頁面上。
* 當URL不包含追蹤程式碼，但Adobe Advertising JavaScript在前兩分鐘內偵測到點選時，也可擷取點進流量。

## 維度項目

Dimension專案包含由Meta (Facebook)廣告網路產生的廣告點選識別碼。 這些雜湊值的長度可能有所不同，但通常會有數百個字元長。 範例（截斷）值包括：

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
