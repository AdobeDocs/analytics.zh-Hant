---
description: 'null'
title: Analytics 變數的資料隱私權標籤
uuid: a37a1278-7a0d-4e14-ae35-43bc460e7d12
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics 變數的資料隱私權標籤

## 為何標籤您的資料？{#section_A075CDF3AD0744BD8CEB41CE3FB7BFB3}

許多 Adobe 客戶的法律團隊都已檢閱過資料隱私權法規 (GDPR、CCPA 等)，且已針對如何處理資料以遵循資料隱私權法規得出各自的結論。各公司的法律解釋可能有所不同，而且所需的資料處理設定也可能因客戶而異。由於客戶對資料隱私權資料處理和不同資料集有不同的偏好，因此 Adobe 可讓 Adobe 客戶 (以資料控管者的身分) 根據其獨特資料，針對資料隱私權資料處理自訂其所需的設定。這讓每個獨特客戶都能夠針對其品牌和獨特的資料集，透過最適合的方式處理資料隱私權請求。

Adobe Analytics提供工具，根據資料的敏感性和合約限制來標籤資料。 標籤是相當重要且實用的功能，有助於：(1) 識別資料主題、(2) 判斷要傳回做為存取要求一部分的資料，以及 (3) 識別刪除要求中須刪除的資料欄位。

在確定應將哪些標籤套用至哪些變數/欄位之前，您需要先[瞭解在 Analytics 資料中擷取的 ID](/help/admin/c-data-governance/gdpr-analytics-ids.md)，並決定要將哪個 ID 用於資料隱私權請求。

Adobe Analytics 資料隱私權實作支援下列身分資料、敏感資料和資料控管的標籤。

## DULE 標籤 {#section_B2E78130957647338495EF37DE21D6BC}

>[!NOTE] 資料使用標籤和實行 (DULE) 架構的設計目的，是為了在所有 Adobe 解決方案/服務/平台上提供統一方式，以擷取、通訊和使用 Adobe Experience Cloud 上資料的中繼資料。中繼資料可協助資料控管單位指出哪些資料屬於個人資料、哪些資料屬於敏感資料，以及資料具有哪些合約規定。在此最初發行的版本中，Analytics 只會公開與資料隱私權相關的 DULE 標籤。當其他Adobe產品實作DULE標籤支援時，未來版本將會推出額外的敏感資料標籤以及合約標籤，以協助確保產品間共用的資料僅以合法允許的方式使用。

## 身分資料標籤(DULE) {#identity-data-labels}

