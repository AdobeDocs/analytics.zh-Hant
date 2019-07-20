---
description: 依使用者類型劃分路徑，是您在試圖瞭解特定使用者類型在您的網站上依循何種途徑時常會提出的要求。
keywords: Analytics 實施
seo-description: 依使用者類型劃分路徑，是您在試圖瞭解特定使用者類型在您的網站上依循何種途徑時常會提出的要求。
seo-title: 依使用者類型區分路徑
solution: Analytics
title: 依使用者類型區分路徑
topic: 開發人員和實施
uuid: 5c298f39-381d-453b-a608-109e3276 b361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 依使用者類型區分路徑

依使用者類型劃分路徑，是您在試圖瞭解特定使用者類型在您的網站上依循何種途徑時常會提出的要求。

您可以將使用者類型和頁面名稱串連到 [!UICONTROL sprop] 中，然後對 [!UICONTROL sprop] 啟用路徑分析。

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. 您需要在每個頁面上區分這兩種使用者類型，並將這些值放入您指定的 [!UICONTROL sprop] 中。prop 在填入時應會如下所示: 

```js
 s.prop1=”Registered : “ + s.pageName;
```

若使用者是註冊使用者，且瀏覽了首頁，則 prop 中的值會顯示如下: 

```js
 “Registered : Home Page”
```

若使用者點進名為「頁面 2」的另一個頁面，該頁面上的值會顯示如下: 

```js
 “Registered : Page 2”
```

在開啟[!UICONTROL 「路徑分析」]的情況下，這兩個值會接連出現。若您想瞭解註冊使用者離開首頁後的移動路徑，請在其中一個路徑報表中找出「註冊: 首頁」一值，然後檢視他們所瀏覽的下一個頁面。在此案例中，他們接下來進入了「頁面 2」。
