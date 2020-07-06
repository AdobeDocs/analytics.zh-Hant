---
description: 'null'
title: 標籤最佳作法
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '2689'
ht-degree: 100%

---


# 標籤最佳作法

>[!NOTE]
>
>請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。

## 可直接與間接識別身分的 ID {#section_030799AA1397433FBA61A2BC60A7A750}

在判斷標籤應套用到哪些變數/欄位之前，您必須先瞭解從 Analytics 資料擷取的 ID 所代表之意義，再決定要提供哪些 ID 以用於資料隱私權請求。資料隱私權擴大了 ID 的定義範圍，目前 ID 區分為兩個較廣泛的類別，分別為可直接識別身分 (身分識別標籤：I1) 與可間接識別身分 (身分識別標籤：I2)　的 ID。

* **可直接識別身分的 ID (I1)**：此類 ID 是指個人的名稱或可用來聯絡該人的資訊。例如：某人的姓名 (包括像「約翰」這種可能已有數百人同名的常見名字) 或是電子郵件地址或電話號碼等等。未提供收件人的郵寄地址亦視為可直接識別身分的 ID，即使這個地址只能用來辨別住宅或公司行號，而無法指認該地址的特定對象。
* **可間接識別身分的 ID (I2)**：此類 ID 本身無法辨別個人，但若交叉比對其他資訊 (資訊不限您擁有或他方擁有) 仍可具識別效果。例如：客戶忠誠度編號或公司 CRM 系統所用的 ID (每位客戶指定一個唯一 ID)。根據資料隱私權，即使儲存於 Analytics 所用追蹤 Cookie 的匿名 ID 僅能識別裝置而無法識別個人，仍會視為可間接識別身分的 ID；在共用裝置上，這些 Cookie 無法辨別系統中的不同使用者。例如，雖然無法用 Cookie 來找到包含 Cookie 的電腦，但如果有人存取電腦並找到 Cookie，就可以從 Analytics Cookie 資料回溯繫結至該電腦。

   此外，由於 IP 位址在任何情況下都只能指派給單一裝置，因此亦視為可間接識別身分的 ID。不過，ISP 可經常定期變更大部分使用者的 IP 位址，因此同一個 IP 位址在一段時間後可能會分配給其他使用者使用；ISP 的多個客戶或公司裡同一個內部網路中的多名員工共用相同外部 IP 位址，也是很普遍的情況。因此，Adobe 不支援使用 IP 位址當作[資料隱私權請求的 ID。](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests)但如果我們接受的 ID 用於刪除請求，我們也會將隨著該 ID 產生的 IP 位址一併清除。您必須判斷是否有其他已收集的 ID 屬於 I1 或 I2 的此類別，但這些 ID 不適合用來當作資料隱私權請求的識別 ID。

即使貴公司從 Analytics 資料中收集了許多不同的 ID，您仍可選擇只將這些 ID 的子集用於資料隱私權請求。原因可能包括：

* 在您自己的系統中，可以將其中一個 ID (如：電子郵件地址) 對應到不同的 ID (如：CRM ID)，然後您為了一致性，決定在資料隱私權處理程序中，只將 CRM ID 用於資料隱私權請求。
* 您沒有可用來確認某人就是與特定 ID 相關聯的驗證方法。例如：您很難確認 IP 位址只由特定一個使用者使用，也很難證明提交請求的人就是該使用者。
* 部分 ID 可能對應到多個人，而您不希望不小心將同個 ID 的其他使用者的資訊傳回。例如：即使您確認某人的姓名就是約翰史密斯，但您並不打算將系統中姓名同為約翰史密斯的所有使用者資料一併傳回。
* 另一個例子是裝置 ID，例如：Analytics Cookie ID。手機應用程式中產生 ID 時，您也許會將使用該 ID 進行的所有互動判斷為來自這支手機的擁有者。但如果是發生在共用裝置 (如家用電腦、圖書館或網咖的電腦) 時，您可能就無法區分該裝置的使用者，而傳回不同使用者資料的風險太大，因此您不能允許使用這類 ID。

## 適用於 Analytics 支援 ID 的最佳實務 {#section_B6481505FF1949498D4B4B35B780D050}

