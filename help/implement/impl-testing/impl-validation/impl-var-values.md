---
description: 請確定從伺服器指令碼或程式碼填入的變數無法輸出任何會對值造成干擾的引號。
keywords: Analytics 實施
seo-description: 請確定從伺服器指令碼或程式碼填入的變數無法輸出任何會對值造成干擾的引號。
seo-title: 變數和值
solution: Analytics
title: 變數和值
topic: 開發人員和實施
uuid: 2ff4857a-9451-4794-9146-f417 abd1 d1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 變數和值

請確定從伺服器指令碼或程式碼填入的變數無法輸出任何會對值造成干擾的引號。

例如: 

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

請確定變數的值未超過本文件中所指定的最大限制。多出的字元在資料收集伺服器上會被截斷。這些字元可能會影響到總長度、無謂地增加頻寬，並可能造成其他問題。

產品變數中請勿使用 $、™、®、© 或逗號 (,)。一般而言，這些字元在任何 [!DNL Analytics] 變數中皆無效用，並且可能干擾到解譯或匯出欄位的能力。最理想的作法是將字元限定為前 127 個 ASCII 字元。

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. 請確定所有 [!DNL Analytics] 變數和函數的大小寫都保持不變，如下所示。

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

頁面名稱須區分大小寫，若有差異將產生其他頁面記錄。"Home" 與 "home" 在 [!DNL Analytics] 中是兩個不同的頁面。

>[!NOTE]
>
>無法在報表內結合多個頁面記錄。

請驗證[!UICONTROL 「自訂連結」]報表中有連結的報告資料。請確定傳入 [!UICONTROL tl] 函數中的參數正確無誤。如需[!UICONTROL 自訂連結]的詳細資訊，請參閱 [連結追蹤](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
