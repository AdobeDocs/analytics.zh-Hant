---
title: cookieDomainPeriods
description: （已棄用）協助AppMeasurement判斷當網站最上層網域包含句點時，要將Cookie儲存於何處。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 19%

---


# cookieDomainPeriods

>[!IMPORTANT]
>此變數已遭取代。 如果您使用AppMeasurement v2.26.x或更新版本，或Adobe Analytics擴充功能v1.9.4或更新版本，程式庫會自動偵測網域以設定Cookie。

此 `cookieDomainPeriods` 變數指出最上層網域中含有額外的句號，有助於AppMeasurement判斷應在何處設定Analytics Cookie。 此變數允許AppMeasurement在頂層網域中容納額外的句號，並在正確位置設定Cookie。 如果您的網站最上層網域未包含額外的句號，則不需要此變數。

* 針對 `example.co.uk` 或 `www.example.co.jp` 這類網域，請將此變數設為 `"3"`。
* 針對網域，例如 `example.nsw.gov.au`，將此變數設為 `"4"`.
* 針對網域，例如 `example.com` 或 `products.example.org`，省略設定此變數或將其設為 `"2"`.

>[!TIP]
>
> 使用此變數時請勿將子網域列入考量。例如，請勿在範例 URL `store.toys.example.com` 上設定 `cookieDomainPeriods`。AppMeasurement可辨識Cookie是儲存在 `example.com`，即使在具有許多子網域的URL上也是如此。

若為AppMeasurement v2.26.x或更新版本上的實施， [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie可協助自動判斷正確的Cookie網域。 程式庫會先嘗試寫入包含兩個網域句號的Cookie。 如果設定此Cookie失敗，會再試一次，包括更多網域句號，直到成功為止。 此Cookie在設定後會立即刪除。

## 使用Web SDK的Cookie網域句號

Web SDK會自動判斷設定Cookie的正確網域。

## 使用Adobe Analytics擴充功能的Cookie網域句號

**[!UICONTROL 網域句號]** 是底下的欄位 [!UICONTROL Cookie] 設定Adobe Analytics擴充功能時的摺疊式功能表。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示[!UICONTROL 網域句號]欄位。

將此欄位設為 `3` 只會在包含句號的頂層網域上進行。 否則，此欄位可留空。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的Cookie網域句號

此 `cookieDomainPeriods` 變數是字串，通常設定為 `"3"`，僅針對包含句號的頂層網域。 其預設值為 `"2"`，可容納大多數頂層網域，例如 `.com` 和 `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
