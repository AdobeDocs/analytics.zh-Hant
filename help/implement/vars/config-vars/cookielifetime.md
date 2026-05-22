---
title: cookieLifetime
description: 覆寫 AppMeasurement 所建立 Cookie 的期限。
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Vnia0RzQf6S5-gbgwIlM0WOiSgm2ZOzL24pvIKNgMl4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 63%

---

# cookieLifetime

AppMeasurement 所設定的 Cookie 通常期限為 2 年。 可使用 `cookieLifetime` 變數覆寫 AppMeasurement 所設定 Cookie 的期限。

>[!NOTE]
>
>此變數會影響不重複訪客計數和歸因。 設定此變數時請小心。

## 使用網頁SDK的Cookie期限

Web SDK尚未針對其設定的Cookie存留期提供自訂功能。

## 使用Adobe Analytics擴充功能的Cookie期限

「Cookie期限」是在設定Adobe Analytics擴充功能時，於[!UICONTROL Cookie]設定追蹤器下方的下拉式清單。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL Cookie]摺疊式功能表，這會顯示[!UICONTROL Cookie期限]下拉式清單。

此下拉式清單包含下列值：

* **預設值**：Cookie 會在 2 年後到期。
* **無**：AppMeasurement 不設定 Cookie。
* **作業階段**：Cookie 會在訪客的作業階段結束時到期。
* **秒**：Cookie 會在指定的秒數過後到期。 例如，將此下拉式清單設定為[!UICONTROL 秒]，並將`86400`放入自訂欄位中，便會強制Cookie在24小時後到期。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.cookieLifetime

`s.cookieLifetime` 變數為字串，可決定 AppMeasurement 所設定 Cookie 的期限。

* 如果設為 `SESSION`，AppMeasurement 設定的 Cookie 會在瀏覽器作業階段完成後到期。
* 如果設為 `NONE`，AppMeasurement 不會嘗試設定 Cookie。
* 如果設為整數字串，AppMeasurement 所設定的 Cookie 會在指定秒數過後到期。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
