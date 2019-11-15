---
description: 對 .JS 檔案或 HTML 程式碼的任何修改進行測試，是客戶本身的責任。將修改發佈到產品網站前即應完成此測試。
keywords: Analytics Implementation
solution: Analytics
title: 程式碼修改
topic: Developer and implementation
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 程式碼修改

對 .JS 檔案或 HTML 程式碼的任何修改進行測試，是客戶本身的責任。將修改發佈到產品網站前即應完成此測試。

請確定未從放置在 HTML 內的程式碼或 [!DNL .JS] 檔案中移除或更改換行/歸位字元。請確定所有頁面與頁面範本上的 JavaScript 執行正確無誤 (在 Internet Explorer 的「網際網路選項」中選取「進階」標籤，然後按一下「每次出現指令碼錯誤時皆顯示通知」)。

測試錯誤時，請將程式碼貼到預設的 HTML 頁面中，以判斷錯誤是否是因為其他頁面元素/物件而發生的。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

