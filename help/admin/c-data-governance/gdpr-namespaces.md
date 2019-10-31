---
description: 命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。
seo-description: 命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。
seo-title: 命名空間
title: 命名空間
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 命名空間

命名空間是一組自訂字串，可用來在所有報表套裝的任何變數中識別 ID，您要搜尋的每個 ID 都會有一個指定的命名空間。

命名空間字串用於識別您在提供ID做為資料隱私權要求的一部分時所要搜尋的欄位。 提交「資料隱私權」請求時，請求將包含JSON區段，指定要用於請求的資料主體ID。 您可以納入多個 ID 做為資料主體的單一請求的一部分。JSON 包含以下項目:

* 具有命名空間字串的「namespace」欄位。
* 大部分 Adobe Analytics 請求的「type」欄位，其中具有「analytics」這個值。
* 具有 ID 的「value」欄位，該 ID 是 Analytics 在每個報表套裝的相關聯命名空間變數中搜尋的目標。

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

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

您也可以使用 `"namespaceId": 10` (而非 `"namespace": "AAID"`)，這樣就能看到其他幾種 Adobe 產品使用該表單。

## 舊版 Analytics 追蹤 Cookie: 已廢止的形式

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

已廢止的形式:

指定值時應採用兩組 16 位數十六進位數字，或兩組 19 位數十進位數字。數字之間應以破折號 (-)、底線 (_) 或冒號 (:) 區隔。如果其中一個數字沒有足夠的位數，則應添加前導零。

## 身分識別服務 Cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

指定值時必須採用 38 位數十進位數字。如果您是從 Data Warehouse 報表或資料摘要的「mcvisid\_high/low」或「post\_msvisid\_high/low」兩欄擷取數字，必須將這兩組數字以零補滿 19 位數，然後以數值高者在前的方式串聯這兩組值。

您也可以使用 `"namespaceId": 4` (而非 `"namespace": "ECID"`)，這樣就能看到其他幾種 Adobe 產品使用該表單。

> [!NOTE]Experience Cloud ID (ECID) 先前稱為 Marketing Cloud ID (MCID)，現在有些文件還是會以舊名指稱。
>
>這些是 Analytics 支援的 ID 中，唯一使用「type」值而非「analytics」值的 ID。

如果這些Cookie ID中任何一個的值部分的格式不符合該ID所描述的格式，則資料隱私權要求將會失敗，並出現錯誤「值格式不正確」。

大部分情況下，您會最常使用新的[隱私權 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm)收集這些 Cookie ID，這會自動為 JSON ID 提供所有相關索引鍵值配對。

除了上述項目（namespace、類型、值）外，此JavaScript程式碼還會填入JSON中其他金鑰／值配對，但上述欄位是Analytics資料隱私權處理的最重要欄位，也是您以其他方式收集ID時唯一需要提供的欄位。

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

對於自訂流量或轉換變數 (屬性或 eVar) 中的 ID，請使用 ID-DEVICE 或 ID-PERSON 標籤標記變數，然後將您自己的命名空間名稱指派給該類型 ID。See [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](gdpr-labels.md)

您也會看到並可重複使用先前為其他變數或報表套裝定義的命名空間，如此即可輕鬆讓儲存該類型 ID 的所有報表套裝都使用相同的命名空間。此外，您也可以指派相同的命名空間給報表套裝中的多個變數。例如，部分客戶會在流量變數和轉換變數中儲存 CRM ID (視頁面而定，有時會儲存在其中一個變數或兩者皆有)，並將「CRM ID」命名空間指派給這兩個變數。

> [!TIP] 在為資料隱私API指定命名空間時，請避免使用變數的好記名稱（顯示在報告UI中的名稱）或變數的編號（例如eVar12），除非這是套用ID-DEVICE或ID-PERSON標籤時指定的命名空間。 使用命名空間而非簡單易記的名稱，這樣能促使同一個使用者身分識別區塊為多個報表套裝指定正確的變數。例如，若ID位於某些報表套裝中的不同eVar，或友好名稱不符（例如友好名稱已本地化為特定報表套裝時）。

> [!CAUTION] 系統會保留命名空間「visitorId」和「customVisitorId」，以識別 Analytics 舊版追蹤 Cookie 和 Analytics 客戶的訪客 ID。請勿將這些命名空間用於自訂流量或轉換變數。

For more information, see [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md)
