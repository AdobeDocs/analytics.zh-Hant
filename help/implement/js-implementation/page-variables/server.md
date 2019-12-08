---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# server

此變數可用來顯示網頁的網域 (以指出訪客進入的網域) 或為頁面提供服務的伺服器 (以供負載平衡快速參考之用)。


<!-- 

server.xml

 -->

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | server | 伺服器 | "" |

若您的網站有多個網域提供相同內容，您可以使用&#x200B;*`server`*&#x200B;變數來追蹤訪客使用了其中的哪些網域。下列 JavaScript 會將頁面的網域填入伺服器變數中。

```js
s.server=window.location.hostname
```

若您要使用伺服器變數提供負載平衡的快速指引，您可以在伺服器變數中放入伺服器名稱或號碼。請檢視下列範例: 

```js
s.server="server 14"
```

雖然[!UICONTROL 「最受歡迎伺服器」]報表可作為負載平衡快速參考，但以此方式測量伺服器負載並不精準。例如，「上一頁」按鈕的流量並不會增加伺服器負載，但卻會顯示於報表中。此報表並不會顯示哪些伺服器提供了影像或大量下載內容。

**語法和可能的值** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

除了標準變數限制以外，*`server`* 變數並無其他限制。

**範例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**組態設定** {#section_969DB379D5BD469FBEE8D505D3000E49}

無

**缺陷、問題和提示** {#section_42A28F9B01574F38891D9D54B411D8FE}

*`server`* 變數可用來顯示哪些網域最多人使用，或哪些伺服器所提供的頁面最多。

