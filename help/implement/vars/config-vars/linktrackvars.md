---
title: linkTrackVars
description: 指定要將哪些變數納入連結追蹤影像要求中。
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 60%

---

# linkTrackVars

有些實施不希望將所有變數納入每個連結追蹤影像要求中。 請使用 `linkTrackVars` 和 [`linkTrackEvents`](linktrackevents.md) 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

此變數不適用於頁面瀏覽數呼叫 ([`t()`](../functions/t-method.md) 方法)。

## 使用網頁SDK決定要包含在XDM事件中的變數

網頁SDK不會排除連結追蹤呼叫的某些欄位。 不過，您可在將資料傳送至Adobe之前，使用`onBeforeEventSend`回呼來清除或設定所要的欄位。 如需詳細資訊，請參閱Web SDK檔案中的[全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

## 使用Adobe Analytics擴充功能時連結追蹤呼叫中的變數

此變數會根據介面中設定的變數自動填入後端，因此在使用Adobe Analytics擴充功能的實施中一律會設定。

>[!IMPORTANT]
>
>如果您使用自訂程式碼編輯器設定變數，您也必須使用自訂程式碼在`linkTrackVars`中包含變數。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkTrackVars

`s.linkTrackVars` 變數是字串，其中包含您要納入連結追蹤影像要求 (`tl()` 方法) 中的逗號分隔變數清單。 若要在連結追蹤點擊中納入維度，以下兩個條件必須滿足：

* 設定所需的變數值。 例如，`s.eVar1 = "Example value";`。
* 在 `linkTrackVars` 變數中設定所要的變數。 例如，`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此變數的預設值為空字串。 不過，在「代碼管理器」內由 Adobe 提供的 AppMeasurement 程式碼中，此變數設為 `"None"`。 有效值是任何填入維度的頁面層級變數。

* 如果此變數未定義或設為空字串，*所有*&#x200B;變數都會納入連結追蹤影像要求中。
* 如果此變數設為 `"None"`，*不會*&#x200B;有任何變數納入連結追蹤影像要求中。

>[!TIP]
>
>在此變數中指定變數時，請避免使用 Analytics 物件識別碼 (`s.`)。 例如，`s.linkTrackVars = "eVar1";` 正確，而 `s.linkTrackVars = "s.eVar1";` 不正確。

## 範例

以下連結追蹤函數只會在傳送給 Adobe 的影像要求中納入 `eVar1` (不會納入 `eVar2`)：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
