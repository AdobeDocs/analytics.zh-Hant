---
description: 'null'
title: 標籤最佳作法
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 標籤最佳作法

>[!NOTE] 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。在啟用新的解決方案整合時，您也需要檢閱標籤，因為這些標籤可能會公開可能需要標籤的新變數。 重新實作行動應用程式或網站可能會改變現有變數的使用方式，這可能也需要更新標籤。

## 可直接與間接識別身分的 ID {#section_030799AA1397433FBA61A2BC60A7A750}

在判斷標籤應套用到哪些變數/欄位之前，您必須先瞭解從 Analytics 資料擷取的 ID 所代表之意義，再決定要提供哪些 ID 以用於資料隱私權請求。資料隱私權擴大了 ID 的定義範圍，目前 ID 區分為兩個較廣泛的類別，分別為可直接識別身分 (身分識別標籤：I1) 與可間接識別身分 (身分識別標籤：I2)　的 ID。

* **可直接識別身分的 ID (I1)**：此類 ID 是指個人的名稱或可用來聯絡該人的資訊。例如：某人的姓名 (包括像「約翰」這種可能已有數百人同名的常見名字) 或是電子郵件地址或電話號碼等等。無名稱的郵寄地址可能被視為直接可識別身份，即使它只能識別家庭或企業，而不能識別該家庭或企業內的特定人員。
* **可間接識別身分的 ID (I2)**：此類 ID 本身無法辨別個人，但若交叉比對其他資訊 (資訊不限您擁有或他方擁有) 仍可具識別效果。例如：客戶忠誠度編號或公司 CRM 系統所用的 ID (每位客戶指定一個唯一 ID)。根據資料隱私權，即使儲存於 Analytics 所用追蹤 Cookie 的匿名 ID 僅能識別裝置而無法識別個人，仍會視為可間接識別身分的 ID；在共用裝置上，這些 Cookie 無法辨別系統中的不同使用者。例如，雖然Cookie無法用於尋找包含Cookie的電腦，但是如果有人可存取電腦並找到Cookie，則他們可將Analytics Cookie資料系結回電腦。

   IP位址也被視為可間接識別，因為在任何時間上，都可能只指派給單一裝置。 但是，ISP可以而且通常會定期變更大部分使用者的IP位址，因此隨著時間推移，任何使用者都可能會使用IP位址。 同時，許多ISP客戶或同一內部網路上企業內的多名員工共用相同的外部IP位址，也並不少見。 因此，Adobe 不支援使用 IP 位址當作[資料隱私權請求的 ID。](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests)但如果我們接受的 ID 用於刪除請求，我們也會將隨著該 ID 產生的 IP 位址一併清除。您必須判斷是否有其他已收集的 ID 屬於 I1 或 I2 的此類別，但這些 ID 不適合用來當作資料隱私權請求的識別 ID。

即使貴公司從 Analytics 資料中收集了許多不同的 ID，您仍可選擇只將這些 ID 的子集用於資料隱私權請求。原因可能包括：

* 在您自己的系統中，可以將其中一個 ID (如：電子郵件地址) 對應到不同的 ID (如：CRM ID)，然後您為了一致性，決定在資料隱私權處理程序中，只將 CRM ID 用於資料隱私權請求。
* 您沒有驗證某人是與ID關聯之人的方法。 例如：您很難確認 IP 位址只由特定一個使用者使用，也很難證明提交請求的人就是該使用者。
* 有些ID可能對應至多個人，您不想冒將某人相關資訊傳回給其他具有相同ID的人的風險。 例如：即使您確認某人的姓名就是約翰史密斯，但您並不打算將系統中姓名同為約翰史密斯的所有使用者資料一併傳回。
* 另一個例子是裝置 ID，例如：Analytics Cookie ID。如果ID發生在行動電話應用程式上，您可以決定使用該ID的所有互動都應該可供行動電話擁有者使用。 不過，如果發生在共用裝置上（例如家用電腦或資料庫或網際網路咖啡廳中的電腦），您可能會決定無法區分該裝置的使用者，而針對不同使用者傳回資料的風險太大，無法使用此類ID。

## Analytics支援的ID最佳實務 {#section_B6481505FF1949498D4B4B35B780D050}

