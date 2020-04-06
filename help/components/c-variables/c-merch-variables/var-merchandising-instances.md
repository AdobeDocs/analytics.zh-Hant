---
description: 說明如何計算銷售變數的例項。
keywords: Analytics Implementation
title: 銷售變數的例項
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 銷售變數的例項

說明如何計算銷售變數的例項。

銷售變數目前不支援例項。 如果您注意到報表中包含銷售變數的例項，表示eVar設定在產品字串以外的某些位置，不應視為所選銷售變數的實際例項計數。

如果您使用「轉換變數語法」，則每次設定變數時都會計算一個例項。 不過，除非每次設定變數時符合下列條件，否則例項會歸因於「無」：

* 已設定綁定事件。
* 產品變數已設定。
* 銷售eVar有值。

例如，eVar1 的下列例項會分配給「戶外：滑雪鏡」：

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

不過，在下列範例中，eVar1 的下列例項會分配給「無」，因為在設定 eVar 時所有條件都不符合 (沒有綁定事件也未設定產品變數)：

瀏覽的第 1 頁：

```js
s.eVar1="Outdoors:Ski Goggles"
```

瀏覽的第 2 頁：

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

若您在未發生系結事件的頁面上設定eVar值，或在產品字串中設定eVar值而未設定系結事件，則會配置至「無」。

>[!NOTE] 在銷售變數上計算例項的功能目前正在審核中，已排定在未來發行中進行變更。

