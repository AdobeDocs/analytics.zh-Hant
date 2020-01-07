---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.registerPreTrackCallback 和 s.registerPostTrackCallback

這些函數採用參數的形式: callback (函數) 和該函數的參數。例如:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

在註冊 callback 時，系統會利用 `requestUrl` 和任何傳入的參數叫用 callback。這項作業會發生在追蹤呼叫之前或之後，須視用來註冊 callback 的方法而定。

我們無法保證這些 callback 的呼叫順序。在前置函數中註冊的 callback，會在最終的追蹤 URL 建立時叫用。後置 callback 會在追蹤呼叫成功時呼叫 (如果追蹤呼叫失敗，系統不會叫這些函數)。任何以 `registerPreTrackCallback` 註冊的 callback 均不會影響追蹤呼叫。此外，我們不建議在任何已註冊的 callback 中呼叫任何追蹤方法，因為這樣可能會導致無限迴圈。
