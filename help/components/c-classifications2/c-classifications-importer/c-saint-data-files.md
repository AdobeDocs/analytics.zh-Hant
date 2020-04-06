---
description: 匯入工具可讓您將分類資料大量上傳至檔案中的分析報表。 匯入需要特定的檔案格式才能成功上傳資料。
subtopic: Classifications
title: 分類資料檔案
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 分類資料檔案

匯入工具可讓您將分類資料大量上傳至檔案中的分析報表。 匯入需要特定的檔案格式才能成功上傳資料。

為協助您建立有效的資料檔案，您可以下載範本檔案，提供檔案結構，以便將分類資料貼入其中。 如需詳細資訊，請參 [閱下載分類範本](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)。

請參閱[一般檔案結構](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)，取得關於分類中字元限制的相關資訊。

請參閱[數值 2 分類](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md)，取得使用數值 2 分類上傳資料的相關資訊。

## 一般檔案結構

以下是範例資料檔案的圖例：

![](assets/completed-saint-file.png)

資料檔案必須符合以下結構規則：

* 分類的值不能是0（零）。
* Adobe 建議您將匯入和匯出上限設為 30 欄。
* 上傳的檔案應使用UTF-8而不使用BOM字元編碼。
* 特殊字元（例如制表符、新行和引號）可內嵌在儲存格中，但必須指定v2.1檔案格式且儲存格已正確逸出 [即可](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)。 特殊字元包括：

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   逗號不是特殊字元。

