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


# mediaLength

 變數會指定所要播放之媒體的總長度。


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 整個 pev3 要求沒有大小上限 - 大小會限定為瀏覽器的 URL 長度限制。 </td> 
   <td> pev3 </td> 
   <td> 視訊逗留時間; <p>已檢視的視訊分段 </p> </td> 
   <td> 無 </td> 
  </tr> 
 </tbody> 
</table>

**語法和可能的值** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**autoTrack 方法:**

若使用 [!UICONTROL s.Media.autoTrack]，則無須明確實施   [!UICONTROL mediaLength] variable does not need to be implemented explicitly. 這會由「JavaScript 適用的 AppMeasurement」程式碼自動決定。

**手動追蹤方法:**

語法:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能的值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**範例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、問題和提示** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* 只有在無法使用 [!UICONTROL s.Media.autoTrack] = true 來追蹤播放器時，才須呼叫媒體追蹤方法。
* 若未使用 [!UICONTROL autoTrack] 進行追蹤，請確實設定長度 (以秒為單位)。

