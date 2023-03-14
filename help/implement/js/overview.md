---
title: 使用JavaScript適用的AppMeasurement實作Adobe Analytics
description: 瞭解如何在不使用標記管理系統的情況下使用 JavaScript 實施 Adobe Analytics。
feature: Implementation Basics
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 51%

---

# 使用JavaScript適用的AppMeasurement實作Adobe Analytics

JavaScript 適用的 AppMeasurement 向來是實施 Adobe Analytics 的常用方法。但由於標記管理系統越來越熱門，所以建議使用 [Adobe Experience Platform 中的標記](../launch/overview.md)。

實施任務的高層級概觀：

![使用AppMeasurement實作Adobe分析概觀](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>任務</b></th><th style="width:20%"><b>更多資訊</b></th>
</tr>

<tr>
<td>1</td><td>確保您 <b>定義報表套裝</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">報表套裝管理員</a></td>
</tr>

<tr>
<td>2</td><td><b>下載AppMeasurement所需的JavaScript程式碼</b> 從代碼管理器。 將檔案解壓縮。</td><td><a href="../../admin/admin/code-manager-admin.md">程式碼管理員</a></td>
</tr>

<tr>
<td>3</td><td><b>新增 <code>AppMeasurement.js</code> 到您網站的範本檔案</b>. 程式碼包含將資料傳送至Adobe所需的程式庫。

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>在中定義設定 <code>AppMeasurement.js</code></b> 變數。Analytics物件實例化時，這些變數可確保資料收集設定正確無誤。

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">設定變數</a></td>
</tr>

<tr>
<td>5</td><td><b>在網站的頁面程式碼中定義頁面層級變數</b>. 這些變數會決定傳送至 Adobe 的特定維度和量度。

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">頁面變數</a></td>
</tr>

<tr>
<td>6</td><td><b>使用將資料傳送至Adobe <code>t()</code> 方法</b>，而所有頁面變數皆已定義。

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t()方法</a></td>
</tr>

<tr>
<td>7</td><td><b>先擴充和驗證您的實施</b>，再將其投入生產。</b></td><td></td>
</tr>

</table>

## 其他資源

- [變數、函數、方法和外掛程式總覽](../vars/overview.md)
