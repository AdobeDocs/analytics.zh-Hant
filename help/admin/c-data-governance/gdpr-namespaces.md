---
description: 您要搜尋的每個ID都會指派一個命名空間，此為自訂字串，可識別所有報表套裝中所有變數使用該ID的變數。
title: 命名空間
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 命名空間

您要搜尋的每個ID都會指派一個命名空間，此為自訂字串，可識別所有報表套裝中所有變數使用該ID的變數。

當您提供 ID 用於資料隱私權請求時，命名空間字串可識別您要搜尋的欄位。提交資料隱私權請求時，該請求會包含 JSON 區段，用以指定用於請求的資料主體 ID。資料主體的單一要求中可包含多個ID。 JSON 包含以下項目：

* 包含namespace字串的「namespace」欄位。
* 「類型」欄位，適用於大部分Adobe Analytics請求，其中包含值「analytics」。
* 「值」欄位，包含Analytics應在每個報表套裝的關聯命名空間變數中搜尋的ID。

如需更多詳細資料，請參閱 [Experience Cloud 資料隱私權 API 文件](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/technical_overview/privacy_service_overview/privacy_service_overview.md)。

## Cookie ID

舊版 Analytics 追蹤 Cookie，亦稱為 Adobe Analytics ID (AAID)：

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

該值必須指定為兩個以破折號分隔的十六進位數字。 所有字母字元的十六進位數字都必須使用大寫指定。 十六進位值不應具有任何前導零(請注意與在不建議使用的表單中指定的相同值（前導零是必需的）。

您也可以使用 `"namespaceId": 10` (而非 `"namespace": "AAID"`)，這樣就能看到其他幾種 Adobe 產品使用該表單。

## 舊版 Analytics 追蹤 Cookie：已廢止的形式

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

已廢止的形式：

該值應指定為兩個16位十六進位數字或兩個19位十進位數字。 數字應以破折號、底線或冒號分隔。 若數字的位數不足，應於開頭以零補足。

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

>[!NOTE] Experience Cloud ID (ECID) 先前稱為 Marketing Cloud ID (MCID)，現在有些文件還是會以舊名指稱。
>
>這些是 Analytics 支援的 ID 中，唯一使用「type」值而非「analytics」值的 ID。

若這些 Cookie ID 的數值部分格式未遵照上述該 ID 的格式，則資料隱私權請求會失敗，並產生「數值格式有誤」錯誤。

大部分情況下，您會最常使用新的[隱私權 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm)收集這些 Cookie ID，這會自動為 JSON ID 提供所有相關索引鍵值配對。

此 JavaScript 程式碼會使用除了上述 (命名空間、類型、值) 之外的其他索引鍵值配對填入 JSON，不過以上所列欄位是 Analytics 資料隱私權處理程序中最重要的欄位，也是您以其他方式收集 ID 時唯一需要提供的項目。

## 自訂訪客 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

自訂訪客ID也預先定義了命名空間。

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

對於自訂流量或轉換變數 (屬性或 eVar) 中的 ID，請使用 ID-DEVICE 或 ID-PERSON 標籤標記變數，然後將您自己的命名空間名稱指派給該類型 ID。請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](gdpr-labels.md)。

您也可以看到先前為其他變數或報表套裝定義的命名空間，並重複使用其中一個，如此，儲存該類型ID的所有報表套裝都可輕鬆使用相同的命名空間。 您也可以為報表套裝中的多個變數指派相同的命名空間。 例如，有些客戶會將CRM ID儲存在流量變數和轉換變數中（視頁面而定，有時會儲存在其中一個或另一個或兩者），而且他們可以將命名空間「CRM ID」指派給兩個變數。

>[!TIP] 將命名空間指定給資料隱私權 API 時，除非該命名空間是在套用 ID-DEVICE 或 ID-PERSON 標籤時指定的命名空間，否則請避免使用簡單易記的變數名稱 (報表 UI 所顯示的名稱)，也不要使用變數的號碼 (如 eVar12)。使用命名空間而非簡單易記的名稱，這樣能促使同一個使用者身分識別區塊為多個報表套裝指定正確的變數。例如 ID 位於部分報表套裝的其他 eVar，或是易記名稱不符時 (像是特定報表套裝已本地化的易記名稱)。

>[!CAUTION] 系統會保留命名空間「visitorId」和「customVisitorId」，以識別 Analytics 舊版追蹤 Cookie 和 Analytics 客戶的訪客 ID。請勿將這些命名空間用於自訂流量或轉換變數。

如需詳細資訊，請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](/help/admin/c-data-governance/gdpr-labels.md)。
