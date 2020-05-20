---
title: 變數覆寫
description: 「變數覆寫」可讓您變更單一追蹤或追蹤連結呼叫的變數值。
translation-type: ht
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# 變數覆寫

變數覆寫可讓您變更單一點擊的 Analytics 值，而不會影響頁面上的現有變數。

## 工作流程

1. 建立新的 JavaScript 物件。物件名稱可以是您想要的任何名稱。

   ```js
   var y = new Object();
   ```

2. 將有效的 Analytics 屬性指派給此物件：

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. 在適當的追蹤呼叫中將物件當做引數：

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

當追蹤呼叫接收覆寫參數中的物件時，覆寫物件中的所有有效值都會覆寫標準 Analytics 物件中的值。現有 Analytics 物件中已定義的變數則不受影響。
