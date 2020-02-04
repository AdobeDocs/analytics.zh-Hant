---
title: 變數覆寫
description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# 變數覆寫

變數覆寫可讓您變更單一點擊的Analytics值，而不會影響頁面上的現有變數。

## 工作流程

1. 建立新的JavaScript物件。 物件名稱可以是您想要的任何項目。

   ```js
   var y = new Object();
   ```

2. 為此物件指派有效的Analytics屬性：

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. 將物件當做適當追蹤呼叫中的引數：

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

當追蹤呼叫接收覆寫參數中的物件時，覆寫物件中所有有效值都會覆寫標準Analytics物件中的值。 現有Analytics物件中已定義的變數不受影響。
