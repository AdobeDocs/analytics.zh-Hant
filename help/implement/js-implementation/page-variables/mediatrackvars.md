---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# media.trackVars

 變數可識別哪些變數應隨媒體點擊而傳送。


<!-- 

media_trackVars.xml

 -->

此變數僅適用於 JavaScript 和 [!UICONTROL ActionSource]。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | s.Media.trackVars="None" |

**語法和可能的值** {#section_7374684A7EB34AE685E8C40A66CFD289}

變數名稱，例如 [!UICONTROL propN]、*`eVarN`*、*`events`*、*`channel`* 等。

**範例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**缺陷、問題和提示** {#section_615AE1B696124B00B78F651B03813EAB}

* 即使在 [!UICONTROL trackVars] 中指定 eVar3，它仍會隨媒體點擊傳送。

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

此變數會控制使用 Cookie 和訂閱者 ID 來識別訪客的順序。

<!-- 

mobile.xml

 -->

詳情請參閱[行動網路通訊協定](/help/implement/js-implementation/c-additional-libraries/network-protocols.md)。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 影像 URL 路徑中的 /5/ 或 /1/ | 不適用 | 無 |

**語法和可能的值** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**缺陷、問題和提示** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

將 *`s.mobile`* 變數與 JavaScript Cookie 實施搭配使用時，請使用跨訪客身分識別，減輕訪客流量可能暴增的影響。
