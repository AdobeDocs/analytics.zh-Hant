---
description: 匯入工具可讓您大量上傳分類資料至檔案中的分析報告。 匯入需要特定檔案格式才能成功上傳資料。
title: 分類資料檔案
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
TQID: https://experienceleague.adobe.com/NKh-IIAZg2rqdpsJJrM765aXYvKGtpLjGWdwWhbiGTw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1045
ht-degree: 45%

---

# 分類資料檔案（舊版）

{{classification-importer-deprecation}}

匯入工具可讓您大量上傳分類資料至檔案中的分析報告。 匯入需要特定檔案格式才能成功上傳資料。

為協助您建立有效的資料檔案，您可以下載範本檔案，該檔案會提供可貼上分類資料的檔案結構。 有關詳細資訊，請參閱「[下載分類範本](/help/components/classifications/importer/c-download-saint-data.md)」。

請參閱「[一般檔案結構](/help/components/classifications/importer/c-saint-data-files.md)」，取得關於分類中字元限制的相關資訊。

## 一般檔案結構

以下是範例資料檔案的圖例：

![](assets/completed-saint-file.png)

資料檔案必須符合以下結構規則：

* 分類的值不得為0 （零）。
* Adobe 建議您將匯入和匯出上限設為 30 欄。
* 上傳的檔案應使用不含BOM字元編碼的UTF-8。
* 可以在儲存格中嵌入定位字元、新行字元和引號等特殊字元，前提是已指定 v2.1 檔案格式且儲存格已正確[逸出](/help/components/classifications/importer/importer-faq.md)。 特殊字元包括：

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  逗號不是特殊字元。

* 分類名稱不可包含脫字元號(^)，因為此字元是用來表示子分類。
* 使用連字型大小時請小心。 例如，您若是在 Social 詞語中使用連字號 (-)，Social 會將連字號辨識為 [!DNL Not] 運算元 (減號)。 例如，您若使用匯入項目指定 *`fragrance-free`* 為詞語，Social 會將詞語辨識為 fragrance *`minus`* free，並收集提及 *`fragrance`* 但不包含 *`free`* 的字。
* 系統會強制使用字元限制來分類報告資料。 例如，如果您上傳產品名稱超過 100 個字元 (位元組) 的產品分類文字檔 (*`s.products`*)，產品將不會顯示在報告中。 追蹤程式碼和所有自訂轉換變數 (eVar) 可以使用 255 個位元組。 此原則也會延伸至分類和子分類欄值，其受相同255位元組限制的約束。
* 以定位點分隔的資料檔案 (使用任何試算表應用程式或文字編輯器建立範本檔案)。
* 副檔名為 `.tab` 或 `.txt`。
* 井字型大小(#)會將該行識別為使用者註解。 Adobe會忽略任何以#開頭的行。
* 雙井號後面接著SC (`## SC`)會將該行識別為報告所使用的預處理標頭註解。 請勿刪除這些行。
* 由於索引鍵中有新行字元，分類匯出專案可能會有重複的索引鍵。 在FTP或瀏覽器匯出中，這可透過開啟FTP帳戶的報價來解決。 這會在每個鍵周圍加上引號，並使用換行字元。
* 匯入檔案第一行的儲存格C1包含版本識別碼，可決定分類如何處理檔案其餘部分引號的使用。

   * v2.0會忽略引號，並假設引號都是指定索引鍵和值的一部分。 例如這個值：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。 v2.0 會按字面含義將此解析為：&quot;這是&quot;&quot;一些值&quot;&quot;&quot;。
   * v2.1會告訴分類，假設引號是Excel檔案中所使用檔案格式的一部分。 因此，v2.1 會將上述範例設為下列格式：這是&quot;一些值&quot;。
   * 在檔案中指定v2.1時可能會發生問題，但實際需要的是v2.0 — 即引號的使用方式在Excel格式下不合法。 例如，如果檔案中有下列值：&quot;VP NO REPS&quot; S/l Dress w/ Overlay， 使用v2.1時，格式不正確（值應以開頭和結尾引號包圍，屬於實際值的引號應以引號逸出），在此之後，分類將無法運作。
   * 請務必執行下列任一作業：變更上傳檔案的標題 (C1 儲存格) 以將檔案格式變更為 v2.0，「或是」在檔案中正確置入 Excel 引號。

* 資料檔案的第一列（非註解）包含用來識別該欄中分類資料的欄標題。 匯入工具需要欄標題的特定格式。 有關詳細資訊，請參閱「[欄標題格式](/help/components/classifications/importer/c-saint-data-files.md)」。
* 資料檔案中標題列後面緊鄰資料列。 每一行資料應包含每個欄標題的資料欄位。
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
   <td colname="col1"> <p>&lt;換行&gt; </p> </td> 
   <td colname="col2"> <p>新的行字元是資料檔案中資料行/記錄之間唯一支援的分隔字元。 通常，在寫入程式以自動產生資料檔案時，您只需要特別插入這些字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>請求Adobe自動為此元素產生唯一ID。 </p> <p>在促銷活動內容中，此控制值會指示Adobe將識別碼指派給每個創意元素。 請參閱<a href="/help/components/classifications/importer/c-saint-data-files.md"  >索引鍵</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指定資料欄代表與專案相關聯的日期範圍。 請參閱<a href="/help/components/classifications/importer/c-saint-data-files.md"  >日期</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空白欄位 </p> </td> 
   <td colname="col2"> <p>代表目前欄位的NULL值。 如果特定資料欄未套用至目前的記錄，請使用此選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER修飾元 </p> </td> 
   <td colname="col2"> <p>指出資料欄代表 <span class="wintitle">PER 修飾詞</span>欄位。 請參閱 <a href="/help/components/classifications/importer/c-saint-data-files.md"  >PER 修飾詞標題</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 欄標題格式

>[!NOTE]
>
>Adobe 建議您將匯入和匯出上限設為 30 欄。

分類檔案支援下列欄標題：

### 金鑰

每個值在整個系統內必須是唯一的。 此欄位中的值與在網站之 [!DNL JavaScript] 指標中指定給 [!DNL Analytics] 變數的值對應。 此欄中的資料可以包含 ~autogen~ 或其他任何唯一的追蹤程式碼。

### 分類欄標題

>[!NOTE]
>
>[!UICONTROL 分類]欄標題中的值必須與分類的命名慣例完全相符，否則匯入會失敗。 例如，若管理員在「[!UICONTROL 促銷活動設定管理員]」中將「[!UICONTROL 促銷活動]」變更為[!UICONTROL 內部促銷活動名稱]，則檔案欄標題也必須一併變更。 「金鑰」是保留的分類 (標頭) 值。 不支援名為「金鑰」的新分類。

此外，資料檔案支援以下額外的標題慣例，以便識別子分類和其他專業的資料欄：

### 子分類標題

例如，`Campaigns^Owner`是包含`Campaign Owner`值之資料行的資料行標題。 同樣地，`Creative Elements^Size`是包含`Creative Elements`分類之`Size`子分類的資料行的資料行標題。

## 分類的疑難排解

* [常見的 上傳問題](https://helpx.adobe.com/tw/analytics/kb/common-saint-upload-issues.html)：說明因錯誤的檔案格式和檔案內容所引起問題的知識庫文章。
