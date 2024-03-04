---
title: cookieDomainPeriods
description: 如果您的網域尾碼有句號，AppMeasurement 便可瞭解要儲存 Cookie 的網域。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

AppMeasurement 會查看網域和網域尾碼來判斷其 Cookie 位置。針對類似 `example.com` 的網域，AppMeasurement 會將 Cookie 設定在正確的位置。不過，若為其他網域，以 `example.co.uk` 為例，AppMeasurement 可能會錯誤地在 `co.uk` 上設定 Cookie。大部分的瀏覽器會拒絕在此無效網域上設定的 Cookie，造成訪客識別問題。

`cookieDomainPeriods` 變數可協助 AppMeasurement 判斷 Analytics Cookie 的設定位置，方法是對外呼叫網域尾碼有一個額外的句號。此變數可讓 AppMeasurement 在網域尾碼中容納額外的句號，並在正確的位置設定 Cookie。

* 針對 `example.com` 或 `www.example.com` 這類網域，不需要設定此變數。如有需要，您可將此變數設為 `"2"`。
* 針對 `example.co.uk` 或 `www.example.co.jp` 這類網域，請將此變數設為 `"3"`。


>[!IMPORTANT]
>
> 使用此變數時請勿將子網域列入考量。例如，請勿在範例 URL `store.toys.example.com` 上設定 `cookieDomainPeriods`。依預設，AppMeasurement 會辨識 Cookie 應儲存在 `example.com` 上，即使在具有許多子網域的 URL 上亦然。


## Cookie網域句號、第三方Cookie和舊版訪客身分識別

唯有當您使用舊版Adobe Analytics訪客身分識別(而非建議的Experience Cloud身分識別服務)時，才會使用下列專案的隱含或明確設定： `cookieDomainPeriods` 可能會對識別訪客的方式造成影響，具體取決於是否封鎖第三方Cookie。

下表說明四種可能的情況。

| 情境 | `cookieDomainPeriods` 設定是…… | 第三方Cookie遭到封鎖？ | 使用舊版Adobe Analytics訪客身分識別服務時的結果 |
|:---:|---|---|---|
| 1 | <span style="color:green">正確</span> | 否 | 訪客的識別方式為 `s_vi` cookie，設定伺服器端。 |
| 2 | <span style="color:green">正確</span> | 是 | 以遞補內容識別訪客 `s_fid` Cookie，設定使用者端（第一方頁面網域）。 |
| 3 | <span style="color:red">不正確</span> | 否 | 系統會根據使用者代理程式和IP位址的組合，以遞補識別碼來識別訪客。 <br/>AppMeasurement會強制將Cookie設定為第三方Cookie。<br/> 此 `s_vi` Cookie的設定條件可能為 `cookieDomainPeriods` 未正確傳輸。 |
| 4 | <span style="color:red">不正確</span> | 是 | 系統會根據使用者代理程式和IP位址的組合，以遞補識別碼來識別訪客。<br/>AppMeasurement會強制將Cookie設定為第三方Cookie，但遭到封鎖，因此不會設定任何Cookie。 |

>[!CAUTION]
>
>您可能不小心設定了 `cookieDomainPeriods` <span style="color:red">不正確</span> (保留預設值 `"2"`)而使用網域(例如 `example.co.uk`. 這種隱含的不正確設定會導致您在案例3或4之後識別訪客。
>
>AppMeasurement版本2.26.x或更新版本設定 `cookieDomainPeriods` 自動使用正確的值，所以僅情境1或2為可能。 當您更新至AppMeasurement 2.26.x版或更新版本時，雖然目前無法正確識別訪客（案例3或4），但更新將具有重大影響。
>
>* 訪客識別碼正在重設，且訪客將顯示為新訪客。 無法將新活動連結至先前的訪客識別碼。
>* 已設定Cookie （例如用於連結追蹤或Activity Map）。`s_sq` Cookie)，導致報表中突然出現差異。
>
>正確設定時 `cookieDomainPeriods` 將能改善AppMeasurement與Analytics功能，建議您評估升級您的AppMeasurement程式庫而導致的變更，是否會影響您。
>
> 另請參閱 [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=en) 以取得有關CookieAppMeasurement使用的詳細資訊。

## 使用Web SDK的Cookie網域句號

若無此變數，Web SDK便可判斷正確的Cookie儲存網域。

## 使用Adobe Analytics擴充功能的Cookie網域句號

「網域週期」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示[!UICONTROL 網域句號]欄位。

僅針對尾碼中包含句號的網域將此欄位設為 `3`。其他網域可將此欄位保留空白。

## 程式碼AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的Cookie網域句號

您可以設定 `cookieDomainPeriods` 變數中設定，該變數位於AppMeasurement Javascript程式庫或Analytics擴充功能的自訂程式碼編輯器中。

`cookieDomainPeriods` 變數為字串，通常僅針對尾碼中包含句號的網域設為 `"3"`。其預設值為 `"2"`，適用於大部分網域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