請使用下表來判斷將資料隱私權請求提交給 Analytics 時，要使用的 ID 類型。一旦您知道這些資訊，就可更輕鬆地判斷您應用於變數的其他標籤。

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID類型 </th> 
   <th colname="col2" class="entry"> 建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/zh_TW/whitepapers/cookies/cookies_analytics.html"> (舊版) Analytics Cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/zh_TW/mcvid/"> 身分識別服務 Cookie</a> (ECID) 原稱為 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些Cookie可識別裝置，或更確切地說，是裝置使用者的瀏覽器。 對於使用共用登入的共用裝置，此ID可套用至裝置的任何／所有使用者。 如果您想要讓這些 ID 用於資料隱私權請求，Adobe 已建立一些<a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">統一的 JavaScript</a>，可讓您放置於網站中以收集 Cookie。 </p> <p>Adobe Analytics Mobile SDK 也有 Experience Cloud ID (ECID)，SDK 中的 API 呼叫可讀取此 ID，因此您可增強應用程式以收集用於資料隱私權請求的 ID。 </p> <p>許多公司會將瀏覽器 Cookie ID 視為共用裝置 ID，在與內部法務部門人員諮詢過後，可能選擇不支援將這些 ID 用於資料隱私權請求；或者也可選擇在使用這些 ID 時僅傳回非常有限的資料量，或者僅接受這些資料用於刪除請求 </p> <p>這些Cookie有無法變更的ID-DEVICE標籤（以及I2和DEL-DEVICE標籤）。 預設的Adobe Analytics設定只會傳回裝置的一般資訊，例如裝置類型、作業系統、瀏覽器等。 加上使用這些ID時您網站的瀏覽時間／日期。 不過，如果您選擇支援這些 ID 用於資料隱私權請求，則可按照下文所述以新增或移除 ACC-ALL 標籤，並設定您想傳回用於資料隱私權存取請求的確切欄位組合。 </p> <p>特別是在報表套裝已對應到行動應用程式，且您的行動應用程式要求登入的情況下，您可決定讓裝置的 Experience Cloud ID 對應到特定使用者，然後您可能會想透過 ACC-ALL 標籤標記更多欄位，包括使用者造訪的頁面名稱、瀏覽過的產品等等。 </p> <p>注意：如果您在資料隱私權請求中指定「expandIds」選項，則除了您指定的其他任何 ID 之外，請求將一律包含 Cookie ID。如需更多詳細資料，請參閱 <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">ID 擴增</a>。在這些例項中，只有Cookie ID但沒有其他ID的點擊，只會傳回標示為ACC-ALL的資料，做為存取要求的一部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂變數中的 ID </p> </td> 
   <td colname="col2"> <p>部分客戶會將 ID 放置於<a href="https://marketing.adobe.com/resources/help/zh_TW/sc/implement/props_eVars.html">自訂流量變數 (prop) 或自訂轉換變數 (eVar)</a> 中；最常用的是 CRM ID，其他 ID 則包含：電子郵件地址、使用者登入名稱、客戶忠誠度編號或這些值的雜湊。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您想將上述任一 ID 用於資料隱私權請求，則您應該對包含該 ID 的欄位提供 ID-PERSON 標籤。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">(非常少見) 如果其中一個自訂變數的 ID 僅能識別多人共用的裝置，則您可改為包含 ID-DEVICE 標籤。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">這些欄位也需要I1或I2標籤，並應包含DEL-PERSON或DEL-DEVICE標籤。 通常，DEL標籤的PERSON/DEVICE選項會與ID標籤的PERSON/DEVICE選項相符。 </li> 
    </ul> <p> 報表套裝很少會有兩個以上的自訂變數，內含您用來識別資料主體以提供給資料隱私權請求的 ID。您可能有多個變數指派給I1或I2標籤，但通常只有一或兩個變數會有ID-PERSON或ID-DEVICE標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂訪客 ID </p> </td> 
   <td colname="col2"> <p>即使此功能並未廣泛使用，Analytics也支援可提供自訂訪客ID的實作，如果存在則會用來取代舊版Analytics追蹤Cookie。 此欄位具有標籤I2、ID-PERSON和DEL-PERSON。 </p> <p>許多實作會從CRM ID衍生此ID，因此只有在某人登入其網站時才會出現此ID。 這可讓相同的自訂訪客ID用於各種裝置。 一個技術缺點是，在使用者登入之前進行的追蹤無法系結至使用者登入後收集的追蹤。 若您改用自訂訪客ID來識別裝置，則應將ID-PERSON和DEL-PERSON標籤分別變更為ID-DEVICE和DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定刪除標籤的最佳實務 {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE] prop 一律不區分大小寫，而 eVar 雖然預設為不區分，但您可聯絡 Adobe 客戶服務中心將其設為區分大小寫。如果具有 ID 的 eVar 區分大小寫，則您在提交資料隱私權請求時有責任使用正確的大小寫，如此請求中所用的大小寫與點擊包含之 ID 的大小寫才會相符。

請謹慎使用刪除標籤 DEL-DEVICE 和 DEL-PERSON。如果套用到的變數中沒有用於資料隱私權請求的 ID，則歷史 Analytics 報表中的計數 (量度) 幾乎一律都會變更。

