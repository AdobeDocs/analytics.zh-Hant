---
description: '您提交的 ID 不一定會涵蓋 Analytics 可用來與資料主體建立關聯的所有點擊資料。Analytics 可建立擴增 ID 集，將這項相關聯資料納入資料隱私權請求中。您可以透過選用參數來為您提交的每個資料隱私權請求要求此選項 (新增至 JSON 請求) '
title: ID 擴增
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

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
   <td colname="col1"> <p>Cookie ID擴增 </p> </td> 
   <td colname="col2"> <p>許多 Analytics 客戶原本使用 (舊版) <a href="https://marketing.adobe.com/resources/help/zh_TW/whitepapers/cookies/cookies_analytics.html">Analytics Cookie</a>，現在則使用原稱為 Marketing Cloud ID 服務 (MCID) 的<a href="https://marketing.adobe.com/resources/help/zh_TW/mcvid/">身分識別服務 (ECID)</a>。對於在轉換後首次造訪的網站訪客，僅存在ECID。 不過，對於初次造訪時網站只使用舊版 Cookie 而後再訪的使用者：有些資料會兩種 Cookie 都有，而較舊的資料只會有 Analytics Cookie，在極少數情況下，最新的資料則可能只有 ECID。 </p> <p>您要確定您找到透過Analytics（訪客ID）Cookie或ECID識別的訪客的所有資料。 因此，如果您目前使用ECID且先前使用過Analytics Cookie，則每當您使用任一種ID類型提交請求時，請在請求中同時包含這兩個ID，或指定expandIds選項。 當您指定expandId時，Adobe會檢查是否有其他ECID或Analytics Cookie，這些ECID與您提供的任何Cookie ID對應。 請求會自動展開，以包含這些新識別的Cookie ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂ID至Cookie ID擴增 </p> </td> 
   <td colname="col2"> <p>在電子商務網站上，訪客瀏覽網站、將物品新增至購物車，然後在登入網站之前開始結帳程式並不少見。 若用來識別資料隱私權請求使用者的 ID，只會在使用者登入時儲存在自訂變數中，則此預先登入活動不會與此 ID 建立關聯。使用 Analytics Cookie ID 時，由於 Cookie ID 在整個登入過程都會存在，因此客戶可選擇將登入前所進行的瀏覽動作與登入後的購買動作相關聯。 </p> <p>假設您的實作會將登入 ID (CRM ID、使用者名稱、忠誠度編號、電子郵件地址等等，或這些值的任意雜湊) 儲存在自訂變數 (prop 或 eVar) 或自訂訪客 ID 中，然後將此 ID 用於資料隱私權存取請求。資料主體對於系統並未將他們的所有瀏覽資料都隨存取請求傳回，可能會覺得很意外，特別是在您向他們促銷已瀏覽過但尚未購買的商品時。 </p> <p>因此，Analytics 資料隱私權處理程序將僅支援 ID 擴增，Analytics 可在其中找到點擊產生的所有 Cookie ID (這和能產生自訂 ID 的點擊相同)，然後擴增請求以一併納入這些 ID。 </p> <p>當expandID與Cookie命名空間以外的任何命名空間一起指定時，請求將會展開，以包含包含任何指定ID的點擊中找到的Cookie ID（ECID或Analytics Cookie）。 然後，將會如上所述，對任何新找到的Cookie ID執行Cookie ID擴增。 </p> <p>當expandIDs選項用於存取請求，而指定的ID有ID-PERSON標籤時，將會傳回兩組檔案。 第一個集（人員集）將僅包含找到指定ID之點擊的資料。 第二組（裝置集）將僅包含來自已擴充ID的點擊資料，而指定ID則不存在。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在資料隱私權施行的最初幾個月期間，絕大部分的 Analytics 資料隱私權請求不會請求 ID 擴增，但是否要為組織決定適當的值取決於您。您應洽詢您的法律團隊，瞭解您使用的ID和您在Adobe Analytics中收集的資料是否需要擴充ID。 主要考量應是，在多位使用者瀏覽過您網站的共用裝置上，使用ID擴增時，會將來自裝置其他使用者的點擊資料納入存取要求（在裝置檔案中）傳回的資料中。 即使您已遵循標示的最佳實務，例如裝置檔案中未包含任何私人資料（例如已瀏覽的頁面），裝置檔案仍會包含已瀏覽的頁面數和每次瀏覽的時間。 可以與可能還不是訪客的人士共用此資訊嗎？

若是刪除請求（未使用ID擴增），如果您使用非Cookie ID（ECID或Analytics Cookie以外的任何ID）來識別應刪除的點擊，且該ID具有ID-DEVICE標籤，則報表中的獨特訪客計數會變更，因為只有Cookie ID的某些例項會匿名化，而其他的例項則保持不變。 如果您未指定ID擴增，則建議您使用Cookie ID來處理請求，或使用ID-PERSON標籤的ID。

當Adobe執行ID擴增時，可能需要額外的完整資料掃描，這會增加Adobe完成要求所花的時間，通常會增加一週的處理時間。

## 其他資料隱私權請求標記

除了「expandIDs」標記，Analytics 支援其他兩種標記，可以包含在資料隱私權請求中一併傳入。這些標記和其預設值如下：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

「analyticsDeleteMethod」除了預設值「anonymize」外，未來可能也會支援「purge」值。一旦支援此值，會造成整個點擊遭到刪除，而非僅更新帶有 DEL 標籤之點擊欄位的值。

除了其預設值外，優先順序欄位亦支援「low」值。若請求不是資料主體請求的結果，並因此不具須於 30 天內完成的法律規定，您應為此等請求指定此值。請注意，除了資料主體提出的請求以外，Adobe 不鼓勵基於其他原因使用隱私權服務 API。隱私權服務 API 並非適合用於資料清理或修復的工具，可能會致生非預期的後果。

>[!NOTE]
[隱私權服務 API](https://www.adobe.io/apis/experienceplatform/gdpr.html) 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將隱私權服務 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下次回訪您的網站時，即會是新訪客。 所有eVar歸因都會重新開始，如造訪次數、反向連結、首次瀏覽頁面等資訊也會重新開始。 若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出隱私權服務 API 不適合此用途的原因。

請連絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，以進一步檢視及著手移除所有 PII 或資料問題。

