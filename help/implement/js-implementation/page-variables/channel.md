---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# channel

 變數通常用於識別網站的某個區域。


<!-- 

channel.xml

 -->

例如，某零售商的網站擁有如電子產品、玩具或服飾等區域。媒體網站可能會有新聞、運動或商業等區段。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | CH | 網站內容 &gt; 網站區域 | "" |

Adobe 建議在每個頁面上填入 channel 變數。您也可以開啟  *`channel`* 和[!UICONTROL 頁面名稱]變數之間的關聯。

當區域擁有一個或多個層級的子區域時，您可在 *`channel`* 變數中顯示這些區域，或使用單獨變數來識別層級。

**語法和可能的值**

```js
s.channel="value"
```

*`channel`* 變數對其值沒有額外限制。

**範例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**缺陷、問題和提示** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

若您的網站包含多個層級，您可以使用 *`hierarchy`* 或其他變數來指定這些層級。*`channel`* 值不具永久性，但在相同頁面上引發的成功事件會認定為 *`channel`* 值。
