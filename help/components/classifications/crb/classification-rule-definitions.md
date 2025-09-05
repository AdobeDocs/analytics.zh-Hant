---
description: 「分類規則產生器」裡頁面上之介面元素的定義。
title: 分類規則 - 定義
feature: Classifications
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 94%

---

# 分類規則定義（舊版）

{{classification-rulebuilder-deprecation}}

「分類規則產生器」裡頁面上之介面元素的定義。

## 規則頁面

這個頁面會顯示規則集裡的規則。

![](assets/classification_rules_page.png)

**定義**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>選取報表套裝和變數 </p> </td> 
   <td colname="col2"> <p><b>報表套裝</b> </p> <p>要套用規則集的報表套裝。 </p> <p><b>變數</b> </p> <p>建立分類規則集時，只能套用一個變數。如果要為一個變數建立多個規則集，必須將每個規則集套用到多個報表套裝。 </p> <p>注意：您只能在報表套裝中使用您有權存取的變數。必須先為變數定義至少一個分類，變數才會顯示在<span class="wintitle">「新的規則集」</span>面板中。 </p> <p> 您可以在<span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">報表套裝</span> &gt; <span class="uicontrol">流量</span> &gt; <span class="uicontrol">流量分類」</span>(或<span class="uicontrol">「轉換</span> &gt; <span class="uicontrol">轉換分類」</span>) 中建立變數的分類。然後選取變數，再按一下<span class="uicontrol">「新增分類」</span>。 </p> <p>請參閱「管理說明」裡的「<a href="/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md"  >流量分類</a>」和「<a href="/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md"  >轉換分類</a>」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 啟動</span> </p> </td> 
   <td colname="col2"> <p>驗證及啟動規則。每日均會處理作用中的規則，通常會往回追溯一個月內的分類資料並予以檢查。規則會自動檢查是否有新值並上傳分類。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 停用</span> </p> </td> 
   <td colname="col2"> <p>停用規則，讓您能夠編輯和測試規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定報表套裝和變數 </p> </td> 
   <td colname="col2"> <p>顯示<span class="wintitle">「可用報表套裝」</span>頁面，您可在其中選取要用於所有規則集的一或多個可用報表套裝。(當您首次執行<span class="wintitle">「分類規則產生器」</span>時，也會顯示此頁面)。 </p> <p>此功能的用意是在您有數百個可用報表套裝時，降低報表套裝的載入時間。 </p> <p>建立規則時若按一下<span class="uicontrol">「新增套裝」</span>，您在此選取的報表套裝就可在規則層級使用。 </p> <p>注意：<span class="term">只有</span>當已在<span class="wintitle">管理工具</span>中為該變數定義至少一個分類時，報表套裝才可供使用。 <p>(請參閱<a href="/help/components/classifications/crb/classification-rule-set.md"  >分類規則集</a>中的<span class="term">變數</span>，取得此先決條件的說明。) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>規則會覆寫任何現有的值 </p> </td> 
   <td colname="col2"> <p> (預設設定) 一律覆寫現有分類索引，包括透過匯入工具 (SAINT) 上傳的分類。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>規則僅會覆寫未設定的值 </p> </td> 
   <td colname="col2"> <p>只會填入空白 (未設定) 的儲存格。現有分類不會變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>回顧期間 </p> </td> 
   <td colname="col2"> <p>當您啟動及驗證規則時，可以指定規則是否應該覆寫受影響之索引鍵的現有分類。(只有先前在您指定時段內所傳入的 <span class="keyword">Adobe Analytics</span> 已分類索引鍵會受到影響。) </p> <p>若您未指定<span class="term">回顧期間</span>，則規則會概略往回追溯一個月（取決於當天為該月何日）。 除非啟用此選項，否則不會覆寫現有的分類。 </p> <p><b>開發中心</b>：合作夥伴可以在<span class="wintitle">開發中心</span>建立分類規則。當客戶啟動整合時就會部署這些規則。在<span class="wintitle">開發中心</span>中，「<span class="uicontrol">覆寫開始時間</span>」選項可讓合作夥伴指定在啟動或編輯整合時，客戶能否決定覆寫值。 </p> <p>請參閱<a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >規則的處理方式</a>，取得規則處理的詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > 新增規則 </a> </td> 
   <td colname="col2"> <p>可讓您新增規則到規則集。 </p> <p>注意：如果一個值在一組規則裡符合兩次以上，系統會使用最後一個規則將值分類。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 草稿</span> </td> 
   <td colname="col2"> 可讓您指定規則是處於草稿模式。草稿狀態可讓您在執行規則之前先測試規則。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 複製</span> </td> 
   <td colname="col2"> 複製 (拷貝) 規則集，以便將規則集套用到其他變數，或套用到不同報表套裝裡的同一個變數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > 測試規則集 </a> </p> </td> 
   <td colname="col2"> <p>可讓您測試規則集的有效性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 匹配條件</span> </td> 
   <td colname="col2"> 指定要讓規則使用的條件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 分類動作</span> </td> 
   <td colname="col2"> <p>指定發生「匹配條件」時要採取的動作。 </p> <p>例如，您將「促銷活動名稱」設定為 $2，這會將追蹤程式碼裡的位置 2 識別為「促銷活動名稱」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>規則編號。 </p> <p>如需詳細資訊，請參閱<a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >規則的處理方式</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 選擇規則類型</span> </td> 
   <td colname="col2"> <p>每一個規則集套用到一個特定的變數。有效的選項有： </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">開頭為 </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">結尾為 </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">包含 </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > 規則運算式 </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 輸入匹配準則</span> </td> 
   <td colname="col2"> 您在索引鍵中尋找的文字模式。這些準則可以是搜尋詞、字元或規則運算式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 設定分類</span> </td> 
   <td colname="col2"> 如果符合匹配準則時，要設定的分類欄。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 結束日期</span> </td> 
   <td colname="col2"> 如果符合匹配準則時，您要為選取之分類欄指定的值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 篩選 </td> 
   <td colname="col2"> 可讓您搜尋規則。 </td> 
  </tr> 
 </tbody> 
</table>

## 規則運算式頁面 {#section_C932A5469E774841B2229965A154163C}

您可以在「[!UICONTROL 規則運算式]」頁面上編輯規則運算式。

![](assets/regex_tracking_code.png)

**定義**

| 元素 | 說明 |
|---|---|
| 範例密鑰 | 要使用的測試字串。例如，您可以利用追蹤程式碼中的特定字元建立分類。您可以匹配特定的字元、字詞或字元模式。 |
| 匹配群組 | 顯示規則運算式對應到促銷活動 ID 字元的情形，以便您能夠將促銷活動 ID 裡的位置分類。 |
| 匹配結果 | 顯示字串中與規則運算式成功匹配的部分。 |

請參閱分類規則[中的](/help/components/classifications/crb/classification-quickstart-rules.md)規則運算式。

## 測試頁面 {#section_EC926F97901C4E65901413F9683AA70A}

這個頁面可以讓您測試規則集裡的規則。

**定義**

| 元素 | 說明 |
|---|---|
| 執行測試 | 當您測試規則集時，使用報告中的索引鍵查看規則集對它們有何影響。 |
| 篩選 | 篩選「[!UICONTROL 結果]」面板裡的值。 |
