---
description: 命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。
seo-description: 命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。
seo-title: 命名空間
title: 命名空間
uuid: cab61844-3209-4980-b14 c-6859de777606
translation-type: tm+mt
source-git-commit: 9362a59afb6a51bd91d8a94ae5750c4d138fc2f7

---


# 命名空間

命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。

當您提供 ID 用於 GDPR 請求時，命名空間字串可識別您要搜尋的欄位。提交 GDPR 請求時，該請求會包含 JSON 區段，用以指定用於請求的資料主體 ID。您可以納入多個 ID 做為資料主體的單一請求的一部分。JSON 包含以下項目:

* 具有命名空間字串的「namespace」欄位。
* 大部分 Adobe Analytics 請求的「type」欄位，其中具有「analytics」這個值。
* 具有 ID 的「value」欄位，該 ID 是 Analytics 在每個報表套裝的相關聯命名空間變數中搜尋的目標。

如需更多詳細資料，請參閱 [Experience Cloud GDPR API 文件](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)。

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## Cookie ID

舊版 Analytics 追蹤 Cookie，亦稱為 Adobe Analytics ID (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

指定值時必須採用兩組十六進位並以破折號 (-) 區隔的數字。所有十六進位數字的字母字元，指定時必須採用大寫。十六進位數值不應以零開頭 (請注意，這與已廢止的形式不同，過去要求開頭為零)。

您也可以使用它， `“namespaceId”: 10` 而不是除了其他之外，您 `“namespace”: “AAID”` 可能會看見某些其他Adobe產品使用該表單。

## 舊版 Analytics 追蹤 Cookie: 已廢止的形式

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

已廢止的形式:

指定值時應採用兩組 16 位數十六進位數字，或兩組 19 位數十進位數字。數字之間應以破折號 (-)、底線 (_) 或冒號 (:) 區隔。若數字的位數不足，應於開頭以零補足。

## Identity Service Cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

指定值時必須採用 38 位數十進位數字。如果您從資料饋送或資料倉庫報表的兩個mcvisid\_ high/low或post/_ minsquid\__ high/low欄提取此數字，您必須將這兩個數字的每個數字零設為19位元，然後先串連這些數字。

您也可以使用： `“namespaceId”: 4` 您可能會看到 `“namespace”: “ECID”` 某些其他Adobe產品使用該表單。

>[!NOTE]
>
>Experience Cloud ID(ECID)先前稱為Marketing Cloud ID(MCID)，在某些現有文件中，該ID仍為該名稱。
>
>這些ID是Analytics支援的唯一ID，使用「analytics」以外的「類型」值。

若這些 Cookie ID 的數值部分格式未遵照上述該 ID 的格式，則 GDPR 請求會失敗，並產生「數值格式有誤」錯誤。

大部分情況下，您會最常使用新的[隱私權 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm)收集這些 Cookie ID，這會自動為 JSON ID 提供所有相關索引鍵值配對。

此 JavaScript 程式碼會使用除了上述 (命名空間、類型、值) 之外的其他索引鍵值配對填入 JSON，不過以上所列欄位是 Analytics GDPR 處理程序中最重要的欄位，也是您以其他方式收集 ID 時唯一需要提供的項目。

## 自訂訪客 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

系統也會為自訂訪客 ID 預先定義命名空間。

## 自訂變數中的 ID

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

對於自訂流量或轉換變數(prop或eVar)中的ID，請使用ID-DEVICE或ID-PERSON標籤來標示變數，然後將您自己的namespace名稱指派給該類型的ID。請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](gdpr-labels.md)。

您也會看到並可重複使用先前為其他變數或報表套裝定義的命名空間，如此即可輕鬆讓儲存該類型 ID 的所有報表套裝都使用相同的命名空間。此外，您也可以指派相同的命名空間給報表套裝中的多個變數。例如，部分客戶會在流量變數和轉換變數中儲存 CRM ID (視頁面而定，有時會儲存在其中一個變數或兩者皆有)，並將「CRM ID」命名空間指派給這兩個變數。

> [!TIP] 請避免在指定GDPR API的命名空間時(例如套用ID-DEVICE或ID-PERSON標籤時指定的namespace)，使用變數的友好名稱(報告UI中顯示的名稱)或變數的數字(例如eVar12)。使用名稱空間而非友好名稱，可讓相同的使用者識別區塊指定多個報表套裝的正確變數。例如，如果ID位於某些報表套裝中的不同eVar中，或好記名稱不符合(例如，在特定報表套裝的友好名稱已本地化時)。

> [!CAUTION] 命名空間「visitorID」和「customVisitorID」會保留下來識別Analytics舊有追蹤Cookie和Analytics客戶訪客ID。請勿針對自訂流量或轉換變數使用這些名稱空間。

如需詳細資訊，請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)。
