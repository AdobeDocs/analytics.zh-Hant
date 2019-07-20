---
title: 整合模組
seo-title: Adobe Analytics整合模組
description: 整合模組可讓Adobe合作夥伴將其資料收集工作整合至您的組織。
seo-description: 整合模組可讓Adobe合作夥伴將其資料收集工作整合至您的組織。
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# 整合模組

整合模組可讓Adobe合作夥伴將其資料收集工作整合至您的組織。此項整合提供雙向資料連線的機會。通常，使用Integrate模組是由Adobe合作夥伴驅動。

> [!NOTE] 在實施中請求合作夥伴資料，可以提高頁面載入與傳送給Adobe資料收集伺服器的資料之間的延遲。如果訪客在傳送資料之前載入了新頁面，則不會記錄該頁面。

## 整合模組工作流程

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. 傳回JSON物件。
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. 傳送影像請求給 Adobe 資料收集伺服器。

## 整合模組實作

與Adobe合作夥伴合作的組織可以使用這些步驟成功開始使用整合模組。

### 取得整合模組代碼

取得模組代碼需要具有產品管理員存取權的使用者，或屬於產品描述檔的使用者，可存取代碼管理器。所有實施方法(包括Adobe Experience Platform Launch)的模組代碼方法都相同。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 按一下右上方的方形圖示，然後按一下彩色的Analytics標誌。
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. 下載最新的JavaScript AppMeasurement程式庫。
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### 將Integrate模組置於您的實作中

在您的網站上實施Integrate模組需要存取Adobe Experience Platform Launch。如果您使用舊版JavaScript實施，則必須存取組織的網站原始碼。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. 按一下您要編輯的Launch屬性。
3. 按一下「延伸模組」標籤，然後按一下Adobe Analytics下的「設定」。
4. 開啓「使用自訂程式碼設定追蹤器」，然後按一下「&lt;/&gt;開啓編輯器」。
5. 將「整合模組」程式碼貼到程式碼模型視窗中。完成後，按一下「儲存」。

## 整合模組方法

在實施整合模組後，請使用這些方法來設定並接收所需Adobe合作夥伴的資料。

### add

`add` 此方法可個體化合作夥伴物件，在合作夥伴系統與您的實施之間共用資料時，這可做為變數資料的中介存放區。所有整合都需要此方法。如果在單一實施中使用多個合作夥伴，則必須針對每個獨特合作夥伴使用個別的合作夥伴物件。

```JavaScript
s.Integrate.add("<partner_name>");
```

您的組織通常會與Adobe合作夥伴合作判斷合作夥伴名稱的價值。

### 信標

`beacon` 方法會建立影像請求，並將其指向指定的URL。這些影像請求與標準影像請求不同。信標方法通常會傳送資料給Adobe合作夥伴，而非Adobe資料收集伺服器。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

您的組織通常會與Adobe合作夥伴合作判斷合作夥伴名稱的價值。URL中包含的查詢字串是選擇性的，且取決於合作夥伴。Integration模組自動包含包含隨機數字的查詢字串，以防止瀏覽器快取。

### delay

Adobe目前正與內部團隊合作，以取得此種方式。

### get

`get` 此方法可讓用戶端匯入合作夥伴變數，並將其儲存在合作夥伴物件中。資料在合作夥伴物件中後，就可以指派給Analytics變數，並在影像請求中傳送。此方法會呼叫URL，URL會指向包含所需資料的JSON物件。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **合作夥伴名稱：** 您的組織通常會與Adobe合作夥伴合作判斷合作夥伴名稱的價值。
* **JSON物件的URL：** JSON物件的URL，其中包含要併入影像要求的合作夥伴變數。
* **查詢字串參數：** 用來識別合作夥伴系統中組織的合作夥伴帳戶資訊。Adobe合作夥伴會使用此資訊來識別您的資料集。

Integrate模組會自動新增更多查詢字串至URL。var查詢字串指定模組期望來自合作夥伴的JSON物件名稱。也會新增隨機數字，以防止瀏覽器快取。

### 準備就緒

Adobe目前正與內部團隊合作，以取得此種方式。

### useVar

`useVars` 此方法可讓用戶端與Adobe合作夥伴共用變數值。

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

您的組織通常會與Adobe合作夥伴合作，判斷合作夥伴名稱的值以及合作夥伴使用的變數。

### setVars

`setVars` 此方法可讓用戶端使用擷取的合作夥伴資料填入Analytics變數。Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

您的組織通常會與Adobe合作夥伴合作，判斷合作夥伴名稱的值以及合作夥伴使用的變數。

### 指令碼

`script` 此方法可讓Adobe合作夥伴在滿足特定條件時，從合作夥伴網站呼叫額外JavaScript(例如，如果已設定促銷活動變數)。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

您的組織通常會與Adobe合作夥伴合作判斷合作夥伴名稱的價值。URL中包含的查詢字串是選擇性的，且取決於合作夥伴。Integration模組自動包含包含隨機數字的查詢字串，以防止瀏覽器快取。
