---
description: 您提交的 ID 並不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics可建立擴增ID集，將這項相關聯資料納入資料隱私權請求中。
title: ID 擴增
feature: Data Governance
role: Admin
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 96%

---

# ID 擴增

您提交的 ID 並不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求)：

```
"expandIds": true
```

如需更多詳細資料，請參閱 [Privacy Service API 文件](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)。


| 類型 | 考量事項 |
| --- | --- |
| Cookie ID 擴增 | 許多 Analytics 客戶原本使用 (舊版) [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html)，現在則使用 [Experience Cloud 身分服務 (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html)。針對轉換後初次造訪的網站訪客，系統僅存在 ECID。然而，對於那些在只有舊版 Cookie 可用時首次造訪，但此後又造訪過的使用者：他們的部分資料會具有這兩種 Cookie。但是，較舊的資料只有 Analytics Cookie，而在極少數情況下，最新的資料可能只有 ECID。<p>確定您找到的所有訪客資料都是透過 Analytics (訪客 ID) Cookie 或 ECID 識別。若您目前使用 ECID，而之前使用 Analytics Cookie，只要您使用其中一種 ID 來提交請求，皆應在請求中納入兩種 ID，或指定 `expandIds` 選項。當您指定 `expandIds` 時，Adobe 會檢查對應至您所提供的 Cookie ID 之其他 ECID 或 Analytics Cookie。此請求會自動擴增為包含這些新識別的 Cookie ID。 |
| 自訂 ID 至 Cookie ID 擴增 | 在電子商務網站上，訪客經常會先瀏覽網站的各個頁面，將商品加入購物車，在進入結帳程序後才會登入網站。若用來識別資料隱私權請求使用者的 ID，只會在使用者登入時儲存在自訂變數中，則此預先登入活動不會與此 ID 建立關聯。使用 Analytics Cookie ID 時，由於 Cookie ID 在整個登入過程都會存在，因此客戶可選擇將登入前所進行的瀏覽動作與登入後的購買動作相關聯。<p>假設您的實施會將登入 ID (CRM ID、使用者名稱、忠誠度編號、電子郵件地址等等，或這些值的任意雜湊) 儲存在自訂變數 (prop 或 eVar) 或自訂訪客 ID 中，然後將此 ID 用於資料隱私權存取請求。資料主體可能會訝異於系統並未將他們的所有瀏覽資訊做為存取請求的一部分回傳，特別是在您的促銷商品已被瀏覽過但尚未購買的時候。因此，Analytics 資料隱私權處理程序將僅支援 ID 擴增，Analytics 可在其中找到點擊產生的所有 Cookie ID (這和能產生自訂 ID 的點擊相同)，然後擴增請求以一併納入這些 ID。<p>在指定 `expandIDs` 以及 Cookie 命名空間以外的任何命名空間時，系統會擴增請求以納入在包含任何指定 ID 的點擊中找到的任何 Cookie ID (ECID 或 Analytics Cookie)。接著，就會在任何新發現的 Cookie ID 上執行 Cookie ID 擴增 (如上所述)。<p>在將 `expandIDs` 選項用於存取請求，而指定的 ID 具有 ID-PERSON 標籤時，將會傳回兩組檔案。第一組 (人員組) 只會納入找到指定 ID 的點擊中的資料。第二組 (裝置組) 則只會納入來自 expanded ID，但沒有指定 ID 的點擊資料。 |

{style="table-layout:auto"}

## 何時使用 ID 擴增

在資料隱私權施行的最初幾個月期間，絕大部分的 Analytics 資料隱私權請求不會請求 ID 擴增。但是否要為組織決定適當的值取決於您。您應向法務團隊諮詢具您所使用之 ID 的資料，以及在 Adobe Analytics 內收集的資料，是否需要 ID 擴增。

主要考量可以是：在共用裝置上，已有多位使用者造訪您的網站，使用 ID 擴增會在存取請求傳回的資料中，納入該裝置其他使用者的點擊資料 (位於裝置檔案中)。即使您已遵照標籤的最佳實務，例如裝置檔案中沒有納入私人資料 (如造訪的頁面)，裝置檔案仍會包含已造訪的頁面數輛和每次造訪的時間。您可以詢問自己：如果和還不是訪客的人士共用此資訊，是可以的嗎？

當刪除請求&#x200B;*並未*&#x200B;使用 ID 擴增：若您使用非 Cookie ID (非 ECID 或 Analytics Cookie 的 ID) 來找出應刪除的點擊，且該 ID 具有 ID-DEVICE 標籤，則報表中的不重複訪客計數會有所改變。這是因為 Cookie ID 只有部分例項會匿名，其餘例項皆不會變更。若您未指定 ID 擴增，則建議您為請求使用 Cookie ID，或使用具有 ID-PERSON 標籤的 ID。

當 Adobe 執行 ID 擴增時，它可能需要額外的完整資料掃描。這會增加 Adobe 完成請求所需的時間，通常會增加一週的處理時間。

## 其他資料隱私權請求標記

除了「expandIDs」標記，Analytics 支援其他兩種標記，可以包含在資料隱私權請求中一併傳入。這些標記和其預設值如下：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

除了預設值「anonymize」外，`analyticsDeleteMethod` 未來可能也會支援「purge」值。一旦支援此值，會造成整個點擊遭到刪除，而非僅更新帶有 DEL 標籤之點擊欄位的值。

除了其預設值外，`priority` 欄位亦支援「low」值。您應對於不是資料主體請求之結果的請求指定該值，因此沒有必須於特定時間範圍內完成的法律要求。

## Privacy Service API 的使用

>[!IMPORTANT]
>
>除了有效的資料主體提出的請求以外，Adobe 不允許基於其他原因使用[Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)。Privacy Service API 並不是用於資料清理或修復的適當工具。對非數據主體發起的請求對 Privacy Service API 的濫用將會導致意想不到的後果。提供給 Adobe 客戶的 Privacy Service API 是要協助您履行有時效性的資料隱私權請求。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶及時處理較優先、由使用者提出的資料隱私權請求。請勿將 Privacy Service API 用於其他用途，例如資料清理，或清除大訪客群組意外提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的結果，這也突顯出 Privacy Service API 不適合此用途的原因。

請聯絡您的Adobe客戶團隊，以協調我們的工程架構顧問團隊，以進一步檢視及著手移除任何PII或解決資料問題。
