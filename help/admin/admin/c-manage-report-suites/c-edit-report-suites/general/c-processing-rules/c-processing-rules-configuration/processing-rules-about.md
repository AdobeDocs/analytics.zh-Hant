---
description: 處理規則可讓您根據已定義條件來對資料進行變更。當屬性或值符合定義條件時，可以設定或刪除值，以及設定事件。
subtopic: Processing rules
title: 處理規則的運作方式
feature: Processing Rules
role: Admin
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 94%

---

# 處理規則的運作方式

處理規則可讓您根據已定義條件來對資料進行變更。當屬性或值符合定義條件時，可以設定或刪除值，以及設定事件。

處理規則會在收集資料時套用至資料上，規則則會套用至透過 AppMeasurement 庫和「資料插入 API」而來的所有資料。處理規則也適用於完整和記錄檔資料來源。這些來源包含代表&#x200B;*`hit`*&#x200B;或使用者採取動作的資料。 處理規則不適用於其他資料來源。

## 重要概念 {#section_EB138775E7C64C74B0D1D3213F7A823C}

下表包含您在使用處理規則時務必瞭解的重要概念：

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>概念 </p> </th> 
   <th colname="col2" class="entry"> <p>詳細資料 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>規則套用至單一報表套裝。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> 複製處理規則至其他報表套裝 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>處理規則依列出順序而套用。 </p> </td> 
   <td colname="col2"> <p>如果有個動作變更了值，後續條件會使用新值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>系統儲存處理規則後，會將它們立即套用至報表套裝。 </p> </td> 
   <td colname="col2"> <p>若變更處理規則，儲存後數分鐘內應會顯示於報表套裝中。測試處理規則時，建議您在測試報表套裝中設定<a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md">個即時報表</a>，以便快速檢視處理規則的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>處理規則是存取內容資料變數的唯一方法。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md">複製內容資料變數至 eVar</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>處理規則的套用時機早於 VISTA 規則和行銷渠道規則。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> 處理順序 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不能排除點擊。 </p> </td> 
   <td colname="col2"> <p>您可使用 VISTA 規則來排除點擊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不能變更產品字串、反向連結和使用者代理。 </p> </td> 
   <td colname="col2"> <p>反向連結和使用者代理為唯讀。產品字串則不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置屬性和分類不可用。 </p> </td> 
   <td colname="col2"> <p>行動裝置查閱的發生時機早於處理規則，但屬性不可用於處理規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果是執行 JavaScript AppMeasurement H.25.2 或更早的版本，無法讀取超過 URL 前 255 個字元的查詢字串參數。JavaScript AppMeasurement H.25.3 和更新版本提供完整的 URL，包含處理規則的所有查詢字串參數。 </p> </td> 
   <td colname="col2"> <p>升級到 H.25.3 或更新的版本，或者從長 URL 用戶端讀取查詢字串參數，並將它的值儲存在內容資料變數裡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查詢字串值必須編碼為 Unicode 或 UTF-8，處理規則才能讀取。 </p> </td> 
   <td colname="col2"> <p>這可能會影響使用查詢字串傳遞的多位元組字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每個報表套裝最多只能使用 150 個規則，每個含 30 個條件。 </p> </td> 
   <td colname="col2"> <p>處理規則限制是依報表套裝而定，而非依公司而定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>必須先設定處理規則來擷取內容資料變數，之後才能傳送資料。 </p> </td> 
   <td colname="col2"> <p>當傳送伺服器呼叫時，就會套用處理規則。若未使用處理規則複製內容資料變數中儲存的值，這些值就會被捨棄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UI 中的值比較不區分大小寫。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> 清除報表中的值 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>內容資料變數名稱只能包含英數字元、底線和點。其他任何字元都會刪除。 </p> </td> 
   <td colname="col2"> <p>例如，內容資料變數 <code> login_page-home</code> 會自動變成 <code> login_pagehome</code>。所有傳送至 <code> login_page-home</code> 變數的資料，都會分配到 <code> login_pagehome</code> 下。 </p> <p>包含不支援之字元的內容資料變數無法在「處理規則」介面中新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>脫字符號 (^) 是處理規則系統中的特殊字元。 </p> </td> 
   <td colname="col2"> <p>若要表示單一脫字符號字元，請使用兩個脫字符號字元 (^^)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 處理規則條件 {#section_387390EEE9BA4DA98698522A84326DB4}

條件會檢查頁面變數是否有符合值或值是否存在。可以加入多個條件，您也可以選取是否須符合所有條件。

您可以建立無條件的規則，以一律執行已定義動作。

在發生動作前，並不會自動檢查變數的值。例如，Prop1 包含 &quot;something&quot; 值，而 eVar1 空白。如果您設定 Prop1 等於 eVar1，則兩個值都會變成空白。如果您想避免這種情形，請加入一個條件來檢查是否存在值。

## 處理規則動作 {#section_E2285C9D008442C7BF136E52A9A4CC06}

動作可以設定頁面變數、刪除頁面變數或觸發事件。動作也能串連值以顯示在報告中

例如，您可以串連兩個值，以顯示 `category:product`。
