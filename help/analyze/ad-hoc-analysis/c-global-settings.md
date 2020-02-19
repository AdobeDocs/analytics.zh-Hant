---
description: 設定全域行為設定例如，您可以設定自動儲存、圖表和表格設定，以及指定字型和地區。
title: 設定
uuid: 34444052-479b-4923-b379-a03ca614bf3e
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 設定

設定全域行為設定例如，您可以設定自動儲存、圖表和表格設定，以及指定字型和地區。

## 設定 {#concept_D21E3D6F13EA4F97913F60C243B72173}

設定全域行為設定例如，您可以設定自動儲存、圖表和表格設定，以及指定字型和地區。

按一下&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 設定]**&#x200B;存取[!UICONTROL 全域設定]。

## 一般設定標籤 - 定義 {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

設定資料來源、專案儲存、圖表和表格方面的行為設定。

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 資料設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">計算重複例項</span>：指定是否在報告中計算例項。這表示，如果同一個變數有多個連續值，您可以將這些值視為變數的一或多個例項。 </p> <p>例如，您可能看到重複頁面重新載入，也就是網站的網頁在單一造訪期間重新載入或重新整理的次數。這個選項可讓您將指定多次點擊同一個網頁視為一次，或是多次網頁檢視。 </p> <p> <span class="uicontrol"><span class="keyword">臨機</span></span>：指定<span class="keyword">「臨機」</span>作為報告資料的唯一來源。此資料來自網頁產生的影像請求。 </p> <p> <span class="uicontrol"><span class="keyword">資料來源</span></span>：指定要使用其他 Adobe 來源或是自訂資料來源所上載的的資料。這些資料將可供 <span class="keyword">Experience Cloud</span> 中的產品使用。請參閱<a href="https://marketing.adobe.com/resources/help/zh_TW/sc/datasources/index.html"  >資料來源</a>，了解更多資訊。 </p> <p> <span class="uicontrol">兩者</span>：(預設) 使用 <span class="keyword">Ad Hoc Analysis</span> 和其他資料來源的資料。 </p> <p>附註：變更這些選項可能會造成 <span class="keyword">Ad Hoc Analysis</span> 資料和 <span class="keyword">Marketing Reports &amp; Analytics 資料</span>之間產生差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自動儲存設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">自動儲存已啟用</span>：啟用自動儲存功能。 </p> <p> <span class="uicontrol">自動儲存專案頻度</span>：可讓您調整自動儲存功能的時間增量。發生臨機當機時才會建立專案自動儲存。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 圖表設定 </p> </td> 
   <td colname="col2"> <p><b>預設摺疊圖表</b>：按一下此按鈕可顯示報表而不在頂端區域顯示圖表。報表以此選項顯示時，您可手動擴展報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 表格設定 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">顯示行數</span>：開啟或關閉報表表格中的行編號。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 排名標籤 - 定義 {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

設定資料如何顯示在欄中，以及選取流量和轉換報表的預設度量。

<!-- 

r_dsc_ranked_tab.xml

 -->

| 欄位 | 定義 |
|--- |--- |
| 列設定 | 設定您希望表格中的儲存格資料，以及圖表中的長條圖應如何顯示。 |
| 選擇預設度量 | 選取「流量」和「轉換」報表的預設度量，以及所有報表的可用度量。包括報表特定預設值：指定在自訂檢視時是否要包括預設度量。 |

## 站點分析標籤 - 定義 {#reference_9DD37C8EF718409E990E149596282FF8}

設定「站點分析」報表的度量和其他圖形設定。

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| 欄位 | 定義 |
|--- |--- |
| 量度 | 選取圓柱體寬度和圓柱體高度所代表的度量。決定度量以什麼顏色顯示，以及表示該度量之低值和高值的顏色。您可以建立 X 和 Y 軸的度量，再從報表的彈出式文字新增您要的其他度量。您亦可反轉要顯示的任何所選度量。 |
| 一般與警報 | 啟動和停用報表的某些圖形元素。您可以設定警報，在圓柱體所代表之頁面相關度量通過特定值時，就會在報表中顯示警報。 |

## 字型和地區標籤 - 定義 {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

指定語言的區域設定，以及預設字型。您必須重新啟動 ，字型和地區變更才能生效。

<!-- 

r_dsc_font_locale.xml

 -->

| 欄位 | 定義 |
|--- |--- |
| 選取地區設定 | 可讓您指定使用者介面中顯示的語言。 |
| 選擇字型 | 讓您指定用來顯示的字型。 |
