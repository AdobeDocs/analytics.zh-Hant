---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# eVarN

[!UICONTROL eVar] 變數可用來建置自訂報表。


<!-- 

eVarN.xml

 -->

當 eVar 設為某個訪客的值時，系統會記住該值，直到其過期為止。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | v1-v75 ([或是 v100 或 v250](/help/implement/js-implementation/page-variables/page-variables.md)) | 自訂轉換 | "" |

**過期**

`eVars` 在您指定的時段後過期。 eVar 過期後，即不會再獲得成功事件的評價。您也可以將 eVar 設定成隨著成功事件過期。例如，若您有某個內部促銷會在瀏覽結束時過期，此內部促銷將只會因為在購買或註冊啟動的瀏覽期間所發生的購買或註冊，而獲得評價。

有兩種方式可讓 eVar 過期: 

* 您可以將 eVar 設定成在指定的時段或事件之後過期。
* 您可以強制使 eVar 過期，這在重設變數用途時很適用。

若某個 eVar 在五月用來反映內部促銷情形，並在 21 天後過期，而在六月則用來擷取內部搜尋關鍵字，則您應在 6 月 1 日將此變數強制過期，或重設此變數。這麼做有助於將內部促銷值排除在六月的報表以外。

**區分大小寫**

eVar 不區分大小寫，但會以第一次出現時的大寫格式顯示。例如，若 eVar1 的第一個例項設為 "Logged In"，但後續所有的例項皆以 "logged in" 的格式傳入，則報表一律會將 eVar 的值顯示為 "Logged In"。

**計數器**

eVar 通常會用來放置字串值，但也可設定作為計數器。當您嘗試計算使用者在某個事件之前所執行的動作數時，即可將 eVar 當作計數器使用。例如，您可以使用 eVar 擷取購買之前的內部搜尋次數。每次訪客搜尋時，eVar 中都應會有 '+1' 值。若訪客在購買之前做了四次搜尋，您將會看見各個總計數的例項: 1.00、2.00、3.00、4.00。但只有 4.00 會獲得購買事件的評價 (訂購和收入度量)。eVar 計數器的值必須是正數。

**子關聯**

「自訂 eVar」報表的一般需求之一，是必須能夠以一個「自訂 eVar」報表劃分另一個。例如，若一個 eVar 包含性別，另一個包含薪資，您可以問下列問題: 就網站上的女性訪客而言，有多少收入來自於年收入達 50,000 美元以上的女性。任何具有完整子關聯的 eVar，都可在報表中用於此類型的劃分。例如，若性別 eVar 已啟用完整子關聯，則所有其他自訂 eVar 報表都將能以性別來劃分，而性別也能以所有其他 eVar 來劃分。若要檢視兩份報表之間的關聯，只要有其中一份報表啟用完整子關聯即可。依預設，促銷活動、產品和類別報表是完全子關聯的（任何eVar都可依促銷活動或產品劃分）。

**語法和可能的值**

雖然 eVar 可重新命名，但在 JavaScript 檔案中應一律以 eVarX 加以參照，其中，X 是介於 1 與 75 之間 ([或是 100 或 250](/help/implement/js-implementation/page-variables/page-variables.md)) 的數字。

```js
s.eVarX="value"
```

eVar 在未作為計數器時，會受到與所有其他變數相同的限制。若 eVar 為「計數器」，則預期應會接收 "1" 或 "2.5" 之類的數值。若指定了兩個以上的小數位數，eVar 計數器會進位至兩個小數位數。eVar 計數器不可包含負數。

**範例**

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**組態設定**

eVar可在「分析&gt;管理&gt;報表套裝&gt;編輯設定&gt;轉換&gt;轉換變數」中設定。 所有 eVar 都能以「名稱」、「類型」、「配置」、「在設定之後過期」或「重設」來設定。每項組態設定會分開處理。

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 設定 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 名稱 </td> 
   <td> 可讓您變更 <span class="keyword">Analytics</span> 中的 eVar 報表名稱。 <p>無論在 <span class="keyword">Analytics</span> 中為報表指定什麼名稱，eVar 在 JavaScript 程式碼中仍會參照為 s.eVarX。 </p> </td> 
  </tr> 
  <tr> 
   <td> 類型 </td> 
   <td> 可讓您說明 eVar 是文字字串還是計數器。 </td> 
  </tr> 
  <tr> 
   <td> 配置 </td> 
   <td> 用以設定哪個 eVar 值會獲得成功事件的評價。 <p>若「配置」設為「最近 (最後一個)」，則 B 會獲得評價。 </p> <p>若「配置」設為「原始值 (第一個)」，則 A 會獲得評價。 </p> <p>若「配置」設為「線性」，則 A 和 B 會各獲得購買值一半的評價。 </p> </td> 
  </tr> 
  <tr> 
   <td> 過期時間 </td> 
   <td> 可讓您決定 eVar 會在特定事件 (如購買) 發生時過期，還是在自訂或預先定義的時段之後過期。 </td> 
  </tr> 
  <tr> 
   <td> 重設 </td> 
   <td> 為 eVar 選取<span class="wintitle">「重設」</span>核取方塊，然後按一下位於頁面底部的<span class="wintitle">「儲存」</span>，該 eVar 所有的值都會隨即過期。在此之後，將只有 eVar 的新值會獲得成功事件的評價。 </td> 
  </tr> 
 </tbody> 
</table>

**缺陷、問題和提示**

* 不同於 [!UICONTROL prop] 變數，eVar 變數不可以是分隔值清單。若您為 eVar 填入值清單 (例如 "one,two,three")，這個字串將會照原樣出現在報表中。
* eVar 計數器不可包含負數。
