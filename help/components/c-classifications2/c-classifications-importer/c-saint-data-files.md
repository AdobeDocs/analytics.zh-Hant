---
description: 匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。
seo-description: 匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。
seo-title: 分類資料檔案
solution: Analytics
subtopic: 分類
title: 分類資料檔案
topic: 管理工具
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 分類資料檔案

匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。

為了協助您建立有效的資料檔案，您可以下載範本檔案，它能提供檔案結構以供您將分類資料貼入。有關詳細資訊，請參閱 [下載分類範本](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).

See [General File Structure](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) for more information about character limits in classifications.

See [Numeric 2 Classifications](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) for information about uploading data using numeric 2 classifications.

## 一般檔案結構

以下是範例資料檔案的圖例:

![](assets/completed-saint-file.png)

資料檔案必須符合以下結構規則:

* 分類不能具有 0 (零) 的值。
* Adobe 建議您將匯入和匯出上限設為 30 欄。
* 更新檔案應使用 UTF-8 不含 BOM 字元編碼。
* 可以在儲存格中內嵌定位字元、新行字元和引號等特殊字元，前提是已指定 v2.1 檔案格式且儲存格已正確[逸出](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)。特殊字元包括:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   逗號不是特殊字元。

* 分類不可包含脫字符號 (^)，因為此字元用於標示子分類。
* 請謹慎使用連字號。例如，您若是在 Social 詞語中使用連字號 (-)，Social 會將連字號辨識為 [!DNL Not] 運算元 (減號)。For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* 系統會強制使用字元限制來分類報告資料。例如，如果您上傳產品名稱超過100個字元（位元組）的產品( *`s.products`*)分類文字檔案，產品將不會顯示在報表中。 追蹤程式碼和所有的自訂轉換變數 (eVar) 可以使用 255 個位元組。
* 以定位點分隔的資料檔案 (使用任何試算表應用程式或文字編輯器建立範本檔案)。
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* 井字號 (#) 能將文字行識別為使用者註解。Adobe 會略過任何開頭為 # 的文字行。
* 兩個井字號再加上 SC (## SC) 能將文字行識別為報告使用的前處理標題註解。請勿刪除這些文字行。
* 如果索引鍵中有新行字元，分類匯出可以有重複的索引鍵。在 FTP 或瀏覽器匯出中，這可透過開啟 FTP 帳戶的引號來解決。此功能會在含有新行字元的每個索引鍵周圍加上引號。
* 匯入檔案第一行的 C1 儲存格包含版本識別碼，可決定分類如何處理檔案其餘部分使用的引號。

   * v2.0 會忽略引號並假設它們都屬於指定鍵和值的一部分。例如這個值: "這是""一些值"""。v2.0 會按字面含義將此解析為: "這是""一些值"""。
   * v2.1 則會告訴分類將引號假設為 Excel 檔案使用的檔案格式一部分。因此，v2.1 會將上述範例設為下列格式: 這是"一些值"。
   * 如果在檔案中指定 v2.1，但實際需要的卻是 v2.0 (亦即以違反 Excel 格式的方法使用引號)，便可能出現問題。例如，如果檔案中有下列值: "VP NO REPS" S/l Dress w/ Overlay，且您使用 v2.1，則這是不正確的格式 (此值應置於左右引號之間，且屬於實際值一部分的引號應該逸出引號)，因此分類無法繼續進行後續程序。
   * 請務必執行下列任一作業: 變更上傳檔案的標題 (C1 儲存格) 以將檔案格式變更為 v2.0，「或是」在檔案中正確置入 Excel 引號。

* 資料檔案的第一個資料行 (非註解) 含有識別該欄之分類資料所用的欄標題。匯入工具須有特定的欄標題格式。有關詳細資訊，請參閱 [欄標題格式](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).
* 在資料檔案中，緊接在標題行後方的是資料行。每個資料行都應包含每個欄標題的資料欄位。
* 資料檔案支援以下控制代碼，Adobe 會將這些代碼用於提供檔案結構，以及正確匯入分類資料:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 控制代碼 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;新行&gt; </p> </td> 
   <td colname="col2"> <p>新行的字元是資料檔案中資料行/記錄之間唯一支援的分隔字元。您通常只在撰寫自動產生資料檔案的程式時，才需要明確地插入這些字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>要求 Adobe 自動為此元素產生唯一 ID。 </p> <p>在促銷活動內容中，此控制值能指示 Adobe 將識別碼指定給每個創作元素。請參閱 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 代碼 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指出資料欄代表與項目相關的資料範圍。請參閱 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 日期 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空欄位 </p> </td> 
   <td colname="col2"> <p>代表目前的欄位中含有 NULL 值。當特定資料欄不適用於目前的記錄時，請使用此表示法。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修飾詞 </p> </td> 
   <td colname="col2"> <p>指出資料欄代表 <span class="wintitle">PER 修飾詞</span>欄位。See <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [常見上傳問題](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## 欄標題格式

> [!NOTE]Adobe 建議您將匯入和匯出上限設為 30 欄。

分類檔案支援下列欄標題:

### 金鑰

每個值在整個系統內必須是唯一的。The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site's [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### 分類欄標題

例如，Reports &amp; Analytics 會自動包含「[!UICONTROL 促銷活動]」變數的兩個分類:「[!UICONTROL 促銷活動]」和「[!UICONTROL 創作元素]」。若要將資料新增至「[!UICONTROL 促銷活動]」分類，則分類資料檔案中的欄標題應是「[!UICONTROL 促銷活動]」。

> [!NOTE] 分類欄標題中 [!UICONTROL 的值] ，必須完全符合分類的命名慣例，否則匯入會失敗。 例如，若管理員在「[!UICONTROL 促銷活動設定管理員]」中將「[!UICONTROL 促銷活動]」變更為[!UICONTROL 內部促銷活動名稱]，則檔案欄標題也必須一併變更。

此外，資料檔案支援以下額外的標題慣例，以便識別子分類和其他專業的資料欄:

### 子分類標題

例如，[!UICONTROL Campaigns^Owner] 是含有 [!UICONTROL Campaign Owner] 值的資料欄所用的欄標題。同樣地，[!UICONTROL Creative Elements^Size] 是含有 [!UICONTROL Creative Elements] 分類 [!UICONTROL Size] 子分類的資料欄所用的欄標題。

### 分類量度標題

例如，[!UICONTROL Campaigns^~Cost] 表示「[!UICONTROL 促銷活動]」分類中的「[!UICONTROL 成本]」量度。

### PER修飾詞標題

*`Per Modifier`* 標題的表示方式是新 *`~per`* 增至分類度量標題。 For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe支援下列關 *`PER Modifier`* 鍵字：

這些字元在資料檔案中有具有特殊意義。因此請盡可能避免在屬性名稱和資料中使用這些文字。

**FIXED:** 固定的值。不執行任何調整。

**DAY:** 用報告內的天數乘以該數值。

**ORDER:** 用報告中行項目的訂單數乘以該數值。

**CHECKOUT:** 用報告中行項目的結帳數乘以該數值。

**UNIT:** 用報告中行項目的單位數乘以該數值。

**REVENUE:** 用報告中行項目的收入額乘以該數值。

**SCADD:** 用報告中每行項目之[!UICONTROL 購物車新增]事件的呼叫次數乘以該數值。

**SCREMOVE:** 用報告中每行項目之[!UICONTROL 購物車移除]事件的呼叫次數乘以該數值。

**INSTANCE:** 用報告中行項目的例項數乘以該數值。

**CLICK:** 用報告中行項目的點按次數乘以該數值。

**EVENT:** 用報告內每行項目指定的自訂事件發生次數乘以該數值。

**** 範例：如果促銷活動A的成本為$10,000, [!UICONTROL Campaigns^~Cost] 欄會包含10000值，而 [!UICONTROL Campaigns^~~Costper] 欄會包含 [!UICONTROL FIXED]。 在報告中顯示「促銷活動 A」的「成本」時，會在日期範圍內將 $10,000 顯示為「促銷活動 A」的固定成本。

**** 範例：如果促銷活動B的每次點按成本約為$2, [!UICONTROL Campaigns^~Cost] 欄會包含2，而 **[!UICONTROL Campaigns^~~Costper]** 欄會包含 [!UICONTROL CLICK]。 When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. 這將為您提供基於促銷活動 B 所執行點按次數的總成本計算。

### 日期

促銷活動日期通常是與個別促銷活動相關的範圍 (開始日期和結束日期)。日期的顯示格式應為 YYYY/MM/DD。例如: 2013/06/15-2013/06/30。

有關詳細資訊，請參閱「[轉換分類](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)」。

> [!NOTE] 在2018年5月10日的 [!DNL Analytics] 「維護」發行中，Adobe開始限制啟用日期和數值分類的功能。 這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增日期啟用和數值分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL 分類] ，可用來指派日期範圍至促銷活動或其他轉換分 [!UICONTROL 類]，以便更精確地測量促銷活動。 指定值的日期範圍後，發生在日期範圍以外的任何相符值都不會予以分類。如果想採用促銷活動的確實上線日期 (而非符合促銷活動的所有點擊) 來進行促銷活動測量，這個方法會很有用。為了成功分類某個日期範圍的值，必須符合下列條件:

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 相關的日期範圍必須包含開始日期和 (可選) 結束日期。

若要根據日期範圍來分類促銷活動:

1. 登入並 [!DNL Analytics] 前往「管理&gt;分類」。
1. 按一下&#x200B;**[!UICONTROL 「瀏覽器匯出」]標籤，確定啟用日期的分類設定正確，然後按一下「匯出檔案」。**
1. 在 Microsoft Excel 或您熟悉的其他試算表編輯器中開啟檔案。
1. 其中一欄會以

   ^~期間~，此欄是要輸入日期範圍的欄。
1. 在該欄下方，以下列格式輸入每個值的日期範圍:

   `YYYY/MM/DD - YYYY/MM/DD`。並確保:

   * 在破折號兩側留空格。
   * 使用連字號 (-) 來區隔範圍，而非短破折號或長破折號。
   * 如果月或天是一位數，需加上前置零。
   * 必須有開始日期範圍，但結束日期範圍為選用。

1. 儲存檔案，並前往「管理 [!DNL Analytics] 員」將其上傳|分類|匯入檔案。

> [!NOTE] 特定索引鍵值不能有超過一個日期範圍。

## 分類疑難排解

* [常見的 上傳問題](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): 說明因錯誤的檔案格式和檔案內容所引起問題的知識庫文章。

