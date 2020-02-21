---
description: '您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求) '
title: ID 擴增
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# ID 擴增

您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求)：

```
"expandIds": true
```

如需有關如何將此選項納入請求的範例，請參閱[範例 JSON 請求](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request)。如需更多詳細資料，請參閱[隱私權服務 API 文件](https://www.adobe.io/apis/experienceplatform/gdpr.html)。

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 類型 </th> 
   <th colname="col2" class="entry"> 考量事項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID 擴增 </p> </td> 
   <td colname="col2"> <p>許多 Analytics 客戶原本使用 (舊版) <a href="https://marketing.adobe.com/resources/help/zh_TW/whitepapers/cookies/cookies_analytics.html">Analytics Cookie</a>，現在則使用原稱為 Marketing Cloud ID 服務 (MCID) 的<a href="https://marketing.adobe.com/resources/help/zh_TW/mcvid/">身分識別服務 (ECID)</a>。針對轉換後初次造訪的網站訪客，系統僅存在 ECID。不過，對於初次造訪時網站只使用舊版 Cookie 而後再訪的使用者：有些資料會兩種 Cookie 都有，而較舊的資料只會有 Analytics Cookie，在極少數情況下，最新的資料則可能只有 ECID。 </p> <p>您希望確保您找到的所有訪客資料都是透過 Analytics (訪客 ID) Cookie 或 ECID 識別。因此，若您目前使用 ECID，而之前使用 Analytics Cookie，只要您使用其中一種 ID 來提交請求，皆應在請求中納入兩種 ID，或指定 expandIds 選項。當您指定 expandIds 時，Adobe 會檢查對應至您所提供的 Cookie ID 之其他 ECID 或 Analytics Cookie。此請求會自動擴增為包含這些新識別的 Cookie ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂 ID 至 Cookie ID 擴增 </p> </td> 
   <td colname="col2"> <p>在電子商務網站上，訪客經常會先瀏覽網站的各個頁面，將商品加入購物車，在進入結帳程序後才會登入網站。若用來識別資料隱私權請求使用者的 ID，只會在使用者登入時儲存在自訂變數中，則此預先登入活動不會與此 ID 建立關聯。使用 Analytics Cookie ID 時，由於 Cookie ID 在整個登入過程都會存在，因此客戶可選擇將登入前所進行的瀏覽動作與登入後的購買動作相關聯。 </p> <p>假設您的實作會將登入 ID (CRM ID、使用者名稱、忠誠度編號、電子郵件地址等等，或這些值的任意雜湊) 儲存在自訂變數 (prop 或 eVar) 或自訂訪客 ID 中，然後將此 ID 用於資料隱私權存取請求。資料主體對於系統並未將他們的所有瀏覽資料都隨存取請求傳回，可能會覺得很意外，特別是在您向他們促銷已瀏覽過但尚未購買的商品時。 </p> <p>因此，Analytics 資料隱私權處理程序將僅支援 ID 擴增，Analytics 可在其中找到點擊產生的所有 Cookie ID (這和能產生自訂 ID 的點擊相同)，然後擴增請求以一併納入這些 ID。 </p> <p>在指定 expandIDs 以及 Cookie 命名空間以外的任何命名空間時，系統會擴增請求以納入在包含任何指定 ID 的點擊中找到的任何 Cookie ID (ECID 或 Analytics Cookie)。接著，就會在任何新發現的 Cookie ID 上執行 Cookie ID 擴增 (如上所述)。 </p> <p>在將 expandIDs 選項用於存取請求，而指定的 ID 具有 ID-PERSON 標籤時，將會傳回兩組檔案。第一組 (人員組) 只會納入找到指定 ID 的點擊中的資料。第二組 (裝置組) 則只會納入來自 expanded ID，但沒有指定 ID 的點擊資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在資料隱私權施行的最初幾個月期間，絕大部分的 Analytics 資料隱私權請求不會請求 ID 擴增，但是否要為組織決定適當的值取決於您。您應向法務團隊諮詢具您所使用之 ID 的資料，以及在 Adobe Analytics 內收集的資料，是否需要 ID 擴增。主要考量應為在共用裝置上，已有多位使用者造訪網站，使用 ID 擴增會在存取請求傳回的資料中，納入該裝置其他使用者的點擊資料 (位於裝置檔案中)。即使您已遵照標籤的最佳作法，例如裝置檔案中不會納入私人資料 (如造訪的頁面)，裝置檔案仍會包含造訪頁面數和每次造訪的時間。可以與可能還不是訪客的人士共用此資訊嗎？

若為刪除請求，由於這種請求並未使用 ID 擴增，若您使用非 Cookie ID (非 ECID 或 Analytics Cookie 的 ID) 來找出應刪除的點擊，且該 ID 具有 ID-DEVICE 標籤，則報表中的不重複訪客計數會有所改變，這是因為 Cookie ID 只有部分例項會匿名，其餘例項皆不會變更。若您未指定 ID 擴增，則建議您將 Cookie ID 用於請求，或使用具有 ID-PERSON 標籤的 ID。

當 Adobe 執行 ID 擴增時，可能會需要進行額外完整資料掃描，這會增加 Adobe 完成請求所需的時間，通常會增加一週的處理時間。

## 其他資料隱私權請求標記

除了「expandIDs」標記，Analytics 支援其他兩種標記，可以包含在資料隱私權請求中一併傳入。這些標記和其預設值如下：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

「analyticsDeleteMethod」除了預設值「anonymize」外，未來可能也會支援「purge」值。一旦支援此值，會造成整個點擊遭到刪除，而非僅更新帶有 DEL 標籤之點擊欄位的值。

除了其預設值外，優先順序欄位亦支援「low」值。若請求不是資料主體請求的結果，並因此不具須於 30 天內完成的法律規定，您應為此等請求指定此值。請注意，除了資料主體提出的請求以外，Adobe 不鼓勵基於其他原因使用隱私權服務 API。隱私權服務 API 並非適合用於資料清理或修復的工具，可能會致生非預期的後果。

> [!NOTE]
[隱私權服務 API](https://www.adobe.io/apis/experienceplatform/gdpr.html) 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將隱私權服務 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出隱私權服務 API 不適合此用途的原因。

請連絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，以進一步檢視及著手移除所有 PII 或資料問題。

