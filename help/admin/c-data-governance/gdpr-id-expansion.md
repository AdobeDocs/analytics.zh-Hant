---
description: '您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入 GDPR 請求。您可以為您提交的每個 GDPR 請求，要求此包含選用參數的選項，並新增至 JSON 請求 '
seo-description: '您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入 GDPR 請求。您可以為您提交的每個 GDPR 請求，要求此包含選用參數的選項，並新增至 JSON 請求 '
seo-title: ID 擴增
title: ID 擴增
uuid: 2672d17d-c957-4e08-8d98-16d54 d54 bb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# ID 擴增
#

您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入 GDPR 請求。您可以為您提交的每個 GDPR 請求，要求此包含選用參數的選項，並新增至 JSON 請求:

```
"expandIds": true
```

如需有關如何將此選項納入請求的範例，請參閱[範例 JSON 請求](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_DB9DE6492FE740918F91D413E7BAB88F)。如需更多詳細資料，請參閱 [GDPR API 文件](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)。

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
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external"> Analytics Cookie </a>, but are now using the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). 針對轉換後初次造訪的網站訪客，系統僅存在 ECID。不過，對於初次造訪時網站只使用舊版 Cookie 而後再訪的使用者: 有些資料會兩種 Cookie 都有，而較舊的資料只會有 Analytics Cookie，在極少數情況下，最新的資料則可能只有 ECID。 </p> <p>您希望確保您找到的所有訪客資料都是透過 Analytics (訪客 ID) Cookie 或 ECID 識別。因此，若您目前使用 ECID，而之前使用 Analytics Cookie，只要您使用其中一種 ID 來提交請求，皆應在請求中納入兩種 ID，或指定 expandIds 選項。當您指定 expandIds 時，Adobe 會檢查對應至您所提供的 Cookie ID 之其他 ECID 或 Analytics Cookie。此請求會自動擴增為包含這些新識別的 Cookie ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂 ID 至 Cookie ID 擴增 </p> </td> 
   <td colname="col2"> <p>在電子商務網站上，訪客經常會先瀏覽網站的各個頁面，將商品加入購物車，在進入結帳程序後才會登入網站。若用來識別 GDPR 請求使用者的 ID，只會在使用者登入時儲存在自訂變數中，則此預先登入活動不會與此 ID 建立關聯。使用 Analytics Cookie ID 時，由於 Cookie ID 在整個登入過程都會存在，因此客戶可選擇將登入前所進行的瀏覽動作與登入後的購買動作相關聯。 </p> <p>假設您的實作會將登入 ID (CRM ID、使用者名稱、忠誠度編號、電子郵件地址等等，或這些值的任意雜湊) 儲存在自訂變數 (prop 或 eVar) 或自訂訪客 ID 中，然後將此 ID 用於 GDPR 存取請求。資料主體對於系統並未將他們的所有瀏覽資料都隨存取請求傳回，可能會覺得很意外，特別是在您向他們促銷已瀏覽過但尚未購買的商品時。 </p> <p>因此，Analytics GDPR 處理程序將僅支援 ID 擴增，Analytics 可在其中找到點擊產生的所有 Cookie ID (這和能產生自訂 ID 的點擊相同)，然後擴增請求以一併納入這些 ID。 </p> <p>在指定 expandIDs 以及 Cookie 命名空間以外的任何命名空間時，系統會擴增請求以納入在包含任何指定 ID 的點擊中找到的任何 Cookie ID (ECID 或 Analytics Cookie)。接著，就會在任何新發現的 Cookie ID 上執行 Cookie ID 擴增 (如上所述)。 </p> <p>在將 expandIDs 選項用於存取請求，而指定的 ID 具有 ID-PERSON 標籤時，將會傳回兩組檔案。第一組 (人員組) 只會納入找到指定 ID 的點擊中的資料。第二組 (裝置組) 則只會納入來自 expanded ID，但沒有指定 ID 的點擊資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在 GDPR 施行的最初幾個月期間，絕大部分的 Analytics GDPR 請求不會請求 ID 擴增，但是否要為組織決定適當的值由您做主。您應向法務團隊諮詢具您所使用之 ID 的資料，以及在 Adobe Analytics 內收集的資料，是否需要 ID 擴增。主要考量應為在共用裝置上，已有多位使用者造訪網站，使用 ID 擴增會在存取請求傳回的資料中，納入該裝置其他使用者的點擊資料 (位於裝置檔案中)。即使您已遵照標籤的最佳作法，例如裝置檔案中不會納入私人資料 (如造訪的頁面)，裝置檔案仍會包含造訪頁面數和每次造訪的時間。可以與可能還不是訪客的人士共用此資訊嗎?

若為刪除請求，由於這種請求並未使用 ID 擴增，若您使用非 Cookie ID (非 ECID 或 Analytics Cookie 的 ID) 來找出應刪除的點擊，且該 ID 具有 ID-DEVICE 標籤，則報表中的不重複訪客計數會有所改變，這是因為 Cookie ID 只有部分例項會匿名，其餘例項皆不會變更。若您未指定 ID 擴增，則建議您將 Cookie ID 用於請求，或使用具有 ID-PERSON 標籤的 ID。

當 Adobe 執行 ID 擴增時，可能會需要進行額外完整資料掃描，這會增加 Adobe 完成請求所需的時間，通常會增加一週的處理時間。

## 其他GDPR要求標幟
##

除了「expandIDs」標記，Analytics 支援其他兩種標記，可以包含在 GDPR 請求中一併傳入。這些標記和其預設值如下:

```
"analyticsDeleteMethod": “anonymize”
“priority”: “normal”
```

「analyticsDeleteMethod」除了預設值「anonymize」外，未來可能也會支援「purge」值。一旦支援此值，會造成整個點擊遭到刪除，而非僅更新帶有 DEL 標籤之點擊欄位的值。

除了其預設值外，優先順序欄位亦支援「low」值。若請求不是資料主體請求的結果，並因此不具須於 30 天內完成的法律規定，您應為此等請求指定此值。請注意，除了資料主體提出的請求以外，Adobe 不鼓勵基於其他原因使用 GDPR API。GDPR API 並非適合用於資料清理或修復的工具，可能會致生非預期的後果。

>[!NOTE]
>GDPR API已提供協助您履行敏感的GDPR要求。Adobe不支援使用此API for&gt;其他目的，並且可能會影響Adobe為其他Adobe客戶適時啓用高優先順序的GDPR請求。我們要求您不要使用GDPR API，例如清除意外提交給大量訪客的資料。
>
>您也應注意，因為GDPR&gt;刪除要求而刪除了點擊的任何訪客(更新或匿名)都會重設狀態資訊。訪客下次返回您的網站時，就會變成新訪客。所有eVar歸因都會再次開始，如造訪次數、反向連結、第一頁瀏覽等資訊都會再次啓動。在您想要清除&gt;資料欄位的情況下，此副作用是不需要的，並且反白顯示GDPR API不適合此使用情況的原因一。
>
>請聯絡您的客戶經理(CSM)，與我們的工程架構設計人員諮詢團隊合作，進一步審查並提供更多的努力以移除任何PII或資料問題。

