---
description: 了解在 Analytics 資料中擷取的 ID，並決定您要用於資料隱私權請求的 ID。
title: 標籤最佳作法
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
TQID: https://experienceleague.adobe.com/btvouuszSZn1h7xDCInebbqYE9vb1bwcU4-DMW3l3oM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 2341
ht-degree: 71%

---

# 標籤最佳作法

每次建立新報告套裝或在現有報告套裝中啟用新變數時，都必須仔細檢閱標籤。 啟用新的解決方案整合時，您可能需要檢閱標籤，因為它們可能會公開需要加上標籤的新變數。 重新實施行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。

I1、I2、S1 及 S2 標籤與 Adobe Experience Platform 中對應命名的 DULE 標籤具有相同意義。 然而，它們的用途卻截然不同。 在 Adobe Analytics 中，這些標籤用於協助識別因 Privacy Service 請求而應匿名處理的欄位。 在 Adobe Experience Platform 中，它們用於存取控制、同意管理，以及對標記欄位執行行銷限制。 Adobe Experience Platform 支援許多 Adobe Analytics 未使用的其他標籤。 如果您利用 Analytics 資料連接器將 Adobe Analytics 資料匯入至 Adobe Experience Platform，應確保您已在 Adobe Analytics 中套用的任何 I1、I2、S1 及 S2 標籤，也套用於由匯入的報告套裝使用的 Adobe Experience Platform 結構描述。

## 可直接與間接識別身分的 ID {#direct-vs-indirect}

在判斷標籤應套用到哪些變數/欄位之前，您必須先瞭解從 Analytics 資料擷取的 ID 所代表之意義，再決定要提供哪些 ID 以用於資料隱私權請求。 資料隱私權擴大了 ID 的定義範圍， 目前 ID 區分為兩個較廣泛的類別，分別為可直接識別身分 (身分識別標籤：I1) 與可間接識別身分 (身分識別標籤：I2)　的 ID。

* **可直接識別身分的 ID (I1)**：此類 ID 是指個人的名稱或可用來聯絡該人的資訊。 例如：某人的姓名（包括像「約翰史密斯」這種可能已有數百人同名的常見名字）、電子郵件地址或電話號碼等等。沒有名稱的郵寄地址可能會被視為直接可識別，即使它可能只識別家庭或企業，而不是該家庭或企業內的特定人員。
* **可間接識別身分的 ID (I2)**：此類 ID 本身無法辨別個人，但若交叉比對其他資訊 (資訊不限您擁有或他方擁有) 仍可具識別效果。 間接的可識別 ID 範例包括客戶忠誠度編號，或公司 CRM 系統所使用每位客戶唯一的 ID。 根據資料隱私權，即使儲存於 Analytics 所用追蹤 Cookie 的匿名 ID 僅能識別裝置而無法識別個人，仍會視為可間接識別身分的 ID；在共用裝置上，這些 Cookie 無法辨別系統中的不同使用者。 例如，雖然無法用 Cookie 找到包含 Cookie 的電腦，但如果有人存取電腦並找到 Cookie，就可以從 Analytics Cookie 資料回溯繫結至該電腦。

此外，由於 IP 位址在任何特定時刻都只能指派給單一裝置，因此亦視為可間接識別身分。 不過，ISP可以而且經常會定期變更大部分使用者的IP位址，因此一段時間後，其使用者可能會使用IP位址。 ISP的許多客戶或同一企業內部網路上的多位員工共用相同的外部IP位址的情況也很常見。 因此，Adobe 並不支援使用 IP 位址當作資料隱私權請求的 ID。 但如果我們接受的 ID 用於刪除請求，我們也會將隨著該 ID 產生的 IP 位址一併清除。 您必須判斷是否有其他已收集的 ID 屬於此 I1 或 I2 的類別，但不適合使用做為資料隱私權請求的識別 ID。

即使貴公司從 Analytics 資料中收集了許多不同的 ID，您仍可選擇只將這些 ID 的子集用於資料隱私權請求。 原因可能包括：

