---
description: 瞭解 s.linkTrackVars 和 s.linkTrackEvents 變數，是成功實施連結追蹤的關鍵。這可讓您傳送使用者動作的自訂變數值。
keywords: Analytics Implementation
title: 使用 s.linkTrackVars 和 s.linkTrackEvents
topic: Developer and implementation
uuid: f6b7019b-987b-4b7d-a446-80205f7cc36c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用 s.linkTrackVars 和 s.linkTrackEvents

瞭解 s.linkTrackVars 和 s.linkTrackEvents 變數，是成功實施連結追蹤的關鍵。這可讓您傳送使用者動作的自訂變數值。

若您實施自訂連結追蹤，並設定了[!UICONTROL 自訂]變數和&#x200B;*`events`*，請確定您的 [!UICONTROL s.linkTrackVars] 變數中包含您傳送之所有變數的逗號分隔清單，包括 *`events`* 變數。請確定 [!UICONTROL s.linkTrackEvents] 包含您所傳送之所有事件的逗號分隔清單。

設定 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 時，並不會實際設定這些變數/事件，而只是讓 [!DNL Analytics] 程式碼準備執行此設定。您還須手動設定這些變數，如下列範例所示: 

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

請注意，事件會列示在 [!UICONTROL s.linkTrackVars] 變數中。可傳送的個別事件會包含在 [!UICONTROL s.linkTrackEvents] 變數中，後續在函數中也會包含於 [!UICONTROL s.events] 內。每個可傳送的變數在後續填入至函數之前，都會列示在 [!UICONTROL s.linkTrackVars] 中。"event9" 也已包含在 [!UICONTROL s.linkTrackEvents] 中，但尚未包含在 [!UICONTROL s.events] 中。此事件並未記錄，但若使用者選擇設定 s.events="event5,event9"，則可加以記錄。

自動檔案下載和[!UICONTROL 退出]連結追蹤的運作方式並不相同。[!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 都包含在標準 [!DNL s_code.js] 檔案中，且都設為「無」。這些變數在 [!DNL s_code.js] 檔案中通常會保留「無」的設定，以便讓自動連結追蹤 (不同於[!UICONTROL 自訂連結追蹤]) 使用您在全域 JavaScript 檔案中設定的 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 值。它們也會在檔案下載或[!UICONTROL 退出]連結受到記錄時，傳送這些變數的現有值。

請考量在頁面載入時 s.channel="Home"，且 s.linkTrackVars="channel" 的 [!DNL s_code.js] 檔案範例。若使用者藉由點按而下載檔案，自動檔案下載追蹤會將資料傳入 [!DNL Analytics] 中，包括對頁面載入設定的 [!UICONTROL s.channel] 值在內。"Home" 會傳入第二次，而導致[!UICONTROL 「網站區段」]報表中的這個值出現頁面檢視資料不實膨脹的情形。

Adobe 強烈建議在全域 JavaScript 檔案中將 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 的設定保留為「無」，而在您的[!UICONTROL 自訂連結追蹤]實施中視需要加以明確設定。