* 我們建議將其中一個標籤套用到標記為 I1、I2 或 S1 的任何變數；未標記 I1、I2 或 S1 的任何變數無法套用這些標籤。
* DEL-標籤會讓系統為這些變數進行[匿名處理](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (ID 將替換為以「Data Privacy-」為首碼的隨機字串)，相同的匿名值會取代所有點擊中由請求中使用的ID所識別的原始值的所有例項。 如果此欄位中的原始值是其中一個ID，則報表量度不會變更。
* 通常，如果欄位具有標籤ID-DEVICE，則您還應指定標籤DEL-DEVICE。
* 同樣地，如果欄位具有標籤ID-PERSON，則您也應該指派標籤DEL-PERSON。
* 如果欄位沒有ID標籤，但包含您要匿名化的識別資訊，則適當的標籤（DEVICE或PERSON）會視您的實作而定。 如果您在資料隱私權請求中僅使用 Cookie ID，則應使用 DEL-DEVICE。
* 如果您在具有ID-PERSON標籤的不同欄位上使用自訂ID，而您只想在出現該ID的列上清除此項，請使用DEL-PERSON。
* 如果您使用ID擴增，而且想要清除所有識別裝置上所有點擊的所有值，則使用DEL-DEVICE。 在此例中，您可以視需要同時套用DEL-DEVICE和DEL-PERSON標籤，但DEL-PERSON標籤是不必要的，因為ID擴增表示符合人員ID的所有列也會符合裝置ID。
* 如果您不會指定使用ID擴增，但會針對不同的請求使用裝置與人員ID的混合，則您可能會想要為使用任一ID類型時應刪除的變數指定DEL-DEVICE和DEL-PERSON標籤。
* 請注意，如果在任何未用作該請求ID的變數（包括擴充的ID）上指定DEL-DEVICE或DEL-PERSON標籤，則該變數中的唯一值只會在出現指定（或擴充）ID的點擊時匿名。 如果其他點擊包含相同的值，則不會在這些其他位置更新。 這可能導致計數（量度）變更。

   例如，如果您在 eVar7 有三個含有「foo」值的點擊，不過只有其中一個點擊同時在符合刪除條件的其他變數中含有 ID，則系統會將該點擊的「foo」修改為「Data Privacy-123456789」之類的值，其他兩個點擊的值將維持不變。在顯示 eVar7 唯一值數量的報表中，將會比以往多顯示一個唯一值。顯示 eVar 最高值的報表只會包含兩個例項的「foo」(而非先前的 3 個)，而新值則會連同單一例項一併顯示。

## 設定存取標籤的最佳實務 {#section_AC7E216F81C141FCA6A62F8836E06EE7}

很少有欄位會包含其他標籤，不過許多欄位有 ACC 標籤這是常見的情況。適當的存取標籤取決於您要用於資料隱私權請求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果你用…… </th> 
   <th colname="col2" class="entry"> ...使用這些建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>僅限裝置ID </p> </td> 
   <td colname="col2"> <p>如果您使用的唯一ID是Cookie ID或具有ID-DEVICE標籤的ID，則您只應使用ACC-ALL標籤。 </p> <p>您會針對每個存取要求取得一對檔案，其中一對檔案會針對每個符合的點擊加上所有指定的ACC-ALL欄位，另一對檔案會包含此資料的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>沒有ID擴增的人員ID </p> </td> 
   <td colname="col2"> <p>如果您僅使用具有ID-PERSON標籤的自訂ID，而未執行ID擴增，則應使用ACC-PERSON標籤。 但是，您不需要變更預設的ACC-ALL標籤；這些欄位會自動納入存取請求中。 </p> <p>您會針對每個存取要求取得一對檔案，其中一對檔案會針對每個符合的點擊加上所有指定的ACC-DEVICE和ACC-PERSON欄位，而另一對檔案則包含此資料的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>混合 ID 和/或 ID 擴增 </p> </td> 
   <td colname="col2"> <p>如果您在資料隱私權請求中納入裝置及人員 ID，或者使用自訂 ID (自訂訪客 ID 或是 prop 或 eVar 中的 ID)，則請務必注意您所使用的 ACC 標籤。每個存取請求都會傳回兩組資料檔案，其中一組含有從人員 ID 匹配的點擊所擷取的資料，另一組則含有從人員 ID 不符但裝置 ID 匹配的點擊所擷取的資料。 </p> <p>「人員ID」檔案包含所有符合人員ID的點擊資料，其中包含具有ACC-PERSON或ACC-ALL標籤的所有欄位（一個檔案具有所有符合的點擊，另一個則是摘要）。 </p> <p>「裝置ID」檔案對僅包含具有ACC-ALL標籤的欄位，且僅包含未包含任何相符人員ID的點擊。 這些檔案可能包含共用裝置其他使用者產生的資料，因此您需要仔細考慮包含ACC-ALL標籤的欄位集。 Analytics中的預設標籤僅將此標籤套用至與裝置相關的一般資訊欄位（裝置類型、作業系統、瀏覽器等）加上每次點擊的日期／時間。 </p> <p>您可以選擇從Adobe接收裝置和人員檔案集，然後僅共用人員檔案，以避免共用裝置的其他使用者可能產生的資料。 或者，您可能希望將一組或兩組資料中的資料與您瞭解的資料主體的其他資訊合併，並以您自己的格式傳回。 </p> </td> 
  </tr> 
 </tbody> 
</table>

