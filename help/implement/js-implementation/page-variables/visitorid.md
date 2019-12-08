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


# visitorID

訪客可由 變數來識別，或由 IP 位址/使用者代理識別。


<!-- 

visitorID.xml

 -->

*`visitorID`* 最多可達 100 個英數字元，且不可含有連字號。

如果您明確設定自訂 ID，則會優先於其他 ID 方法而使用此自訂 ID。

使用順序如下: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** 最大尺寸** | ** 偵錯器參數** | ** 填充報表** | ** 預設值** |
|---|---|---|---|
| 100 位元組 | vid | 不適用 | "" |

**語法和可能的值** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE]*`visitorID`* 變數不可包含連字號。

**範例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**組態設定** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

無
