---
description: 匯入工具可讓您大量上傳分類資料至檔案中的分析報告。匯入功能須有特定的檔案格式才能成功上傳資料。
title: 分類資料檔案
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 90%

---

# 分類資料檔案（舊版）

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
* 可以在儲存格中嵌入定位字元、新行字元和引號等特殊字元，前提是已指定 v2.1 檔案格式且儲存格已正確[逸出](/help/components/classifications/importer/importer-faq.md)。特殊字元包括：

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  逗號不是特殊字元。

* 分類名稱不可包含脫字元號(^)，因為此字元是用來表示子分類。
* 請謹慎使用連字號。例如，您若是在 Social 詞語中使用連字號 (-)，Social 會將連字號辨識為 [!DNL Not] 運算元 (減號)。例如，您若使用匯入項目指定 *`fragrance-free`* 為詞語，Social 會將詞語辨識為 fragrance *`minus`* free，並收集提及 *`fragrance`* 但不包含 *`free`* 的字。
* 系統會強制使用字元限制來分類報告資料。例如，如果您上傳產品名稱超過 100 個字元 (位元組) 的產品分類文字檔 (*`s.products`*)，產品將不會顯示在報告中。追蹤程式碼和所有自訂轉換變數 (eVar) 可以使用 255 個位元組。此原則也會延伸至分類和子分類欄值，其受相同255位元組限制的約束。
* 以定位點分隔的資料檔案 (使用任何試算表應用程式或文字編輯器建立範本檔案)。
* 副檔名為 `.tab` 或 `.txt`。
* 井字號 (#) 能將文字行識別為使用者註解。Adobe 會略過任何開頭為 # 的文字行。
* 雙井號後面接著SC (`## SC`)會將該行識別為報告所使用的預處理標頭註解。 請勿刪除這些文字行。
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

例如，`Campaigns^Owner`是包含`Campaign Owner`值之資料行的資料行標題。 同樣地，`Creative Elements^Size`是包含`Creative Elements`分類之`Size`子分類的資料行的資料行標題。

## 分類的疑難排解

* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)：說明因錯誤的檔案格式和檔案內容所引起問題的知識庫文章。