請使用下表來判斷將資料隱私權請求提交給 Analytics 時，要使用的 ID 類型。瞭解此資訊能讓您輕鬆地判斷變數應使用的其他標籤。

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 類型 </th> 
   <th colname="col2" class="entry"> 建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-privacy.html"> (舊版) Analytics Cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html"> 身分識別服務 Cookie</a> (ECID) 原稱為 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些 Cookie 可用來識別裝置，更具體的說法是裝置使用者所用的瀏覽器；而共用裝置一般會採用通用登入帳號，因此 ID 可能適用於裝置的任何/所有使用者。如果您想要讓這些 ID 用於資料隱私權請求，Adobe 已建立一些<a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">統一的 JavaScript</a>，可讓您放置於網站中以收集 Cookie。 </p> <p>Adobe Analytics Mobile SDK 也有 Experience Cloud ID (ECID)，SDK 中的 API 呼叫可讀取此 ID，因此您可增強應用程式以收集用於資料隱私權請求的 ID。 </p> <p>許多公司會將瀏覽器 Cookie ID 視為共用裝置 ID，在與內部法務部門人員諮詢過後，可能選擇不支援將這些 ID 用於資料隱私權請求；或者也可選擇在使用這些 ID 時僅傳回非常有限的資料量，或者僅接受這些資料用於刪除請求 </p> <p>這些 Cookie 具有無法變更的 ID-DEVICE 標籤 (以及 I2 和 DEL-DEVICE 標籤)。預設的 Adobe Analytics 設定將僅傳回裝置的類型、作業系統、瀏覽器等一般資料，以及裝置使用這些 ID 造訪網站的時間/日期。不過，如果您選擇支援這些 ID 用於資料隱私權請求，則可按照下文所述以新增或移除 ACC-ALL 標籤，並設定您想傳回用於資料隱私權存取請求的確切欄位組合。 </p> <p>特別是在報表套裝已對應到行動應用程式，且您的行動應用程式要求登入的情況下，您可決定讓裝置的 Experience Cloud ID 對應到特定使用者，然後您可能會想透過 ACC-ALL 標籤標記更多欄位，包括使用者造訪的頁面名稱、瀏覽過的產品等等。 </p> <p>注意：如果您在資料隱私權請求中指定「expandIds」選項，則除了您指定的其他任何 ID 之外，請求將一律包含 Cookie ID。如需更多詳細資料，請參閱 <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">ID 擴增</a>。在這些例項中，只有一個 Cookie ID (沒有其他 ID) 的點擊只會在存取請求中傳回標籤為 ACC-ALL 的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂變數中的 ID </p> </td> 
   <td colname="col2"> <p>部分客戶會將 ID 放置於<a href="https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/vars/page-vars/evar.html">自訂流量變數 (prop) 或自訂轉換變數 (eVar)</a> 中；最常用的是 CRM ID，其他 ID 則包含：電子郵件地址、使用者登入名稱、客戶忠誠度編號或這些值的雜湊。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您想將上述任一 ID 用於資料隱私權請求，則您應該對包含該 ID 的欄位提供 ID-PERSON 標籤。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">(非常少見) 如果其中一個自訂變數的 ID 僅能識別多人共用的裝置，則您可改為包含 ID-DEVICE 標籤。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">這些欄位也會要求 I1 或 I2 標籤，且應包含 DEL-PERSON 或 DEL-DEVICE 標籤。一般來說，DEL 標籤的 PERSON/DEVICE 選項將與 ID 標籤的 PERSON/DEVICE 選項相符。 </li> 
    </ul> <p> 報表套裝很少會有兩個以上的自訂變數，內含您用來識別資料主體以提供給資料隱私權請求的 ID。您可能會有多個變數標記 I1 或 I2 標籤，但通常只有其中一或兩個會同時包含 ID-PERSON 或 ID-DEVICE 標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂訪客 ID </p> </td> 
   <td colname="col2"> <p>雖然自訂訪客 ID 並未廣泛使用，Analytics 仍支援提供此 ID 的實作；如有此 ID，系統就會用來取代舊版 Analytics 追蹤 Cookie。此欄位的標籤有 I2、ID-PERSON 和 DEL-PERSON。 </p> <p>在許多實作中，自訂訪客 ID 會衍生自 CRM ID，因此只有在使用者已登入網站時才會存在此 ID；如此可在不同裝置間使用相同的自訂訪客 ID。而這有一個技術上的缺點，即使用者登入之前的追蹤資料將無法繫結至登入後系統收集的追蹤資料。不過，如果您使用自訂訪客 ID 僅為了能識別裝置，應將 ID-PERSON 和 DEL- PERSON 標籤分別變更為 ID-DEVICE 和 DEL- DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定刪除標籤的最佳實務 {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>屬性一律不區分大小寫，而 eVar 雖然預設為不區分，但您可聯絡 Adobe 客戶服務中心將其設為區分大小寫。如果具有 ID 的 eVar 區分大小寫，則您在提交資料隱私權請求時有責任使用正確的大小寫，如此請求中所用的大小寫與點擊包含之 ID 的大小寫才會相符。

請謹慎使用刪除標籤 DEL-DEVICE 和 DEL-PERSON。如果套用到的變數中沒有用於資料隱私權請求的 ID，則歷史 Analytics 報表中的計數 (量度) 幾乎一律都會變更。

* 我們建議將其中一個標籤套用到標記為 I1、I2 或 S1 的任何變數；未標記 I1、I2 或 S1 的任何變數無法套用這些標籤。
* DEL-標籤會讓系統為這些變數進行[匿名處理](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (ID 將替換為以「Data Privacy-」為首碼的隨機字串)，而在由請求所用 ID 識別出來的所有點擊中，所有原始值的例項都會取代為相同的匿名值。如果此欄位中的原始值是這些 ID 的其中之一，則報表量度將不會變更。
* 一般而言，如果欄位有 ID-DEVICE 標籤，則您也應指派 DEL-DEVICE 標籤。
* 同樣地，如果欄位有 ID-PERSON 標籤，則您也應指派 DEL-PERSON 標籤。
* 如果欄位中沒有 ID- 標籤，但含有您想要匿名處理的身分識別資訊，則應根據您的實作採用適當的標籤 (DEVICE 或 PERSON)。如果您在資料隱私權請求中僅使用 Cookie ID，則應使用 DEL-DEVICE。
* 如果您在含有 ID-PERSON 標籤的不同欄位中使用自訂 ID，且只想從產生 ID 的資料列中清除值，請使用 DEL-PERSON。
* 如果您使用 ID 擴增，且想將所有值從全部已識別裝置的所有點擊中清除，則請使用 DEL-DEVICE。您可以在這個案例中偏好同時套用 DEL-DEVICE 和 DEL-PERSON 標籤，只不過 DEL-PERSON 並非必要標籤，因為 ID 擴增意味著所有符合人員 ID 的資料列也符合裝置 ID。
* 如果您不指定使用 ID 擴增，但會混合使用裝置和人員 ID 來因應不同請求的需求，在使用任一種 ID 的情況下，您可能想要同時為應刪除的變數指定 DEL-DEVICE 和 DEL-PERSON 這兩個標籤。
* 請注意，若對任何變數指定 DEL-DEVICE 或 DEL-PERSON 標籤，而該變數並非用作該請求的 ID (包括擴增 ID)，那麼系統只能在指定 (或擴增) ID 出現的點擊中，以匿名方式處理該變數中的唯一值。如果其他點擊含有相同的值，系統便不會更新這些其他位置的值。這會導致計數 (量度) 發生變化。

   例如，如果您在 eVar7 有三個含有「foo」值的點擊，不過只有其中一個點擊同時在符合刪除條件的其他變數中含有 ID，則系統會將該點擊的「foo」修改為「Data Privacy-123456789」之類的值，其他兩個點擊的值將維持不變。在顯示 eVar7 唯一值數量的報表中，將會比以往多顯示一個唯一值。顯示 eVar 最高值的報表只會包含兩個例項的「foo」(而非先前的 3 個)，而新值則會連同單一例項一併顯示。

## 設定存取標籤的最佳實務 {#section_AC7E216F81C141FCA6A62F8836E06EE7}

很少有欄位會包含其他標籤，不過許多欄位有 ACC 標籤這是常見的情況。適當的存取標籤取決於您要用於資料隱私權請求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若您使用... </th> 
   <th colname="col2" class="entry"> ...請遵循這些建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>僅限裝置 ID </p> </td> 
   <td colname="col2"> <p>如果您使用的只有 Cookie ID 或具有 ID-DEVICE 標籤的 ID，則您只能使用 ACC-ALL 標籤。 </p> <p>每個存取請求會有一組檔案，其中一個檔案每個匹配的點擊都有一個資料列，並且具有所有指定的 ACC-ALL 欄位；第二個則含有此資料的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>沒有 ID 擴增的人員 ID </p> </td> 
   <td colname="col2"> <p>如果您僅使用含有 ID-PERSON 標籤的自訂 ID 但未實作 ID 擴增，則您應使用 ACC-PERSON 標籤。不過，您不需要變更預設的 ACC-ALL 標籤，這些欄位會自動納入存取請求。 </p> <p>每個存取請求會有一組檔案，其中一個檔案每個匹配的點擊都有一個資料列，並且具有所有指定的 ACC-DEVICE 和 ACC-PERSON 欄位；第二個則含有此資料的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>混合 ID 和/或 ID 擴增 </p> </td> 
   <td colname="col2"> <p>如果您在資料隱私權請求中納入裝置及人員 ID，或者使用自訂 ID (自訂訪客 ID 或是 prop 或 eVar 中的 ID)，則請務必注意您所使用的 ACC 標籤。每個存取請求都會傳回兩組資料檔案，其中一組含有從人員 ID 匹配的點擊所擷取的資料，另一組則含有從人員 ID 不符但裝置 ID 匹配的點擊所擷取的資料。 </p> <p>「person ID」檔案包含的所有點擊資料與具有包含 ACC-PERSON 和/或 ACC-ALL 標籤的所有欄位之人員 ID 相符 (一個檔案具有所有相符的點擊，另一個則提供摘要)。 </p> <p>「device ID」檔案組只包含有 ACC-ALL 標籤的欄位，以及不具任何匹配人員 ID 的點擊。這些檔案可能含有共用裝置上其他使用者產生的資料，因此使用具有 ACC-ALL 標籤的檔案組前，請務必謹慎考慮。Analytics 的預設標籤功能只會將該標籤套用到與裝置相關的一般資訊欄位 (裝置類型、作業系統、瀏覽器等等)，以及每個點擊的日期/時間。 </p> <p>您可選擇接收來自 Adobe 的裝置及人員檔案組，並僅分享人員檔案，只要別分享可能是共用裝置上其他使用者產生的資料即可。或者，您也可以將其中一個或兩個檔案集合的資料，和其他有關資料主體的已知資訊合併，然後再依您自己的格式傳回。 </p> </td> 
  </tr> 
 </tbody> 
</table>

