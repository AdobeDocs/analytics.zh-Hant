---
description: 說明如何計算銷售變數的例項。
keywords: Analytics Implementation
title: 銷售變數的例項
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 銷售變數的例項

說明如何計算銷售變數的例項。

例項目前不支援銷售變數。若您在包含銷售變數的報表中發現例項，此表示 eVar 設定於產品字串以外之部分位置，且不應視為已選取銷售變數的正確例項計數。

如果您使用「轉換變數語法」，則每次設定變數時都會計算例項。不過，除非每次設定變數時符合下列條件，否則例項會歸因於「無」:

* 已設定綁定事件。
* 已設定產品變數。
* 銷售 eVar 具有值。

例如，eVar1 的下列例項會分配給「戶外:滑雪鏡」:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

不過，在下列範例中，eVar1 的下列例項會分配給「無」，因為在設定 eVar 時所有條件都不符合 (沒有綁定事件也未設定產品變數):

瀏覽的第 1 頁:

```js
s.eVar1="Outdoors:Ski Goggles"
```

瀏覽的第 2 頁:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

如果在未發生綁定事件的頁面上設定 eVar 的值，或是在沒有綁定事件的產品字串中設定 eVar 值，會發生分配給「無」的情形。

> [!NOTE] 在銷售變數上計算例項的功能目前正在審核中，已排定在未來發行中進行變更。

