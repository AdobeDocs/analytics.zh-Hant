---
title: 整合模組
description: 整合模組可讓 Adobe 合作夥伴將其資料收集成果與您的組織加以整合。
feature: Appmeasurement Implementation
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 98%

---

# 整合模組

整合模組可讓 Adobe 合作夥伴將其資料收集成果與您的組織加以整合。此整合可提供雙向資料連線的機會。整合模組的使用通常是由 Adobe 合作夥伴推動。

>[!NOTE]
>
> 在實作中要求提供合作夥伴資料可增加頁面載入與傳送至 Adobe 資料收集伺服器之資料間的延遲時間。如果訪客在傳送資料前載入新頁面，則不會記錄該頁面。

## 整合模組工作流程

1. 您的網站訪客會載入頁面，為合作夥伴資料發起 `get` 要求。
2. Adobe 合作夥伴會收到 `get` 要求，並將適當的變數封裝在 JSON 物件中。系統會傳回 JSON 物件。
3. 網站會收到 JSON 物件，並呼叫 `setVars` 以將 JSON 物件中所包含的資訊指派給 Adobe Analytics 變數
4. 傳送影像要求給 Adobe 資料收集伺服器。

## 整合模組實作

與 Adobe 合作夥伴合作的組織可利用這些步驟，成功開始使用整合模組。

### 取得整合模組程式碼

若要取得模組程式碼，使用者必須有產品管理員存取權，或屬於某個可存取代碼管理器的產品設定檔。對於所有實作方法 (包括 Adobe Experience Platform 中的標記)，取得模組程式碼的方法都是相同的。

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
1. 在頂端導覽區域中，按一下「**[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 代碼管理器]**」。
1. 下載最新 JavaScript AppMeasurement 資料庫。
1. 下載後，將檔案解壓縮，然後找出 `AppMeasurement_Module_Integrate.js`。

### 將整合模組放置在實作中

若要在網站上實作整合模組，您必須擁有Adobe Experience Platform Data Collection的存取權。 如果您使用舊版 JavaScript 實作，則需要存取貴組織的網站原始碼。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下您要編輯的標記屬性。
1. 按一下「擴充功能」標記，然後按一下 Adobe Analytics 下方的設定。
1. 開啟「使用自訂程式碼設定追蹤器」摺疊式功能表，然後按一下「&lt;/> 開啟編輯器」。
1. 將整合模組程式碼貼到程式碼模組視窗中。完成後，請按一下儲存。

## 整合模組方法

實作整合模組後，請使用這些方法設定該模組，以從您想要的 Adobe 合作夥伴傳送及接收資料。

### add

`add` 方法可具現化合作夥伴物件，可在合作夥伴系統與實作之間分享資料時，做為變數資料的中繼儲存。所有整合都必須採用此方法。若在單一實作中使用多個合作夥伴，則必須針對每個唯一合作夥伴使用個別的合作夥伴物件。

```JavaScript
s.Integrate.add("<partner_name>");
```

組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值。

### beacon

`beacon` 方法會建立影像要求，並將其指向指定的 URL。這些影像要求與標準影像要求不同。信標方法通常會將資料傳送至 Adobe 合作夥伴，而不是傳送至 Adobe 資料收集伺服器。

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值。URL 中包含的查詢字串是選用字串，且取決於合作夥伴。整合模組會自動納入包含隨機編號的查詢字串，以防止瀏覽器進行快取。

### delay

Adobe 內部團隊正在彼此合作，以提供說明此方法的相關文件。

### get

`get` 方法可讓用戶端匯入合作夥伴變數，並將其儲存在合作夥伴物件中。一旦資料進入合作夥伴物件中，即可將資料指派給 Analytics 變數，並在影像要求中傳送。此方法會呼叫 URL，指向包含所需資料的 JSON 物件。

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **合作夥伴名稱：**&#x200B;組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值。
* **JSON 物件的 URL：**&#x200B;包含要併入影像要求之合作夥伴變數的 JSON 物件的 URL。
* **查詢字串參數：**&#x200B;可在合作夥伴系統中識別您的組織的合作夥伴帳戶資訊。Adobe 合作夥伴會使用此資訊來識別資料集。

整合模組會自動將更多查詢字串新增至此 URL。變數查詢字串會指定模組預計要從合作夥伴傳回的 JSON 物件名稱。您也可以新增隨機數字，以防止瀏覽器進行快取。

### 已就緒

Adobe 內部團隊正在彼此合作，以提供說明此方法的相關文件。

### useVars

`useVars` 方法可讓用戶端與 Adobe 合作夥伴分享變數值。

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值以及合作夥伴使用的變數。

### setVars

`setVars` 方法可讓用戶端使用擷取的合作夥伴資料填入 Analytics 變數。合作夥伴資料可能是 `get` 方法、靜態指派或使用資料填入合作夥伴物件之任何其他機制的結果。

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值以及合作夥伴使用的變數。

### 指令碼

在符合某些條件的情況下 (例如，若已設定促銷活動變數)，`script` 方法可讓 Adobe 合作夥伴從合作夥伴網站呼叫其他 JavaScript。

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

組織通常會與 Adobe 合作夥伴合作，決定合作夥伴名稱的值。URL 中包含的查詢字串是選用字串，且取決於合作夥伴。整合模組會自動納入包含隨機編號的查詢字串，以防止瀏覽器進行快取。
