---
description: 匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。
title: 分類資料檔案
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: eb6703dc4079678020954984905ee210cbcbbf8f
workflow-type: tm+mt
source-wordcount: '1787'
ht-degree: 100%

---

# 分類資料檔案

匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。

為了協助您建立有效的資料檔案，您可以下載範本檔案，它能提供檔案結構以供您將分類資料貼入。有關詳細資訊，請參閱「[下載分類範本](/help/components/classifications/importer/c-download-saint-data.md)」。

請參閱「[一般檔案結構](/help/components/classifications/importer/c-saint-data-files.md)」，取得關於分類中字元限制的相關資訊。

## 一般檔案結構

以下是範例資料檔案的圖例：

![](assets/completed-saint-file.png)

資料檔案必須符合以下結構規則：

* 分類不能具有 0 (零) 的值。
* Adobe 建議您將匯入和匯出上限設為 30 欄。
* 更新檔案應使用 UTF-8 不含 BOM 字元編碼。
* 可以在儲存格中內嵌定位字元、新行字元和引號等特殊字元，前提是已指定 v2.1 檔案格式且儲存格已正確[逸出](/help/components/classifications/importer/t-classifications-escape-data.md)。特殊字元包括：

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  逗號不是特殊字元。

* 分類不可包含脫字符號 (^)，因為此字元用於標示子分類。
* 請謹慎使用連字號。例如，您若是在 Social 詞語中使用連字號 (-)，Social 會將連字號辨識為 [!DNL Not] 運算元 (減號)。例如，您若使用匯入項目指定 *`fragrance-free`* 為詞語，Social 會將詞語辨識為 fragrance *`minus`* free，並收集提及 *`fragrance`* 但不包含 *`free`* 的字。
* 系統會強制使用字元限制來分類報告資料。例如，如果您上傳產品名稱超過 100 個字元 (位元組) 的產品分類文字檔 (*`s.products`*)，產品將不會顯示在報告中。追蹤程式碼和所有自訂轉換變數 (eVar) 可以使用 255 個位元組。此策略也擴及到分類和子分類欄值，且這些欄值受到相同的 255 個位元組限制。
* 以定位點分隔的資料檔案 (使用任何試算表應用程式或文字編輯器建立範本檔案)。
* 副檔名為 [!DNL .tab] 或 [!DNL .txt]。
* 井字號 (#) 能將文字行識別為使用者註解。Adobe 會略過任何開頭為 # 的文字行。
* 兩個井字號再加上 SC (## SC) 能將文字行識別為報告使用的前處理標題註解。請勿刪除這些文字行。
* 如果索引鍵中有新行字元，分類匯出可以有重複的索引鍵。在 FTP 或瀏覽器匯出中，這可透過開啟 FTP 帳戶的引號來解決。此功能會在含有新行字元的每個索引鍵周圍加上引號。
* 匯入檔案第一行的 C1 儲存格包含版本識別碼，可決定分類如何處理檔案其餘部分使用的引號。

   * v2.0 會忽略引號並假設它們都屬於指定鍵和值的一部分。例如這個值：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。v2.0 會按字面含義將此解析為：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。
   * v2.1 則會告訴分類將引號假設為 Excel 檔案使用的檔案格式一部分。因此，v2.1 會將上述範例設為下列格式：這是&quot;一些值&quot;。
   * 如果在檔案中指定 v2.1，但實際需要的卻是 v2.0 (亦即以違反 Excel 格式的方法使用引號)，便可能出現問題。例如，如果檔案中有下列值：&quot;VP NO REPS&quot; S/l Dress w/ Overlay，且您使用 v2.1，則這是不正確的格式 (此值應置於左右引號之間，且屬於實際值一部分的引號應該逸出引號)，因此分類無法繼續進行後續程序。
   * 請務必執行下列任一作業：變更上傳檔案的標題 (C1 儲存格) 以將檔案格式變更為 v2.0，「或是」在檔案中正確置入 Excel 引號。

* 資料檔案的第一個資料行 (非註解) 含有識別該欄之分類資料所用的欄標題。匯入工具須有特定的欄標題格式。有關詳細資訊，請參閱「[欄標題格式](/help/components/classifications/importer/c-saint-data-files.md)」。
* 在資料檔案中，緊接在標題行後方的是資料行。每個資料行都應包含每個欄標題的資料欄位。
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
   <td colname="col2"> <p>新行的字元是資料檔案中資料行/記錄之間唯一支援的分隔字元。您通常只在撰寫自動產生資料檔案的程式時，才需要明確地插入這些字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>要求 Adobe 自動為此元素產生唯一 ID。 </p> <p>在促銷活動內容中，此控制值能指示 Adobe 將識別碼指定給每個創作元素。請參閱<a href="/help/components/classifications/importer/c-saint-data-files.md"  >索引鍵</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指出資料欄代表與項目相關的資料範圍。請參閱<a href="/help/components/classifications/importer/c-saint-data-files.md"  >日期</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空欄位 </p> </td> 
   <td colname="col2"> <p>代表目前的欄位中含有 NULL 值。當特定資料欄不適用於目前的記錄時，請使用此表示法。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修飾詞 </p> </td> 
   <td colname="col2"> <p>指出資料欄代表 <span class="wintitle">PER 修飾詞</span>欄位。請參閱 <a href="/help/components/classifications/importer/c-saint-data-files.md"  >PER 修飾詞標題</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)

## 欄標題格式

>[!NOTE]
>
>Adobe 建議您將匯入和匯出上限設為 30 欄。

分類檔案支援下列欄標題：

### 金鑰

每個值在整個系統內必須是唯一的。此欄位中的值與在網站之 [!DNL JavaScript] 指標中指定給 [!DNL Analytics] 變數的值對應。此欄中的資料可以包含 ~autogen~ 或其他任何唯一的追蹤程式碼。

### 分類欄標題

>[!NOTE]
>
> [!UICONTROL 分類]欄標題中的值必須與分類的命名慣例完全相符，否則匯入會失敗。例如，若管理員在「[!UICONTROL 促銷活動設定管理員]」中將「[!UICONTROL 促銷活動]」變更為[!UICONTROL 內部促銷活動名稱]，則檔案欄標題也必須一併變更。「金鑰」是保留的分類 (標頭) 值。不支援名為「金鑰」的新分類。

此外，資料檔案支援以下額外的標題慣例，以便識別子分類和其他專業的資料欄：

### 子分類標題

例如，[!UICONTROL Campaigns^Owner] 是含有 [!UICONTROL Campaign Owner] 值的資料欄所用的欄標題。同樣地，[!UICONTROL Creative Elements^Size] 是含有 [!UICONTROL Creative Elements] 分類 [!UICONTROL Size] 子分類的資料欄所用的欄標題。

### 分類量度標題

例如，[!UICONTROL Campaigns^~Cost] 表示「[!UICONTROL 促銷活動]」分類中的「[!UICONTROL 成本]」量度。

### PER 修飾詞標題

*`Per Modifier`* 修飾詞標題的表示方法為在分類量度標題中加上 *`~per`*。例如，如果 *`Metric`* 標題為 *`Campaigns^~Cost`*，PER 修飾詞標題即為 *`Campaigns^~Cost~per`*。Adobe 支援下列 *`PER Modifier`* 關鍵字：

這些字元在資料檔案中有具有特殊意義。因此請盡可能避免在屬性名稱和資料中使用這些文字。

**FIXED**：固定的值。不執行任何調整。

**DAY**：用報告內的天數乘以該數值。

**ORDER**：用報告中行項目的訂單數乘以該數值。

**CHECKOUT**：用報告中行項目的結帳數乘以該數值。

**UNIT**：用報告中行項目的單位數乘以該數值。

**REVENUE**：用報告中行項目的收入額乘以該數值。

**SCADD**：用報告中每行項目之[!UICONTROL 購物車新增]事件的呼叫次數乘以該數值。

**SCREMOVE**：用報告中每行項目之[!UICONTROL 購物車移除]事件的呼叫次數乘以該數值。

**INSTANCE**：用報告中行項目的例項數乘以該數值。

**CLICK**：用報告中行項目的點按次數乘以該數值。

**EVENT**：用報告內每行項目指定的自訂事件發生次數乘以該數值。

**範例**：如果促銷活動 A 的成本為 $10,000，[!UICONTROL Campaigns^~Cost] 欄便含有值 10000，而 [!UICONTROL Campaigns^~Cost~per] 欄含有 [!UICONTROL FIXED]。在報告中顯示「促銷活動 A」的「成本」時，會在日期範圍內將 $10,000 顯示為「促銷活動 A」的固定成本。

**範例**：如果促銷活動 B 每個點按的成本約 $2，[!UICONTROL Campaigns^~Cost] 欄便含有 2，而 **[!UICONTROL Campaigns^~Cost~per]** 欄含有 [!UICONTROL CLICK]。在報告中顯示「促銷活動 B 的成本」時，Adobe 會在報告的日期範圍內即時計算 (2 &#42;[點按次數])。這將為您提供基於促銷活動 B 所執行點按次數的總成本計算。

### 日期

促銷活動日期通常是與個別促銷活動相關的範圍 (開始日期和結束日期)。日期的顯示格式應為 YYYY/MM/DD。例如：2013/06/15-2013/06/30。

有關詳細資訊，請參閱「[轉換分類](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html?lang=zh-Hant)」。

>[!NOTE]
>
>在 2018 年 5 月 10 日的[!DNL Analytics]維護發行中，Adobe 已開始限制日期啟用和數值分類的功能。這些分類類型已從「管理員」和「分類匯入工具」介面中移除。無法新增日期啟用和數值分類。但仍可透過標準分類工作流程來管理 (上傳和刪除) 現有分類，並可繼續在報告中使用。

## 結合使用日期和[!UICONTROL 分類] {#section_966A07B228CD4643B258E73FB8BA150A}

可以使用[!UICONTROL 分類]來指派日期範圍給促銷活動或其他轉換[!UICONTROL 分類]，以便進行更精確的促銷活動測量。指定值的日期範圍後，發生在日期範圍以外的任何相符值都不會予以分類。如果想採用促銷活動的確實上線日期 (而非符合促銷活動的所有點擊) 來進行促銷活動測量，這個方法會很有用。為了成功分類某個日期範圍的值，必須符合下列條件：

* [!UICONTROL 分類]必須根據轉換變數。
* 使用的[!UICONTROL 分類]必須設定為「啟用日期」或「數值 2」。
* 相關的日期範圍必須包含開始日期和 (可選) 結束日期。

若要根據日期範圍來分類促銷活動：

>[!IMPORTANT]
>此選項不適用於已啟用「新分類架構」的報告套裝。

1. 登入 [!DNL Analytics] 並前往「管理員 > 分類」。
1. 按一下&#x200B;**[!UICONTROL 「瀏覽器匯出」]**&#x200B;標籤，確定啟用日期的分類設定正確，然後按一下「匯出檔案」。
1. 在 Microsoft Excel 或您熟悉的其他試算表編輯器中開啟檔案。
1. 其中一欄結尾會是

   ^~period~，需在此欄輸入日期範圍。
1. 在該欄下方，以下列格式輸入每個值的日期範圍：

   `YYYY/MM/DD - YYYY/MM/DD`。並確保：

   * 在破折號兩側留空格。
   * 使用連字號 (-) 來區隔範圍，而非短破折號或長破折號。
   * 如果月或天是一位數，需加上前置零。
   * 必須有開始日期範圍，但結束日期範圍為選用。

1. 儲存檔案並前往「管理員 | 分類 | 匯入檔案」，將其上傳至 [!DNL Analytics]。

>[!NOTE]
>
>一個具體的鍵值只能有一個日期範圍。

## 分類的疑難排解

* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)：說明因錯誤的檔案格式和檔案內容所引起問題的知識庫文章。
