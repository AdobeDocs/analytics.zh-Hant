---
title: pageName
description: 網站上各個頁面的名稱。
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UVcun7asSJzB20Q4TD5EAqt1-M1OY4VUhH--rEJRdc4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 86%

---

# pageName

`pageName` 變數通常會儲存指定頁面的名稱。 這個變數有助於判斷哪些個別頁面最受歡迎。 此變數會填入「[頁面](/help/components/dimensions/page.md)」維度。

如果您未在指定頁面追蹤呼叫上設定此變數，系統會改用 [`pageURL`](pageurl.md) 變數。

>[!NOTE]
>
>Adobe 資料收集伺服器會從所有 [連結追蹤](/help/implement/vars/functions/tl-method.md) 影像要求中移除此維度。 如果您想要此點擊出現在連結追蹤點擊中，請考慮將維度複製到 [eVar](evar.md)。

## 使用網頁SDK的頁面名稱

頁面名稱會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.name`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.pageName`

## 使用Adobe Analytics擴充功能的頁面名稱

您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面名稱，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設定為 Adobe Analytics，並將[!UICONTROL 「動作類型」]設定為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「頁面名稱」]區段。

您可以將頁面名稱設為任何字串值，包括資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.pageName

`s.pageName` 變數是字串，通常包含頁面的名稱。 其最大值為 100 個位元組；超過上限的值會遭到截斷。 此處的截斷包含當此變數為空白時回溯為 `pageURL` 的情況。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
