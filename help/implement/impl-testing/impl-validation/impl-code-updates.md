---
description: 對 .JS 檔案或 HTML 程式碼的任何修改進行測試，是客戶本身的責任。將修改發佈到產品網站前即應完成此測試。
keywords: Analytics 實施
seo-description: 對 .JS 檔案或 HTML 程式碼的任何修改進行測試，是客戶本身的責任。將修改發佈到產品網站前即應完成此測試。
seo-title: 程式碼修改
solution: Analytics
title: 程式碼修改
topic: 開發人員和實施
uuid: efac045e-15f5-45f6-a21 a-de6 c4 b0 a8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 程式碼修改

對 .JS 檔案或 HTML 程式碼的任何修改進行測試，是客戶本身的責任。將修改發佈到產品網站前即應完成此測試。

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. 請確定所有頁面與頁面範本上的 JavaScript 執行正確無誤 (在 Internet Explorer 的「網際網路選項」中選取「進階」標籤，然後按一下「每次出現指令碼錯誤時皆顯示通知」)。

測試錯誤時，請將程式碼貼到預設的 HTML 頁面中，以判斷錯誤是否是因為其他頁面元素/物件而發生的。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

