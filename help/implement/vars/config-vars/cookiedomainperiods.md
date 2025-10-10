---
title: cookieDomainPeriods
description: （已棄用）協助AppMeasurement判斷當網站最上層網域包含句點時，要將Cookie儲存於何處。
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>此變數已遭取代。 如果您使用下列任何一項：
>
>* AppMeasurement v2.26.x或更新版本
>* Adobe Analytics擴充功能v1.9.4或更新版本
>* Adobe Experience Cloud ID服務
>
>此變數不會產生任何效用，因為適用的程式庫會自動偵測要設定Cookie的網域。

`cookieDomainPeriods`變數指出最上層網域中含有額外的句號，協助AppMeasurement判斷應在何處設定Analytics Cookie。 此變數可讓AppMeasurement在頂層網域中容納額外的句號，並在正確位置設定Cookie。 如果您的網站最上層網域未包含額外的句號，則不需要此變數。

* 針對 `example.co.uk` 或 `www.example.co.jp` 這類網域，請將此變數設為 `"3"`。
* 針對類似`example.nsw.gov.au`的網域，將此變數設為`"4"`。
* 針對`example.com`或`products.example.org`等網域，請省略設定此變數或將其設為`"2"`。

>[!TIP]
>
> 使用此變數時請勿將子網域列入考量。例如，請勿在範例 URL `store.toys.example.com` 上設定 `cookieDomainPeriods`。AppMeasurement會辨識Cookie儲存在`example.com`上，即使在具有許多子網域的URL上亦然。

針對AppMeasurement v2.26.x或更新版本上的實作，[`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie是用來協助自動判斷正確的Cookie網域。 程式庫會先嘗試寫入包含兩個網域句號的Cookie。 如果設定此Cookie失敗，會再試一次，包括更多網域句號，直到成功為止。 此Cookie在設定後會立即刪除。

## 使用網頁SDK的Cookie網域句號

網頁SDK會自動判斷設定Cookie的正確網域。

## 使用Adobe Analytics擴充功能的Cookie網域句號

設定Adobe Analytics擴充功能時，**[!UICONTROL 網域週期]**&#x200B;是[!UICONTROL Cookie]摺疊式功能表下的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示[!UICONTROL 網域句號]欄位。

僅針對包含句號的頂層網域將此欄位設為`3`。 否則，此欄位可留空。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的Cookie網域句號

`cookieDomainPeriods`變數是字串，通常設定為`"3"`，只針對包含句點的最上層網域。 其預設值為`"2"`，可容納大部分的頂層網域，例如`.com`和`.org`。

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
