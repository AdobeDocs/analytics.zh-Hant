---
description: '可協助您回答下列問題: 「使用者透過促銷活動進入我的網站後瀏覽了哪些項目？」'
keywords: Analytics Implementation
title: 依促銷活動或追蹤代碼的路徑分析
topic: Developer and implementation
uuid: eb6e3484-1b40-4ec6-8017-ac1003cdf636
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 依促銷活動或追蹤代碼的路徑分析

可協助您回答下列問題: 「使用者透過促銷活動進入我的網站後瀏覽了哪些項目？」

要回答此問題，您必須特別設定要用於此報表的 [!UICONTROL sprop]。接著，您必須以適當方式建構要填入此 prop 中的資料，使其在路徑分析啟用時能夠具有意義。

在此範例中，您要使用 [!UICONTROL prop1] 作為促銷活動路徑分析 prop。此時，您想要在此 [!UICONTROL sprop] 中填入您在[!UICONTROL 頁面名稱]變數中放入的同一個值。請檢視下列項目: 

```js
s.prop1=s.pageName;
```

除非訪客是從促銷活動點進的，否則您應在所有頁面上執行此動作。若他們是從促銷活動點進的，且位於促銷活動的登陸頁面上，則您會在 prop 中填入促銷活動與[!UICONTROL 頁面名稱]的串連。請檢視下列項目: 

```js
 s.prop1=s.campaign + ' : ' + s.pageName;
```

若他們所點按的促銷活動名為 "banner1234"，而其登陸頁面名為「首頁」，則該 prop 中的值會是「banner1234: 首頁」。在後續的每個頁面上，您都在 prop 中放入[!UICONTROL 頁面名稱]，如前所述。

當使用者點按此促銷活動，且在該次瀏覽中共檢視了四個頁面，則您的 sprop 中會依下列順序出現下列值: 

```js
"banner1234 : Home Page" > "Page 2" > "Page 3" > "Page 4"
```

依此方式在 [!UICONTROL prop1] 中擷取我們的資料，並對此 prop 啟用路徑分析後，此時您即可檢視眾多路徑分析報表之一，以瞭解訪客從促銷活動點進網站後的瀏覽路徑。

您可以指定要作為路徑報表起點的起始頁面。在此案例中，您選取了「banner1234: 首頁」，因為您想瞭解使用者從促銷活動 "banner 1234" 點進後的瀏覽路徑。此報表只是眾多路徑報表之一的範例。