系統會使用身分識別資料「I」標籤，將可識別或聯絡特定人士的資料加以分類。

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 其他需求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>可直接識別</b>：可以明確識別或可與個人直接聯絡的資料，例如姓名或電子郵件地址。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">無法在事件上設定 </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">無法在銷售eVar上設定 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>可間接識別</b>：可與任何其他資料合併使用，以識別或直接聯絡個人或裝置的資料， </p> <p>不允許個人本身的身分識別，但可結合其他資訊（可能或可能不在您手中）來識別某人。 例如：客戶忠誠度編號或公司 CRM 系統所用的 ID (每位客戶指定一個唯一 ID)。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">無法在事件上設定 </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">無法在銷售eVar上設定 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 敏感資料標籤(DULE) {#sensitive-data-labels}

系統會使用敏感資料「S」標籤，將地理資料等敏感資料加以分類。未來將推出額外的敏感資料標籤，以識別其他類型的敏感資訊。

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> 與緯度和經度相關的精確地理位置資料，可用來判斷裝置的確切位置（在100米或以下）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> 地理位置資料可用於判定廣泛定義的地理圍欄區域。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料控管標籤 (資料隱私權) {#data-governance-labels}

資料控管標籤讓使用者可分類反映隱私權相關考量事項，以及遵循法規和公司政策的合約條件資料。

**資料隱私權存取標籤**

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 其他需求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>無 </p> </td> 
   <td colname="col2"> <p>如果此變數包含的資料中，不包括資料隱私權存取請求中傳回至資料主體的必要資料，請選取此選項。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p><u>所有</u>資料隱私權存取請求皆應包含此欄位中的值。 </p> <p>如果此值來自多人共享的裝置，則您身為資料控管者可藉由套用此標籤，表明此欄位資料可與任何具備該共享裝置存取權限的人共享。 </p> </td> 
   <td colname="col3"> <p>將會為所有資料隱私權請求傳回帶有此標籤的欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> 只有在相當確定點擊來自資料主體時 (可透過符合 ID-PERSON 欄位值的資料隱私權請求 ID 來判斷)，資料隱私權請求才可包含此欄位中的值。 </p> </td> 
   <td colname="col3"> <p>您也必須在此報表套裝中的某些變數上設定ID-PERSON標籤，並使用該ID提交請求，否則此標籤將永遠不適用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

雖然很少有變數會收到任何其他標籤，但存取標籤應套用至許多變數。 但是，您應與法律團隊協商，決定您收集的資料應與資料主體共用。

**資料隱私權刪除標籤**

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 其他需求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>與其他標籤不同，這些「刪除」標籤並非互斥。 您可以選擇兩者或無。 不需要單獨的「無」標籤，因為「無」只需不勾選任一「刪除」選項即可。 </p> </td> 
   <td colname="col3"> <p>只有包含允許點擊與資料主體相關聯之值的欄位（即允許識別資料主體）才需要刪除標籤。 </p> <p> 其他個人資訊（我的最愛、瀏覽／購買記錄、健康狀況等）不需要刪除，因為與資料主體的關聯將會中斷。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>對於資料隱私權刪除請求，只有在點擊含有特定 ID-DEVICE 的請求中，才應對此欄位的值進行匿名處理。 </p> <p>如果其他點擊發生相同的值，但未刪除，則不會變更其他例項。 這會導致計算此欄位唯一計數的報表計數變更。 在共用裝置上，這可能會移除資料主體以外的其他個人識別碼。 </p> <p>如果此欄位也具有 ID-DEVICE 標籤，而且以該欄位中的值做為資料隱私權請求的 ID，則計數不會變更。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">也需要I1或I2或S1標籤 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">無法在事件上設定 </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">無法在銷售eVar上設定 </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">無法在分類上設定 </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">您必須使用ID-DEVICE提交請求，或將expandIDs設為true，否則此標籤將不適用。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>對於資料隱私權刪除請求，只有在點擊含有特定 ID-PERSON 的請求中，才應對此欄位的值進行匿名處理。 </p> <p>如果其他點擊發生相同的值，但未刪除，則不會變更其他值。 這會導致計算此欄位唯一計數的報表計數變更。 如果此欄位也具有 ID-PERSON 標籤，而且以該欄位中的值做為資料隱私權請求的 ID，則計數不會變更。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">也需要I1或I2或S1標籤 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">無法在事件上設定 </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">無法在銷售eVar上設定 </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">無法在分類上設定 </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">您也必須在此報表套裝中的某些變數上設定ID-PERSON標籤，並使用該ID提交請求，否則此標籤將永遠不適用。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**資料隱私權身分標籤**

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 其他需求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>無 </p> </td> 
   <td colname="col2"> <p>此變數不包含用於資料隱私權請求的 ID。 </p> </td> 
   <td colname="col3"> <p>如果此欄位含有透過資料隱私權 API 或 UI 提交存取或刪除請求時會使用的 ID，您才需要設定這些標籤中的其中一個。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>此欄位包含的 ID 可用於針對資料隱私權請求識別裝置，但無法辨別共用裝置上的不同使用者。 </p> <p>您不需要為所有包含 ID 的變數指定此標籤 (這是 I1/I2 標籤的作用)。如果您使用儲存在此變數中的 ID 提交資料隱私權請求，而且想要搜尋此變數以找出指定 ID，請使用此標籤。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">也需要I1或I2標籤 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">無法在事件上設定 </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">無法在銷售eVar上設定 </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">無法在分類上設定 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>此欄位包含的 ID 可針對資料隱私權請求識別已驗證的使用者 (特定人員)。 </p> <p>您不需要為所有包含 ID 的變數指定此標籤 (這是 I1/I2 標籤的作用)。如果您要使用儲存在此變數中的 ID 提交資料隱私權請求，而且想要搜尋此變數以找出指定 ID，請使用此標籤。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">也需要I1或I2標籤 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">無法在事件上設定 </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">無法在銷售eVar上設定 </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">無法在分類上設定 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

當您將變數標示為ID-DEVICE或ID-PERSON時，會提示您提供命名空間。 您可以使用先前定義的命名空間或定義新命名空間。

**使用先前定義的命名空間**

如果您先前已將ID標籤指派給登入公司中任何報表套裝中的其他變數，您可以選取其中一個現有名稱空間。 如果此變數包含的ID類型與已使用此名稱空間標示的其他變數相同，且您想在提交請求時搜尋所有變數，則應重複使用namespace。

1. Click **[!UICONTROL Select Namespace]** and select one of the existing namespaces.
1. 按一下 **[!UICONTROL Apply]**.

![](assets/namespace.png)

**定義新的命名空間**

您也可以定義新的命名空間。 我們建議將命名空間字串限制為英數字元，加上底線、破折號和空格字元。 它們將轉換為所有小寫。

1. Click **[!UICONTROL Select Namespace]** and type in the namespace title.

   ![](assets/namespace2.png)

1. 按下 **[!UICONTROL Enter]** 即可新增此命名空間。「套用」按鈕必須等到現在才會啟用。
1. 按一下 **[!UICONTROL Apply]**.

您指定為命名空間的字串，也就是在透過資料隱私權 API 提交請求 (即「namespace」參數的值) 時應使用的字串。然後，請求會導致Adobe Analytics在您所有共用此命名空間的報表套裝中，針對您在請求中指定的ID搜尋所有變數。

您不需要在包含ID的所有變數（I1/I2標籤的用途）上指定ID-DEVICE或ID-PERSON標籤。 如果您要使用儲存在此變數中的 ID 提交資料隱私權請求，而且想要搜尋此變數以找出指定 ID，請使用此標籤。舉例來說，如果 eVar1 含有電子郵件地址，而 eVar2 含有登入使用者名稱，不過您只會以使用者名稱來提交請求，便可以使用命名空間「user name」將 eVar1 標示為 I1、ACC-PERSON、DEL-PERSON，而將 eVar2 標示為 I2、ACC-PERSON、DEL-PERSON、ID-PERSON。接著，您可以利用使用者區段 JSON 區塊來提交請求，如下所示：

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

對於相同報表套裝中的不同變數，可以使用相同的命名空間。 例如，有些自訂實作會將CRM-ID儲存在prop和eVar中。 如果CRM-ID總是出現在其中一個（例如eVar）中，且偶爾只出現在另一個(prop)中，而且在eVar中也不出現在prop中，則只有eVar需要ID標籤和命名空間，因為Adobe只能在該eVar中搜尋ID。 然而如果 CRM-ID 有時候會發生在某個變數中，有時則會發生在另一個變數中，那麼這兩個變數都應該擁有相同的命名空間，而 Adobe 會搜尋這兩個變數，找出在以此命名空間提交之資料隱私權請求中指定 ID 的發生次數。所有這些變數上仍應包含DEL標籤，因此不論值發生在何處，都會進行匿名處理。

另一個例子是，您可能有CRM ID，有時會透過eVar1傳入，有時會透過prop7傳入。 然後，您就有處理規則，將eVar1的值（如果存在）複製到eVar3。 否則，它會將prop7的值複製到eVar3。 在此案例中，eVar3一律會包含已知的CRM ID，因此只有eVar3需要ID-PERSON標籤。

>[!CAUTION] 系統會保留命名空間「visitorId」和「customVisitorId」，以識別 Analytics 舊版追蹤 Cookie 和 Analytics 客戶的訪客 ID。請勿將這些命名空間用於自訂流量或轉換變數。

## 支援的變數類型與資料隱私權/DULE 標籤 {#section_CE7C3EDE1344466A98BC45E394B40762}

資料隱私權/DULE 標籤會影響四大類 Analytics 變數。並非所有變數都支援所有標籤。 此表顯示哪些變數支援或不支援哪些標籤。

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 支援的標籤 </th> 
   <th colname="col3" class="entry"> 不支援的標籤 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">自訂成功事件 </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">銷售eVar </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">多值變數(mvVar) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">階層變數 </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL、ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>分類 </p> </td> 
   <td colname="col2"> <p>I1/I2、S1/S2 </p> <p>ACC-ALL、ACC-PERSON、 </p> </td> 
   <td colname="col3"> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">流量變數(prop) </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">商務變數（非銷售eVar） </li> 
    </ul> </td> 
   <td colname="col2"> <p>所有標籤 </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>大多數其他變數 </p> <p><i>（例外情況見下表）</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL、ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2、S1/S2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## 可指派／修改ACC-ALL/ACC-PERSON以外標籤的變數 {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 群組 </th> 
   <th colname="col2" class="entry"> 變數 </th> 
   <th colname="col3" class="entry"> 可修改的標籤 </th> 
   <th colname="col4" class="entry"> 評論 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">轉換維度 </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">自訂流量維度 </li> 
    </ul> </td> 
   <td colname="col2"> <p>全部，分類除外 </p> </td> 
   <td colname="col3"> <p>全部 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>分類 </p> </td> 
   <td colname="col3"> <p>無/ I1 / I2 </p> <p>無/ S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>轉換事件 </p> </td> 
   <td colname="col2"> <p>全部 </p> </td> 
   <td colname="col3"> <p>無/ S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>解決方案維度和事件 </p> </td> 
   <td colname="col2"> <p>Activity Map 連結, </p> <p>Activity Map 頁面 </p> </td> 
   <td colname="col3"> <p>無/ I1 / I2 </p> <p>無/ DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>變數可包含URL參數，其中可能包含直接或間接可識別的資料。 如果您的實作未收集這些變數中可直接識別或可間接識別的資料，那麼這些資料不需要身分或刪除標籤。 </p> <p>請注意，刪除會清除 URL 參數，但會保留基礎 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料處理維度 </p> </td> 
   <td colname="col2"> <p>自訂訪客 ID </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>您不能移除 ID 或 DEL 標籤 (設定為「無」)，不過您可以根據自訂 ID 實作，將其變更為 DEVICE 或 PERSON 變體。 </p> <p>如果您不使用自訂訪客 ID，那麼採用哪種設定並不重要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">標準維度 </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">資料處理維度 </li> 
    </ul> </td> 
   <td colname="col2"> <p>IP 位址 </p> <p>IP 位址 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>您無法移除DEL標籤，但可以將其變更為DEL-DEVICE或DEL-PERSON或兩者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap 動作 (舊版), </p> <p>ClickMap 內容 (舊版), </p> <p>頁面, </p> <p>頁面 URL、 </p> <p>原始登入頁面 URL, </p> <p>反向連結, </p> <p>造訪開始頁面 URL </p> </td> 
   <td colname="col3"> <p>無/ I1 / I2 </p> <p>無/ DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>變數可包含URL參數，其中可能包含直接或間接可識別的資料。 如果您的實作未收集這些變數中可直接識別或可間接識別的資料，那麼這些資料不需要身分或刪除標籤。 </p> <p>請注意，刪除會清除 URL 參數，但會保留基礎 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 刪除處理 {#section_F3DEE591671A4B16A8E043F91C137ECB}

Adobe Analytics 提供的資料隱私權刪除請求支援，目的為將對報表的影響降至最低。在大多數情況下，報表中顯示的量度應該不會變更。在資料隱私權刪除前執行的歷史報表將會與刪除後執行的報表一致。為了達成此目的，可以完全解除已刪除資料與資料主體的關聯，同時保留無法識別身分的資料；如此一來，報表的值就能維持一致。

下表說明如何「刪除」不同的變數。這不是完整清單。

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 刪除方法 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>·流量變數(prop) </p> <p>·商務變數(eVar) </p> </td> 
   <td colname="col2"> <p>現有值會被新值取代，格式為「Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482」，其中「Data Privacy-」首碼之後的 32 位數十六進位值，為 128 位元強式密碼偽隨機數。由於舊值是以隨機字串取代，故無法由新值反推原始值，亦無法由原始值推導出新值。 </p> <p>對於指定的變數而言，如果同一個資料隱私權請求中被刪除的其他點擊內，也出現相同的值遭到取代，則該值的所有例項都會取代為相同的新值。 </p> <p>如果某個值的某些實例被一個刪除請求替換，而稍後的請求刪除了原始值的其他（新）實例，則新的替換值將與原始替換值不同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購買 ID </p> </td> 
   <td colname="col2"> <p>現有值會被新值取代，格式為「G-7588FCD8642718EC50」，其中「G-」首碼之後的十六進位 18 位數為一組 128 位元強式密碼偽隨機數的前 18 位數。所有適用於刪除流量和商務變數的注釋也適用於此處。 </p> <p>購買ID是交易ID，其主要目的是確保購買不會計入兩次，例如當某人重新整理其購買確認頁面時。 ID本身可能會將購買系結至您自己的資料庫中記錄購買的列。 在大多數情況下，不需要刪除此ID，因此預設不會刪除它。 若您在提出資料隱私權刪除自有資料請求後，購買仍可反向繫結使用者，則您可能需要刪除該欄位，這樣該訪客的 Analytics 資料就無法反向繫結購買者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪客 ID </p> </td> 
   <td colname="col2"> <p>值是128位元整數，會以加密的128位元偽隨機值取代。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• 自訂訪客 ID </p> <p>• IP 位址 </p> <p>• IP 位址 2 </p> </td> 
   <td colname="col2"> <p>這個值會遭清除 (根據變數類型而設定為空字串或 0)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• ClickMap 動作 (舊版) </p> <p>• ClickMap 內容 (舊版) </p> <p>• 頁面 </p> <p>• 頁面 URL </p> <p>• 原始登入頁面 URL </p> <p>• 反向連結 </p> <p>• 造訪開始頁面 URL </p> </td> 
   <td colname="col2"> <p>會清除／移除URL參數。 如果值看起來不像URL，則會清除該值（設為空字串）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• 緯度 </p> <p>• 經度 </p> </td> 
   <td colname="col2"> <p>精度降至1公里以上。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 不支援預期刪除標籤的變數 {#section_956B766EFFEC427E87E6CFF3A4217E86}

本節旨在釐清不支援刪除之 Analytics 變數的相關資訊。有時候，這些變數會遭到非 Analytics 使用者 (例如法務團隊)　刪除，而這些人並不瞭解變數中包含的資料類型，僅根據變數的名稱做出不正確的假設。以下為其中一些變數的清單，以及這些變數不需要刪除，或者為這些變數不需要特定的刪除標籤的原因。

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 備註 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>新訪客 ID </p> </td> 
   <td colname="col2"> <p>新訪客ID是布林值，在我們第一次看到指定訪客ID時為true。 訪客ID匿名後，就不需要刪除它。 匿名後，它會對應至我們第一次看到這個匿名ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>郵遞區號 </p> <p>地理郵遞區號 </p> </td> 
   <td colname="col2"> <p>郵遞區號僅針對源自美國的點擊設定。 它們不適用於來自歐盟的點擊。 即使設定好，也只提供廣泛的地理區域，使資料主體的重新識別變得困難。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地理緯度 </p> <p>地理經度 </p> </td> 
   <td colname="col2"> <p>這些提供從IP位址衍生的粗略位置。 其精確度通常與郵遞區號的精確度類似，離實際位置不到幾十公里。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者代理 </p> </td> 
   <td colname="col2"> <p>使用者代理會識別所使用的瀏覽器版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者 ID </p> </td> 
   <td colname="col2"> <p> 指定包含資料的Analytics報表套裝（以數字表示）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表套裝 ID </p> </td> 
   <td colname="col2"> <p> 指定包含資料的Analytics報表套裝名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪客 ID </p> <p>MCID / ECID </p> </td> 
   <td colname="col2"> <p> 這些標籤具有DEL-DEVICE標籤，但無法添加DEL-PERSON標籤。 If you specify <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> ID Expansion</a> with each request, then these IDs will automatically be deleted for all delete requests, even those using an ID-PERSON. </p> <p>如果您不使用ID擴增，但希望這些Cookie ID在prop或eVar中包含相符ID的點擊上匿名化，您可以使用ID-DEVICE標籤來標籤prop或eVar，以解決此標籤限制，即使它確實識別人員（所有DEL-PERSON標籤也必須變更為DEL-DEVICE標籤）。 在此情況下，由於只有訪客ID或ECID的某些例項會進行匿名處理，因此獨特訪客計數會在歷史報告中變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p> Adobe Advertising Cloud ID 為解決方案變數，具有不可修改的 DEL-DEVICE 標籤。它會從Cookie填入，就像訪客ID和MCID一樣。 每當刪除其他ID時，應從點擊中刪除該ID。 如需詳細資訊，請參閱這些變數的說明。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 存取請求的日期欄位 {#section_6678FB4FF42B481C9B78E64F61782397}

共有五個標準變數包含時間戳記：

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 時間戳記 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>點擊時間 UTC </p> </td> 
   <td colname="col2"> <p>Adobe Analytics收到點擊的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定點擊時間 UTC </p> </td> 
   <td colname="col2"> <p>點擊發生的時間，對於某些行動應用程式和其他實施而言，此時間可能早於收到點擊的時間。 例如，如果發生網路連線時無法使用，應用程式可能會保留點擊並在連線可用時傳送。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期時間 </p> </td> 
   <td colname="col2"> <p>與「自訂點擊時間 UTC」值相同，但採用報表套裝的時區，而非 GMT。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次點擊時間 GMT </p> </td> 
   <td colname="col2"> <p>針對此點擊的訪客ID值收到的首次點擊的自訂點擊時間UTC值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>造訪開始時間 UTC </p> </td> 
   <td colname="col2"> <p>收到此訪客 ID 值當次造訪首次點擊的自訂點擊時間 UTC 值。</p> </td> 
  </tr> 
 </tbody> 
</table>

針對按資料隱私權存取請求傳回的檔案，產生這些檔案的程式碼會要求存取請求 (有適用這類要求的 ACC 標籤) 中，須納入前三個時間戳記變數中的其中一個。如未納入任一變數，則自訂點擊時間 UTC 會視同具有 ACC-ALL 標籤。

按資料隱私權存取請求傳回的點擊層級 CSV 檔案，會將這些欄位中採 Unix 時間戳記的值，轉換為日期/時間欄位的格式，即 YYYY-MM-DD HH:MM:SS (例如 2018-05-01 13:49:22)。在摘要 HTML 檔案中，這些時間戳記值會遭截斷，僅包括日期 (YYYY-MM-DD)，以減少這些欄位中所產生的不重複值數量。
