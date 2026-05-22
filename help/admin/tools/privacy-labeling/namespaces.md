---
description: 您想要搜尋的每個ID都會指派名稱空間，名稱空間是自訂字串，可在所有報表套裝使用的任何變數中識別該ID。
title: 命名空間
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
TQID: https://experienceleague.adobe.com/f9Pqs889VWpF4jyxX2GDBVdLyrDqWpHAkcHmDUizoGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 942
ht-degree: 65%

---

# 命名空間

您想要搜尋的每個ID都會指派名稱空間，名稱空間是自訂字串，可在所有報表套裝使用的任何變數中識別該ID。

當您提供 ID 用於資料隱私權請求時，命名空間字串可識別您要搜尋的欄位。 提交資料隱私權請求時，該請求會包含 JSON 區段，以指定用於請求的資料主體 ID。 您可以將多個 ID 納入做為資料主體的單次請求的一部分。 JSON 包含以下項目：

* 包含名稱空間字串的「名稱空間」欄位。
* 針對大多數Adobe Analytics請求，包含「analytics」值的「type」欄位。
* 一個「值」欄位，其中包含Analytics應在每個報表套裝的關聯名稱空間變數中搜尋的ID。

請參閱[CX Enterprise資料隱私權API檔案](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)，以取得詳細資訊和標準識別名稱空間[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/api/appendix#standard-namespaces)的清單。 請參閱[建立存取/刪除工作](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/api/privacy-jobs#access-delete)，以取得範例請求。

## Cookie ID

舊版 Analytics 追蹤 Cookie，亦稱為 Adobe Analytics ID (AAID)：

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

值必須指定為兩個以破折號分隔的十六進位數字。 所有為字母字元的十六進位數字都必須使用大寫來指定。 十六進位值不應有任何前導零（請注意與已棄用形式中指定的相同值不同，其中前導零為必填）。

您也可以使用 `"namespaceId": 10` (而非 `"namespace": "AAID"`)，這樣就能看到其他幾種 Adobe 產品使用該表單。

## 舊版 Analytics 追蹤 Cookie：已廢止的形式

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

此值應指定為兩個16位數的十六進位數字，或兩個19位數的十進位數字。 數字應以破折號、底線或冒號分隔。 若數字的位數不足，應於開頭以零補足。

## 身分識別服務 Cookie

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

指定值時必須採用 38 位數十進位數字。 如果您是從 Data Warehouse 報表或資料摘要的「mcvisid\_high/low」或「post\_msvisid\_high/low」兩欄擷取數字，必須將這兩組數字以零補滿 19 位數，然後以數值高者在前的方式串聯這兩組值。

您也可以使用 `"namespaceId": 4` (而非 `"namespace": "ECID"`)，這樣就能看到其他幾種 Adobe 產品使用該表單。

>[!NOTE]
>
>Experience Cloud ID (ECID) 先前稱為 Marketing Cloud ID (MCID)，現在有些文件還是會以舊名指稱。
>
>這些是 Analytics 支援的 ID 中，唯一使用「type」值而非「analytics」值的 ID。

若這些 Cookie ID 的數值部分格式未遵照上述該 ID 的格式，則資料隱私權請求會失敗，並產生「數值格式有誤」錯誤。

大部分情況下，您會最常使用新的[隱私權 JavaScript](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)收集這些 Cookie ID，這會自動為 JSON ID 提供所有相關索引鍵值配對。

此 JavaScript 程式碼會使用除了上述 (命名空間、類型、值) 之外的其他索引鍵值配對填入 JSON，不過以上所列欄位是 Analytics 資料隱私權處理程序中最重要的欄位，也是您以其他方式收集 ID 時唯一需要提供的項目。

## 自訂訪客 ID

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

該名稱空間也會預先定義給自訂訪客ID。

## 自訂變數中的 ID

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

對於自訂流量或轉換變數 (屬性或 eVar) 中的 ID，請使用 ID-DEVICE 或 ID-PERSON 標籤標記變數，然後將您自己的命名空間名稱指派給該類型 ID。 請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](/help/admin/tools/privacy-labeling/labels.md)。

您也可以檢視您先前為其他變數或報表套裝定義的名稱空間，並重複使用其中一個，好讓所有儲存該型別ID的報表套裝都能輕鬆使用相同的名稱空間。 您也可以將相同的名稱空間指派給報表套裝中的多個變數。 例如，有些客戶會將CRM ID儲存在流量變數和轉換變數中（視頁面而定，變數有時會儲存在其中一個變數中，或是儲存在兩個變數中），而且他們可以將名稱空間「CRM ID」指派給這兩個變數。

>[!TIP]
>
>將命名空間指定給資料隱私權 API 時，除非該命名空間是在套用 ID-DEVICE 或 ID-PERSON 標籤時指定的命名空間，否則請避免使用簡單易記的變數名稱 (報表 UI 所顯示的名稱)，也不要使用變數的號碼 (如 eVar12)。 使用命名空間而非簡單易記的名稱，這樣能促使同一個使用者身分識別區塊為多個報表套裝指定正確的變數。 例如 ID 位於部分報表套裝的其他 eVar，或是易記名稱不符時 (像是特定報表套裝已本地化的易記名稱)。

>[!CAUTION]
>
>系統會保留命名空間「`visitorId`」和「`customVisitorId`」，以識別 Analytics 舊版追蹤 Cookie 和 Analytics 客戶訪客 ID。 請勿將這些命名空間用於自訂流量或轉換變數。

如需詳細資訊，請參閱[將變數標示為 ID-DEVICE 或 ID-PERSON 時提供命名空間](/help/admin/tools/privacy-labeling/labels.md)。