* 在您自己的系統中，可以將其中一個 ID (如：電子郵件地址) 對應到不同的 ID (如：CRM ID)， 然後您為了一致性，決定在資料隱私權處理程序中，只將 CRM ID 用於資料隱私權請求。
* 您沒有方法可驗證某個人實際是與ID相關聯的人員。 例如：您很難確認 IP 位址只由特定一個使用者使用，也很難證明提交請求的人就是該使用者。
* 部分 ID 可能對應到多個人，且您並不希望冒險將一個人的相關資訊回傳給具有相同 ID 的其他使用者。 例如：即使您確認某人的姓名就是約翰史密斯，但您並不打算將系統中姓名同為約翰史密斯的所有使用者資料一併傳回。
* 另一個例子是裝置 ID，例如：Analytics Cookie ID。 如果此ID發生在行動電話應用程式上，您可以決定使用此ID的所有互動都應該可供行動電話的擁有者使用。 但是，如果這發生在共用裝置上，例如家用電腦或圖書館或網際網路咖啡館中的電腦，您可能會決定您無法區分該裝置的使用者，並且為不同使用者傳回資料的風險太大，不允許使用這種型別的ID。

## 適用於 Analytics 支援 ID 的最佳做法 {#best-practices-an}

請使用下表來判斷將資料隱私權請求提交給 Analytics 時，要使用的 ID 類型。 知道這些資訊後，就能更輕鬆決定變數應使用的其他標籤。

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
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/tw/en/docs/id-service/using/home"> 身分識別服務 Cookie</a> (ECID) 原稱為 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些Cookie會識別裝置，或更具體地說，為裝置的使用者識別瀏覽器。 若是使用通用登入的共用裝置，此ID可套用至裝置的任何/所有使用者。 如果您想要讓這些 ID 用於資料隱私權請求，Adobe 已建立一些<a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">統一的 JavaScript</a>，可讓您放置於網站中以收集 Cookie。 </p> <p>Adobe Analytics Mobile SDK 也有 Experience Cloud ID (ECID)， SDK 中的 API 呼叫可讀取此 ID，因此您可增強應用程式以收集用於資料隱私權請求的 ID。 </p> <p>許多公司會將瀏覽器 Cookie ID 視為共用裝置 ID， 因此，在與他們的法律團隊協商後，他們可能會選擇不支援使用做為資料隱私權請求的可接受 ID。 或者，他們可能會選擇在使用這些 ID 時，僅傳回數量非常有限的資料，或者他們可能只接受用於刪除請求。 </p> <p>這些Cookie具有無法變更的ID-DEVICE標籤（以及I2和DEL-DEVICE標籤）。 預設Adobe Analytics設定只會傳回關於裝置的一般資訊，例如裝置型別、作業系統、瀏覽器等，加上使用這些ID造訪您網站的時間/日期。 不過，如果您選擇支援這些 ID 用於資料隱私權請求，則可按照下文所述以新增或移除 ACC-ALL 標籤，並設定您想傳回用於資料隱私權存取請求的確切欄位組合。 </p> <p>如果報告套裝對應於需要登入的行動應用程式，您可以確定該裝置的 Experience Cloud ID 確實對應於特定使用者。 在這種情況下，您可能希望使用 ACC-ALL 標籤標記更多欄位，包括造訪過的頁面名稱、檢視過的產品等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂變數中的 ID </p> </td> 
   <td colname="col2"> <p>部分客戶會將 ID 放置於<a href="/help/implement/vars/page-vars/evar.md">自訂流量變數 (prop) 或自訂轉換變數 (eVar)</a> 中； 最常用的是 CRM ID，其他 ID 則包含：電子郵件地址、使用者登入名稱、客戶忠誠度編號或這些值的雜湊。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您想將上述任一 ID 用於資料隱私權請求，則您應該對包含該 ID 的欄位提供 ID-PERSON 標籤。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">(非常少見) 如果其中一個自訂變數的 ID 僅能識別多人共用的裝置，則您可改為包含 ID-DEVICE 標籤。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">這些欄位也需要I1或I2標籤，而且應該包含DEL-PERSON或DEL-DEVICE標籤。 通常，DEL標籤的「人員/裝置」選項會與ID標籤的「人員/裝置」選項相符。 </li> 
    </ul> <p> 報告套裝很少會有超過一個或兩個的自訂變數，內含您用來識別資料主體以提供給資料隱私權請求的 ID。 您可能有多個已指派I1或I2標籤的變數，但通常其中只有一或兩個會同時具有ID-PERSON或ID-DEVICE標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂訪客 ID </p> </td> 
   <td colname="col2"> <p>雖然自訂訪客 ID 並未廣泛使用，Analytics 仍支援提供此 ID 的實作；如有此 ID，系統就會用來取代舊版 Analytics 追蹤 Cookie。 此欄位具有標籤I2、ID-PERSON和DEL-PERSON。 </p> <p>許多實作會從 CRM ID 衍生此 ID，因此只在有人登入其網站時才會出現。 如此可讓跨裝置使用相同的自訂訪客ID。 一個技術缺點是，使用者登入前發生的追蹤無法繫結至他們登入後收集的追蹤。 如果您改用自訂訪客ID來簡單識別裝置，則應分別將ID-PERSON和DEL-PERSON標籤變更為ID-DEVICE和DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定刪除標籤的最佳做法 {#best-practices-delete}

>[!NOTE]
>
>屬性一律不區分大小寫， 而 eVar 雖然預設為不區分，但您可聯絡 Adobe 客戶服務中心將其設為區分大小寫。 如果具有 ID 的 eVar 區分大小寫，則您在提交資料隱私權請求時有責任使用正確的大小寫，如此請求中所用的大小寫與點擊包含之 ID 的大小寫才會相符。

請謹慎使用刪除標籤 DEL-DEVICE 和 DEL-PERSON。 如果套用到的變數中沒有用於資料隱私權請求的 ID，則歷史 Analytics 報表中的計數 (量度) 幾乎一律都會變更。

* 我們建議將其中一個標籤套用到標記為 I1、I2 或 S1 的任何變數； 未標記 I1、I2 或 S1 的任何變數無法套用這些標籤。
* DEL-標籤會讓系統為這些變數進行[匿名處理](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) (ID 將替換為以「Data Privacy-」為首碼的隨機字串)， 相同的匿名值將會取代請求中使用之ID所識別的所有點選中原始值的所有例項。 如果此欄位中的原始值是這些ID之一，則報表量度不會變更。
* 一般而言，如果欄位具有標籤ID-DEVICE，則您也應該指派標籤DEL-DEVICE。
* 同樣地，如果欄位具有標籤ID-PERSON，則您也應該指派標籤DEL-PERSON。
* 如果欄位中沒有 ID- 標籤，但含有您想要匿名處理的身分識別資訊，則應根據您的實作採用適當的標籤 (DEVICE 或 PERSON)。 如果您在資料隱私權請求中僅使用 Cookie ID，則應使用 DEL-DEVICE。
* 如果您在具有 ID-PERSON 標籤的不同欄位中使用自訂 ID，且只想從產生 ID 的資料列中清除此 ID，則使用 DEL-PERSON。
* 請注意，如果未在任何未當作該請求ID使用的變數上指定DEL-DEVICE或DEL-PERSON標籤（包括展開的ID），則只有在發生指定（或展開）ID的點選中，才會匿名顯示該變數中的唯一值。 如果其他點選包含相同的值，則其他位置不會更新該值。 這可能會導致計數（量度）變更。

  例如，如果您在 eVar7 有三個含有「foo」值的點擊，不過只有其中一個點擊同時在符合刪除條件的其他變數中含有 ID，則系統會將該點擊的「foo」修改為「Data Privacy-123456789」之類的值，其他兩個點擊的值將維持不變。 在顯示 eVar7 唯一值數量的報表中，將會比以往多顯示一個唯一值。 顯示 eVar 最高值的報表只會包含兩個例項的「foo」(而非先前的 3 個)，而新值則會連同單一例項一併顯示。

## 設定存取標籤的最佳做法 {#best-practices-access}

很少有欄位會包含其他標籤，不過許多欄位有 ACC 標籤這是常見的情況。 適當的存取標籤取決於您要用於資料隱私權請求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若您使用... </th> 
   <th colname="col2" class="entry"> ...使用這些Recommendations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>僅限裝置ID </p> </td> 
   <td colname="col2"> <p>如果您唯一使用的ID是Cookie ID或具有ID-DEVICE標籤的ID，則您應該僅使用ACC-ALL標籤。 </p> <p>每個存取請求將會獲得一組檔案：一個檔案包含每個相符點擊的資料列，並且具有所有指定的 ACC-ALL 欄位，而摘要檔案則包含此資料的摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>
