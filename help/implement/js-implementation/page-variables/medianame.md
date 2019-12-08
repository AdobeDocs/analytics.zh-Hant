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


# mediaName

此變數會指定視訊或媒體項目的名稱。


<!-- 

mediaName.xml

 -->

此變數只能透過[!UICONTROL 「資料插入 API」]和[!UICONTROL 「完整處理資料來源」]來使用。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 64KB | pev3 | 視訊、下一視訊流量、上一視訊流量、已檢視的視訊區段、視訊逗留時間 | 無 |

**語法和可能的值** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack 方法:**

若使用 [!UICONTROL s.Media.autoTrack]，則無須明確實施  *`mediaName`* 變數。這會由「JavaScript 適用的 AppMeasurement」程式碼自動決定。

**手動追蹤方法:**

語法:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

可能的值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**範例** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**缺陷、問題和提示** {#section_941A445BB52E4063B0F6920E61BB90DE}

* 只有在無法使用 [!UICONTROL s.Media.autoTrack] = true 來追蹤播放器時，才須呼叫媒體追蹤方法。
* 此變數儲存為 mySQL TEXT 變數，以與 VARCHAR(100) 相對照。
