---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# visitorNamespace

 變數可用來識別 Cookie 設定所在的網域。


<!-- 

visitorNamespace.xml

 -->

如果 JavaScript 檔案中使用了 *`visitorNamespace`*，請勿將其刪除或更改。如果 *`visitorNamespace`* 有所變更，則 Analytics 中報告的所有訪客都可能變成新訪客。訪客的歷史記錄會與目前和後續的流量失去連結。未經 Adobe 代表許可，請勿更改此變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | ns | 不適用 | "" |

Analytics 會使用 Cookie 對進入您的網站的訪客進行唯一識別。若未使用 *`visitorNamespace`*，Cookie 則會與 2o7.net 相關聯。若已使用 *`visitorNamespace`*，則 Cookie 會與 2o7.net 的子網域相關聯。瀏覽您網站的所有訪客均應有各自關聯至相同網域或子網域的 Cookie。

之所以使用  *`visitorNamespace`* 變數，是為了避免發生超出瀏覽器 Cookie 限制的狀況。Internet Explorer 會有每個網域 20 個 Cookie 的限制。藉由使用  *`visitorNamespace`* 變數，其他公司的 Analytics Cookie 就不會與您的訪客的 Cookie 發生衝突。

**語法和可能的值** {#section_EE247FE371784CA4B6058182181F3EA1}

*`visitorNamespace`* 的值必須由 Adobe 提供，且是不含逗號、句號、空格或特殊字元的 ASCII 字元字串。

```js
s.visitorNamespace="company_specific_value"
```

**跨報表套裝的訪客識別** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

若未指定 `visitorNamespace`，則公司內的每個報表套裝都會收到寫入為 `s_vi_[random string]` 的各自訪客 ID Cookie。如果有指定 `visitorNamespace`，將對所有傳送資料至所指定之 `s_vi` 的報表套裝，使用相同的 `trackingServer` Cookie。如果有實施多套裝標記，請務必指定訪客命名空間，好讓每個報表套裝使用相同的 Cookie。

**範例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**組態設定** {#section_1128A2531ECC43DFA6749ECC21F050A2}

無
