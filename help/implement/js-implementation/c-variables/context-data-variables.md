---
description: 「上下文資料」變數可讓您定義每個頁面上可由「處理規則」讀取的自訂變數。
keywords: Analytics Implementation;contextdata;s.contextdata
subtopic: Variables
title: 上下文資料變數
topic: Developer and implementation
uuid: 4b215803-99d4-46f2-b3c1-e78558987764
translation-type: tm+mt
source-git-commit: 5d69587886c87bc62ad744c51d56bb6cd9e53167

---


# 上下文資料變數

「上下文資料」變數可讓您定義每個頁面上可由「處理規則」讀取的自訂變數。

您無須在程式碼中明確為 prop 和 eVar 指派值，而可以在以「處理規則」進行對映的上下文資料變數中傳送資料。處理規則提供功能強大的圖形介面，可以在收到資料時變更資料。您可以根據上下文資料中傳送的來設定事件、將值複製到 eVar 與 prop，以及執行其他條件陳述式。

> [!NOTE]內容資料變數不區分大小寫。例如，下列 2 個變數效力相同:
>
```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>與
>
```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```

使用上下文資料不需要更新程式碼，就能支援不同的報表套裝設定。

例如，您可以定義下列  *`s.contextData`* 變數:

```
s.contextData['myco.rsid'] = 'value'
```

您可使用處理規則來新增條件，檢查是否有 `myco.rsid` 上下文資料變數。找到此變數時，則可新增動作，將其複製至 prop 或 eVar。

您也可以在處理規則介面中直接定義上下文資料變數，以暫時儲存值，或收集您已知後續將用於報表套裝的上下文資料變數值。例如，如果您需要交換兩個值，則可建立一個上下文資料變數，在交換期間用於儲存值。

由於處理規則只在蒐集資料時會套用，因此在開始傳送上下文資料前，請務必先設定好處理規則。處理點擊時，未由處理規則讀取的上下文資料值都會被捨棄。

## 規則 {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>規則 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>支援的名稱和字元 </p> </td> 
   <td colname="col2"> <p>上下文資料變數的名稱只能包含英數字元、底線和點。其他任何字元都會被移除。上下文資料變數並未以數值指定，而是採用命名的方式。 </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. 所有傳送至 <code> login_page-home </code> 變數的資料，都會分配到 <code> login_pagehome </code> 下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>命名空間 </p> </td> 
   <td colname="col2"> <p>建議做法是在變數前面加上公司名稱、網站名稱或類似的值，以確保該名稱在整個報表套裝中都是唯一的。 </p> <p>上下文資料變數的命名方式可與其他 JavaScript 變數相同。Be aware that the namespace <code> a.* </code> is reserved for use by Adobe products in context variable names. iOS 適用的 AppMeasurement 程式庫會使用 <code> a.InstallEvent </code> 來評估應用程式安裝。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Internet Explorer 的 URL 限制 </p> </td> 
   <td colname="col2"> <p>您可能會遇到 Internet Explorer 6 和 7 的舊版 URL 限制，也就是 URL 會在 2000 位元組處被截斷。您可以使用 <span class="keyword">DigitalPulse</span> 除錯程式來判斷 URL 字串的大小。 </p> <p>對 AppMeasurement 進行的最新更新 (2014 年 9 月) 中，Internet Explorer 8 以上採用 HTTP POST，排除了截斷的問題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>支援的 AppMeasurement 版本 </p> </td> 
   <td colname="col2"> <p>上下文資料變數至少需要 H23 程式碼或更高版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 在追蹤連結呼叫上傳送上下文資料 {#section_35EBE5D1CF29427598BD4B2165CE64FC}

加入 `ContextData` + 您要加入至 `s.linkTrackVars` 的變數名稱:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## 範例 {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

取代 *`s.pageName`* 變數實施的可能方式，假設處理規則已逐一正確設定:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

實施上下文資料變數的其他範例: 

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

如需範例，請參閱「Analytics 參考」中的[複製上下文資料變數至 eVar](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html)。
