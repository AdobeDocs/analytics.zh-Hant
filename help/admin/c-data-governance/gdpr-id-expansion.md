---
description: 您提交的ID不一定會涵蓋Analytics可與資料主體建立關聯的所有點擊資料。 Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求)
title: ID 擴增
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: f135138de15f3fc788e637128daeb064d0d453af
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 33%

---

# ID 擴增

您提交的ID不一定會涵蓋Analytics可與資料主體建立關聯的所有點擊資料。 Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求)：

```
"expandIds": true
```

如需更多詳細資料，請參閱 [Privacy Service API 文件](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html)。


| 類型 | 考量事項 |
| --- | --- |
| Cookie ID 擴增 | 許多Analytics客戶原本使用（舊版） [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en)，但現在正使用 [Experience CloudIdentity服務(ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-TW). 針對轉換後初次造訪的網站訪客，系統僅存在 ECID。不過，對於初次造訪時只有舊版Cookie可供使用，但之後已造訪的使用者：其部分資料有兩個cookie。 不過，較舊的資料只會有Analytics Cookie，而在少數情況下，最新的資料可能只會有ECID。<p>請務必找到透過Analytics（訪客ID）Cookie或ECID識別之訪客的所有資料。 如果您目前使用ECID，且先前已使用Analytics Cookie，則每當您使用任一ID類型提交請求時，請在請求中納入兩個ID，或指定 `expandIds` 選項。 指定 `expandIds`,Adobe會檢查與您提供之任何Cookie ID對應的其他ECID或Analytics Cookie。 請求會自動展開以包含這些新識別的Cookie ID。 |
| 自訂 ID 至 Cookie ID 擴增 | 在電子商務網站上，訪客經常會先瀏覽網站的各個頁面，將商品加入購物車，在進入結帳程序後才會登入網站。如果用於識別資料隱私權請求使用者的ID，只會在使用者登入時儲存在自訂變數中，則此預先登入活動不會與ID相關聯。 使用 Analytics Cookie ID 時，由於 Cookie ID 在整個登入過程都會存在，因此客戶可選擇將登入前所進行的瀏覽動作與登入後的購買動作相關聯。<p>假設您的實作會將登入 ID (CRM ID、使用者名稱、忠誠度編號、電子郵件地址等等，或這些值的任意雜湊) 儲存在自訂變數 (prop 或 eVar) 或自訂訪客 ID 中，然後將此 ID 用於資料隱私權存取請求。資料主體對於系統並未將其所有瀏覽資訊隨存取請求傳回，可能會很吃驚，尤其是如果您已促銷已檢視但尚未購買的項目。 因此，Analytics 資料隱私權處理程序將僅支援 ID 擴增，Analytics 可在其中找到點擊產生的所有 Cookie ID (這和能產生自訂 ID 的點擊相同)，然後擴增請求以一併納入這些 ID。<p>當 `expandIDs` 會連同Cookie命名空間以外的任何命名空間一起指定，請求會擴增為包含任何Cookie ID（ECID或Analytics Cookie），只要在包含任何指定ID的點擊中找到。 接著會對任何新找到的Cookie ID執行Cookie ID擴增（如上所述）。<p>當 `expandIDs` 選項用於存取請求，而指定的ID標籤為ID-PERSON，則會傳回兩組檔案。 第一組 (人員組) 只會納入找到指定 ID 的點擊中的資料。第二組 (裝置組) 則只會納入來自 expanded ID，但沒有指定 ID 的點擊資料。 |

{style=&quot;table-layout:auto&quot;}

## 何時使用ID擴增

資料隱私權上線後的頭幾個月，絕大多數的Analytics資料隱私權請求都未要求ID擴增。 不過，您應自行決定適合貴組織的值。 您應洽詢您的法律團隊，諮詢是否需要ID擴增才能使用您使用的ID，以及您在Adobe Analytics中收集的資料。

主要考慮因素包括：在有多位使用者造訪過您網站的共用裝置上，使用ID擴增時，會將來自其他使用者點擊裝置的資料，納入存取請求傳回的資料中（在裝置檔案中）。 即使您已遵循標籤的最佳實務（例如，裝置檔案中未包含任何私人資料，例如已造訪的頁面），裝置檔案仍會包含已造訪的頁面數和每次造訪的時間。 你可能想問自己：可以與可能不是訪客的人共用此資訊嗎？

當ID擴增為 *not* 用於刪除請求：如果您使用非Cookie ID（ECID或Analytics Cookie以外的任何ID）來識別應刪除的點擊，且該ID具有ID-DEVICE標籤，則報表中的獨特訪客計數將會改變。 這是因為只有部分Cookie ID會進行匿名處理，而其他ID則維持不變。 若您未指定ID擴增，建議您為請求使用Cookie ID，或使用ID-PERSON標籤的ID。

當Adobe執行ID擴增時，可能需要額外的完整資料掃描。 這會增加Adobe完成請求所花的時間，通常會增加一週的處理時間。

## 其他資料隱私權請求標記

除了「expandIDs」標記，Analytics 支援其他兩種標記，可以包含在資料隱私權請求中一併傳入。這些標記和其預設值如下：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

未來， `analyticsDeleteMethod` 除了預設值「anonymize」外，可能還支援「purge」值。 若支援，將會刪除整個點擊，而非只更新具有DEL標籤之點擊欄位的值。

除了其預設值外， `priority` 欄位也支援「low」值。 您應為非資料主體請求結果的請求指定此值，因此沒有須於特定時間範圍內完成的法律要求。

## 使用Privacy ServiceAPI

>[!IMPORTANT]
>
>Adobe不允許使用 [Privacy ServiceAPI](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) 除了資料主體啟動的有效請求之外的其他原因。 Privacy ServiceAPI不是資料清理或修復的適當工具。 若將Privacy ServiceAPI誤用於非資料主體起始的請求，將產生非預期的後果。 Privacy ServiceAPI是提供給Adobe客戶，協助您履行資料隱私權請求，這些請求常有時效性。 Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將Privacy ServiceAPI用於其他用途，例如資料衛生或清除大量訪客群組不小心提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見看到這個結果，這也突顯出Privacy ServiceAPI不適合此用途的原因。

請連絡您的客戶經理(CSM)來協調工程架構顧問團隊，以進一步檢閱，並致力移除任何PII或解決資料問題。
