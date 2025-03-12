---
description: 了解在 Analytics 資料中擷取的 ID，並決定您要用於資料隱私權請求的 ID。
title: 標籤最佳作法
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
source-git-commit: 3e87d420591405e57e57e18fda4287d5fbd3bf1b
workflow-type: tm+mt
source-wordcount: '2287'
ht-degree: 91%

---

# 標籤最佳作法

每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。 啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實施行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。

I1、I2、S1和S2標籤與Adobe Experience Platform中相應命名的DULE標籤具有相同的含義。 不過，它們的用途大不相同。 在Adobe Analytics中，這些標籤可用來幫助識別應因Privacy Service請求而匿名的欄位。 在Adobe Experience Platform中，它們用於存取控制、同意管理，以及在標籤欄位上強制執行行銷限制。 Adobe Experience Platform支援許多Adobe Analytics未使用的其他標籤。 如果您使用Analytics Data Connector將Adobe Analytics資料匯入Adobe Experience Platform，您應確保已在Adobe Analytics中套用的任何I1、I2、S1和S2標籤，也會套用至Adobe Experience Platform中由匯入報表套裝使用的結構描述。

## 可直接與間接識別身分的 ID {#direct-vs-indirect}

在判斷標籤應套用到哪些變數/欄位之前，您必須先瞭解從 Analytics 資料擷取的 ID 所代表之意義，再決定要提供哪些 ID 以用於資料隱私權請求。資料隱私權擴大了 ID 的定義範圍，目前 ID 區分為兩個較廣泛的類別，分別為可直接識別身分 (身分識別標籤：I1) 與可間接識別身分 (身分識別標籤：I2)　的 ID。

* **可直接識別身分的 ID (I1)**：此類 ID 是指個人的名稱或可用來聯絡該人的資訊。例如：某人的姓名 (包括像「約翰」這種可能已有數百人同名的常見名字) 或是電子郵件地址或電話號碼等等。未提供收件人的郵寄地址亦視為可直接識別身分的 ID，即使這個地址只能用來辨別住宅或公司行號，而無法指認該地址的特定對象。
* **可間接識別身分的 ID (I2)**：此類 ID 本身無法辨別個人，但若交叉比對其他資訊 (資訊不限您擁有或他方擁有) 仍可具識別效果。間接的可識別 ID 範例包括客戶忠誠度編號，或公司 CRM 系統所使用每位客戶唯一的 ID。根據資料隱私權，即使儲存於 Analytics 所用追蹤 Cookie 的匿名 ID 僅能識別裝置而無法識別個人，仍會視為可間接識別身分的 ID；在共用裝置上，這些 Cookie 無法辨別系統中的不同使用者。例如，雖然無法用 Cookie 找到包含 Cookie 的電腦，但如果有人存取電腦並找到 Cookie，就可以從 Analytics Cookie 資料回溯繫結至該電腦。

此外，由於 IP 位址在任何特定時刻都只能指派給單一裝置，因此亦視為可間接識別身分。不過，ISP 可經常定期變更大部分使用者的 IP 位址，因此同一個 IP 位址在一段時間後可能會分配給其他使用者使用；ISP 的多個客戶或公司裡同一個內部網路中的多名員工共用相同外部 IP 位址，也是很普遍的情況。因此，Adobe 並不支援使用 IP 位址當作資料隱私權請求的 ID。但如果我們接受的 ID 用於刪除請求，我們也會將隨著該 ID 產生的 IP 位址一併清除。您必須判斷是否有其他已收集的 ID 屬於此 I1 或 I2 的類別，但不適合使用做為資料隱私權請求的識別 ID。

即使貴公司從 Analytics 資料中收集了許多不同的 ID，您仍可選擇只將這些 ID 的子集用於資料隱私權請求。原因可能包括：

