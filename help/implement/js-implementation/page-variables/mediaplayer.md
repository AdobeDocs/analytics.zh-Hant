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


# mediaPlayer

此變數會指定用來使用視訊或媒體項目的播放器。


<!-- 

mediaPlayer.xml

 -->

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | pev3 | 視訊播放器 | 無 |

**語法和可能的值** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack 方法:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手動追蹤方法:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能的值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**範例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、問題和提示** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

只有在無法使用 s.Media.autoTrack = true 來追蹤播放器時，才須呼叫媒體追蹤方法。

