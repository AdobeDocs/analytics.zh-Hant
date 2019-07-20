---
description: 相關範例，說明如何在 HTML 範例頁面中使用伺服器產生的影像標記。
keywords: Analytics實作；變數
seo-description: 相關範例，說明如何在 HTML 範例頁面中使用伺服器產生的影像標記。
seo-title: 程式碼範例
solution: Analytics
title: 程式碼範例
topic: 開發人員和實施
uuid: 47e5e82c-clib2-4912-919b-720b2 ee852 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 程式碼範例

相關範例，說明如何在 HTML 範例頁面中使用伺服器產生的影像標記。

下表列出範例中所使用的值。

| 變數 | 值 |
|---|---|
| pageName | 訂購確認 |
| 目前的 URL | https://www.somesite.com/cart/confirmation.asp |
| 事件 | purchase,event1 |
| c1 | Registered |
| purchaseID | 0123456 |
| 產品 | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| 隨機數字 | 123456 |

## 範例 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

下列範例顯示伺服器端的影像標記。強調顯示的隨機數字會防止影像快取。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## 範例 2 {#section_726D12029583428BA853043F988ED1B8}

下列範例顯示基本 JavaScript 影像標記。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