* 分類不能包含脫字元號(^)，因為此字元用來表示子分類。
* 使用連字型大小時請小心。 例如，您若是在 Social 詞語中使用連字號 (-)，Social 會將連字號辨識為 [!DNL Not] 運算元 (減號)。例如，您若使用匯入項目指定 *`fragrance-free`* 為詞語，Social 會將詞語辨識為 fragrance *`minus`* free，並收集提及 *`fragrance`* 但不包含 *`free`* 的字。
* 系統會強制使用字元限制來分類報告資料。例如，如果您上傳產品名稱超過 100 個字元 (位元組) 的產品分類文字檔 (*`s.products`*)，產品將不會顯示在報表中。追蹤代碼和所有自訂轉換變數(eVar)允許255個位元組。
* 以定位點分隔的資料檔案 (使用任何試算表應用程式或文字編輯器建立範本檔案)。
* 副檔名為 [!DNL .tab] 或 [!DNL .txt]。
* 井字型大小(#)會將該行識別為使用者註解。 Adobe會忽略以#開頭的任何行。
* 後接SC(## SC)的雙井號會將該行識別為報告使用的預處理標題註解。 請勿刪除這些行。
* 由於索引鍵中有新行字元，分類匯出可能有重複的索引鍵。 在FTP或瀏覽器匯出中，這可透過開啟FTP帳戶的引號來解決。 這會在每個鍵周圍加上引號，加上新行字元。
* 匯入檔案第一行中的儲存格C1包含版本識別碼，可決定分類如何處理在檔案其餘部分使用引號的問題。

   * v2.0會忽略引號，並假定這些引號都屬於指定的索引鍵和值。 例如這個值：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。v2.0 會按字面含義將此解析為：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。
   * v2.1會讓分類假設引號是Excel檔案中使用之檔案格式的一部分。 因此，v2.1 會將上述範例設為下列格式：這是&quot;一些值&quot;。
   * 當在檔案中指定v2.1時，可能會發生問題，但實際需要的是v2.0 —— 即當引號以Excel格式設定下不合法的方式使用時。 例如，如果檔案中有下列值：&quot;VP NO REPS&quot; S/l Dress w/ Overlay，在v2.1中，這是不正確的格式（值應以開啟和關閉引號括住，而屬於實際值一部分的引號應以引號逸出），分類不會超過此點。
   * 請務必執行下列任一作業：變更上傳檔案的標題 (C1 儲存格) 以將檔案格式變更為 v2.0，「或是」在檔案中正確置入 Excel 引號。

* 資料檔案的第一列（非註解）包含用來識別該欄中分類資料的欄標題。 匯入工具需要特定的欄標題格式。 如需詳細資訊，請參 [閱欄標題格式](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)。
* 資料檔案中緊接在標題列後面的是資料列。 每行資料應包含每個欄標題的資料欄位。
* 資料檔案支援以下控制代碼，Adobe 會將這些代碼用於提供檔案結構，以及正確匯入分類資料：

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
   <td colname="col2"> <p>新行字元是資料檔案中資料行／記錄之間唯一支援的分隔字元。 通常，在編寫自動生成資料檔案的程式時，您只需要明確插入這些字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>要求Adobe自動為此元素產生唯一ID。 </p> <p>在促銷活動內容中，此控制值會指示Adobe為每個創作元素指派識別碼。 請參閱 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 金鑰 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指定資料欄代表與項目關聯的日期範圍。 請參閱 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 日期 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空白欄位 </p> </td> 
   <td colname="col2"> <p>代表目前欄位的NULL值。 如果特定資料列不適用於當前記錄，請使用此選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER修飾詞 </p> </td> 
   <td colname="col2"> <p>指出資料欄代表 <span class="wintitle">PER 修飾詞</span>欄位。請參閱 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >PER 修飾詞標題</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)


## 欄標題格式

>[!NOTE]Adobe 建議您將匯入和匯出上限設為 30 欄。

分類檔案支援下列欄標題：

### 金鑰

每個值在整個系統內必須是唯一的。此欄位中的值與在網站之 [!DNL JavaScript] 指標中指定給 [!DNL Analytics] 變數的值對應。此欄中的資料可以包含 ~autogen~ 或其他任何唯一的追蹤程式碼。

### 分類欄標題

例如，報告與分析會自動包含兩個變數的 [!UICONTROL Campaign] 分類： [!UICONTROL Campaigns] 和 [!UICONTROL Creative Elements]。 若要新增資料至 [!UICONTROL Campaigns] 分類，分類資料檔案中的欄標題應為 [!UICONTROL Campaigns]。

>[!NOTE] 欄標題中的 [!UICONTROL Classifications] 值必須完全符合分類的命名慣例，否則匯入會失敗。 例如，如果管理員在中 [!UICONTROL Campaigns] 變更 [!UICONTROL Internal Campaign Names] 為 [!UICONTROL Campaign Set-up Manager]，則檔案列標題必須變更為匹配。

此外，資料檔案支援以下額外的標題慣例，以便識別子分類和其他專業的資料欄：

### 子分類標題

例如， [!UICONTROL Campaigns^Owner] 是包含值的列的列標 [!UICONTROL Campaign Owner] 題。 同樣地， [!UICONTROL Creative Elements^Size] 是包含分類子分類之 [!UICONTROL Size] 欄的欄標題 [!UICONTROL Creative Elements] 。

### 分類量度標題

For example, [!UICONTROL Campaigns^~Cost] refers to the [!UICONTROL Cost] metric in the [!UICONTROL Campaigns] classification.

### PER 修飾詞標題

*`Per Modifier`* 修飾詞標題的表示方法為在分類量度標題中加上 *`~per`*。例如，如果 *`Metric`* 標題為 *`Campaigns^~Cost`*，PER 修飾詞標題即為 *`Campaigns^~Cost~per`*。Adobe 支援下列 *`PER Modifier`* 關鍵字：

這些字元在資料檔案中有特殊意義。 盡可能避免在屬性名稱和資料中使用這些字詞。

**FIXED**：固定的值。請勿執行任何縮放。

**DAY**：用報告內的天數乘以該數值。

**ORDER**：用報告中行項目的訂單數乘以該數值。

**CHECKOUT**：用報告中行項目的結帳數乘以該數值。

**UNIT**：用報告中行項目的單位數乘以該數值。

**REVENUE**：用報告中行項目的收入額乘以該數值。

**SCADD:** 將值乘以報告中每行項目 [!UICONTROL Shopping Cart Add] 中事件被呼叫的次數。

**SCREMOVE:** 將值乘以報告中每行項目 [!UICONTROL Shopping Cart Remove] 中事件被呼叫的次數。

**INSTANCE**：用報告中行項目的例項數乘以該數值。

**CLICK**：用報告中行項目的點按次數乘以該數值。

**EVENT**：用報告內每行項目指定的自訂事件發生次數乘以該數值。

**範例：** 如果促銷活動A的成本為$10,000, [!UICONTROL Campaigns^~Cost] 則欄會包含值10000，而 [!UICONTROL Campaigns^~~Costper] 欄會包含 [!UICONTROL FIXED]。 在報告中顯示「促銷活動 A」的「成本」時，會在日期範圍內將 $10,000 顯示為「促銷活動 A」的固定成本。

**範例：** 如果促銷活動B的每次點按成本約為$2, [!UICONTROL Campaigns^~Cost] 則欄會包含2, **[!UICONTROL Campaigns^~~Costper]** 欄會包含 [!UICONTROL CLICK]。 在報表中顯示「促銷活動 B 的成本」時，Adobe 會在報表的日期範圍內即時計算 (2 * [點按次數])。這將為您提供基於促銷活動 B 所執行點按次數的總成本計算。

### 日期

促銷活動日期通常是與個別促銷活動相關的範圍（開始和結束日期）。 日期應以YYYY/MM/DD格式顯示。 例如：2013/06/15-2013/06/30。

如需詳細資訊，請參閱 [轉換分類](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)。

>[!NOTE] 在 2018 年 5 月 10 日的[!DNL Analytics]維護發行中，Adobe 已開始限制日期啟用和數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。不能新增啟用日期和數值分類。 但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] 可用來指派日期範圍給您的促銷活動或其他轉換，以 [!UICONTROL classifications]便更精確地測量促銷活動。 指定值的日期範圍後，任何發生在日期範圍以外的相符值都不會分類。 這對於想要利用促銷活動的確切「即時」日期（而非所有符合促銷活動本身的點擊）的促銷活動測量非常有用。 為了成功分類某個日期範圍的值，必須符合下列條件：

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 相關日期範圍必須包含開始日期和（可選）結束日期。

若要根據日期範圍來分類促銷活動：

1. 登入 [!DNL Analytics] 並前往「管理員 > 分類」。
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. 在 Microsoft Excel 或您熟悉的其他試算表編輯器中開啟檔案。
1. 其中一欄結尾會是

   ^~period~，需在此欄輸入日期範圍。
1. 在該欄下方，以下列格式輸入每個值的日期範圍：

   `YYYY/MM/DD - YYYY/MM/DD`。並確保：

   * 在破折號兩側留空格。
   * 使用連字型大小(-)來分隔範圍，而非短破折號或長破折號。
   * 如果月或日是單位數，表示前導零。
   * 必須有開始日期範圍，但結束日期範圍為選用。

1. 儲存檔案並前往「管理員 | 分類 | 匯入檔案」，將其上傳至 [!DNL Analytics]。

>[!NOTE] 一個具體的鍵值只能有一個日期範圍。

## 分類的疑難排解

* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)：說明因錯誤的檔案格式和檔案內容所引起問題的知識庫文章。