* 在您自己的系統中，可以將其中一個 ID (如：電子郵件地址) 對應到不同的 ID (如：CRM ID)，然後您為了一致性，決定在資料隱私權處理程序中，只將 CRM ID 用於資料隱私權請求。
* 您沒有可用來確認某人就是與特定 ID 相關聯的驗證方法。例如：您很難確認 IP 位址只由特定一個使用者使用，也很難證明提交請求的人就是該使用者。
* 部分 ID 可能對應到多個人，且您並不希望冒險將一個人的相關資訊回傳給具有相同 ID 的其他使用者。例如：即使您確認某人的姓名就是約翰史密斯，但您並不打算將系統中姓名同為約翰史密斯的所有使用者資料一併傳回。
* 另一個例子是裝置 ID，例如：Analytics Cookie ID。手機應用程式中產生 ID 時，您也許會將使用該 ID 進行的所有互動判斷為來自這支手機的擁有者。但如果是發生在共用裝置 (如家用電腦、圖書館或網咖的電腦) 時，您可能就無法區分該裝置的使用者，而傳回不同使用者資料的風險太大，因此您不能允許使用這類 ID。

## 適用於 Analytics 支援 ID 的最佳做法 {#best-practices-an}

請使用下表來判斷將資料隱私權請求提交給 Analytics 時，要使用的 ID 類型。瞭解此資訊能讓您輕鬆地判斷變數應使用的其他標籤。

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 類型 </th> 
   <th colname="col2" class="entry"> 推薦 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=zh-Hant"> (舊版) Analytics Cookie </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant"> 身分識別服務 Cookie</a> (ECID) 原稱為 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些 Cookie 可用來識別裝置，更具體的說法是裝置使用者所用的瀏覽器；而共用裝置一般會採用通用登入帳號，因此 ID 可能適用於裝置的任何/所有使用者。如果您想要讓這些 ID 用於資料隱私權請求，Adobe 已建立一些<a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">統一的 JavaScript</a>，可讓您放置於網站中以收集 Cookie。 </p> <p>Adobe Analytics Mobile SDK 也有 Experience Cloud ID (ECID)，SDK 中的 API 呼叫可讀取此 ID，因此您可增強應用程式以收集用於資料隱私權請求的 ID。 </p> <p>許多公司會將瀏覽器 Cookie ID 視為共用裝置 ID，因此，在與他們的法律團隊協商後，他們可能會選擇不支援使用做為資料隱私權請求的可接受 ID。或者，他們可能會選擇在使用這些 ID 時，僅傳回數量非常有限的資料，或者他們可能只接受用於刪除請求。 </p> <p>這些 Cookie 具有無法變更的 ID-DEVICE 標籤 (以及 I2 和 DEL-DEVICE 標籤)。預設的 Adobe Analytics 設定將僅傳回裝置的類型、作業系統、瀏覽器等一般資料，以及裝置使用這些 ID 造訪網站的時間/日期。不過，如果您選擇支援這些 ID 用於資料隱私權請求，則可按照下文所述以新增或移除 ACC-ALL 標籤，並設定您想傳回用於資料隱私權存取請求的確切欄位組合。 </p> <p>如果報告套裝對應於需要登入的行動應用程式，您可以確定該裝置的 Experience Cloud ID 確實對應於特定使用者。在這種情況下，您可能希望使用 ACC-ALL 標籤標記更多欄位，包括造訪過的頁面名稱、檢視過的產品等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂變數中的 ID </p> </td> 
   <td colname="col2"> <p>部分客戶會將 ID 放置於<a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar.html?lang=zh-Hant">自訂流量變數 (prop) 或自訂轉換變數 (eVar)</a> 中；最常用的是 CRM ID，其他 ID 則包含：電子郵件地址、使用者登入名稱、客戶忠誠度編號或這些值的雜湊。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您想將上述任一 ID 用於資料隱私權請求，則您應該對包含該 ID 的欄位提供 ID-PERSON 標籤。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">(非常少見) 如果其中一個自訂變數的 ID 僅能識別多人共用的裝置，則您可改為包含 ID-DEVICE 標籤。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">這些欄位也會要求 I1 或 I2 標籤，且應包含 DEL-PERSON 或 DEL-DEVICE 標籤。一般來說，DEL 標籤的 PERSON/DEVICE 選項將與 ID 標籤的 PERSON/DEVICE 選項相符。 </li> 
    </ul> <p> 報告套裝很少會有超過一個或兩個的自訂變數，內含您用來識別資料主體以提供給資料隱私權請求的 ID。您可能會有多個變數標記 I1 或 I2 標籤，但通常只有其中一或兩個會同時包含 ID-PERSON 或 ID-DEVICE 標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂訪客 ID </p> </td> 
   <td colname="col2"> <p>雖然自訂訪客 ID 並未廣泛使用，Analytics 仍支援提供此 ID 的實施；如有此 ID，系統就會用來取代舊版 Analytics 追蹤 Cookie。此欄位的標籤有 I2、ID-PERSON 和 DEL-PERSON。 </p> <p>許多實作會從 CRM ID 衍生此 ID，因此只在有人登入其網站時才會出現。如此可在不同裝置間使用相同的自訂訪客 ID。而這有一個技術上的缺點，即使用者登入之前的追蹤資料將無法繫結至登入後系統收集的追蹤資料。不過，如果您使用自訂訪客 ID 僅為了能識別裝置，應將 ID-PERSON 和 DEL- PERSON 標籤分別變更為 ID-DEVICE 和 DEL- DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定刪除標籤的最佳做法 {#best-practices-delete}

>[!NOTE]
>
>屬性一律不區分大小寫，而 eVar 雖然預設為不區分，但您可聯絡 Adobe 客戶服務中心將其設為區分大小寫。如果具有 ID 的 eVar 區分大小寫，則您在提交資料隱私權請求時有責任使用正確的大小寫，如此請求中所用的大小寫與點擊包含之 ID 的大小寫才會相符。

請謹慎使用刪除標籤 DEL-DEVICE 和 DEL-PERSON。如果套用到的變數中沒有用於資料隱私權請求的 ID，則歷史 Analytics 報表中的計數 (量度) 幾乎一律都會變更。

* 我們建議將其中一個標籤套用到標記為 I1、I2 或 S1 的任何變數；未標記 I1、I2 或 S1 的任何變數無法套用這些標籤。
* DEL-標籤會讓系統為這些變數進行[匿名處理](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) (ID 將替換為以「Data Privacy-」為首碼的隨機字串)，而在由請求所用 ID 識別出來的所有點擊中，所有原始值的例項都會取代為相同的匿名值。如果此欄位中的原始值是這些 ID 的其中之一，則報表量度將不會變更。
* 一般而言，如果欄位有 ID-DEVICE 標籤，則您也應指派 DEL-DEVICE 標籤。
* 同樣地，如果欄位有 ID-PERSON 標籤，則您也應指派 DEL-PERSON 標籤。
* 如果欄位中沒有 ID- 標籤，但含有您想要匿名處理的身分識別資訊，則應根據您的實施採用適當的標籤 (DEVICE 或 PERSON)。如果您在資料隱私權請求中僅使用 Cookie ID，則應使用 DEL-DEVICE。
* 如果您在含有 ID-PERSON 標籤的不同欄位中使用自訂 ID，且只想從產生 ID 的資料列中清除值，請使用 DEL-PERSON。
* 請注意，若對任何變數指定 DEL-DEVICE 或 DEL-PERSON 標籤，而該變數並非用作該請求的 ID (包括擴增 ID)，那麼系統只能在指定 (或擴增) ID 出現的點擊中，以匿名方式處理該變數中的唯一值。如果其他點擊含有相同的值，系統便不會更新這些其他位置的值。這會導致計數 (量度) 發生變化。

  例如，如果您在 eVar7 有三個含有「foo」值的點擊，不過只有其中一個點擊同時在符合刪除條件的其他變數中含有 ID，則系統會將該點擊的「foo」修改為「Data Privacy-123456789」之類的值，其他兩個點擊的值將維持不變。在顯示 eVar7 唯一值數量的報表中，將會比以往多顯示一個唯一值。顯示 eVar 最高值的報表只會包含兩個例項的「foo」(而非先前的 3 個)，而新值則會連同單一例項一併顯示。

## 設定存取標籤的最佳做法 {#best-practices-access}

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
   <td colname="col2"> <p>如果您使用的只有 Cookie ID 或具有 ID-DEVICE 標籤的 ID，則您只能使用 ACC-ALL 標籤。 </p> <p>您將取得每個存取要求的一對檔案：一個檔案包含每個符合點選（具有所有指定ACC-ALL欄位）的列，以及一個摘要檔案（包含此資料的摘要）。 </p> </td> 
  </tr> 
 </tbody> 
</table>
