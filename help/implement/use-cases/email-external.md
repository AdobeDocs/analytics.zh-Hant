---
title: 外部電子郵件追蹤
description: 使用 Adobe Analytics 追蹤電子郵件內容。
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 外部電子郵件追蹤

公司可使用 Analytics 來判斷電子郵件促銷活動是否成功。

[!DNL Analytics] 可用數種關鍵度量來報告電子郵件促銷活動分析資料，其中包括：

| 量度 | 說明 |
|---|---|
| 點進次數 | 顯示從電子郵件追蹤到登陸頁面的點進次數。 |
| 購買和 (或) 成功 | 顯示因電子郵件而產生的購買數。 |
| 訂購 | 顯示因電子郵件而產生的訂購數。 |
| 產生 | 顯示電子郵件吸引的每次瀏覽所產生的金額。 |
| 轉換 | 顯示因電子郵件而產生的潛在客戶、註冊或任何其他成功事件的數目。 |

必須對 HTML 電子郵件內文和 JavaScript 程式庫進行修改，才能擷取前述的關鍵度量。

## 實施 {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

要順利顯示電子郵件促銷活動分析資料，必須執行數個步驟。這些步驟說明如下：

1. 建立唯一的追蹤代碼。

   使用者常會要求我們提供關於每個特定促銷活動的追蹤建議。這完全取決於使用者，端視何者效果最佳而定。每個使用者都是不同的。Adobe 建議每位使用者建立好記的追蹤代碼，如下列範例所示：

   * sc_cid=A1123A321 > &quot;A&quot; 會標記附屬機構促銷活動
   * sc_cid=EM033007 > &quot;EM&quot; 會標記電子郵件促銷活動
   * sc_cid=GG987123 > &quot;GG&quot; 表示 Google，屬於付費搜尋促銷活動
   如需設定及使用追蹤代碼的詳細資訊，請與 Adobe [!DNL Customer Care] 連絡。

1. 新增查詢字串參數至 HTML 電子郵件連結。

   若要追蹤使用者點進次數和後續的成功事件，必須將查詢字串參數新增至 HTML 電子郵件內的每個連結。您可以選擇個別追蹤每個連結，或一併追蹤所有連結。每個連結可以有一個唯一的追蹤代碼，或是讓所有連結共用相同的追蹤代碼。請考量下列在電子郵件內連至網站的假設性連結：

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   下列查詢字串參數 ?sc_cid=112233B 應新增至上述連結：

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. 更新 JavaScript 程式庫。

   更改 JavaScript 檔案 [!DNL s_code.js] 中的程式碼，可讓您擷取關於有多少使用者 (以及哪些使用者) 從電子郵件點進並參與後續成功事件的資訊。更新 JavaScript 程式庫時須執行兩個步驟。

   1. 呼叫 [!DNL s_code.js]getQueryParam[!UICONTROL  以自訂 ]。

      [!DNL s_code.js] 檔案應放置在 Web 伺服器上可供每個網頁存取之處。*`doPlugins`* 函數應進行更改，以便擷取電子郵件連結上的查詢字串參數。例如：

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      每個必須複製到變數中的查詢字串參數，都應有一個 [!UICONTROL getQueryParam] 呼叫。在上述範例中，查詢字串參數 [!UICONTROL sc_cid] 已複製到    *`campaign`*。

      在擷取點進次數時，只需要第一次的 [!UICONTROL getQueryParam] 呼叫。請連絡 Adobe [!DNL Customer Care] 以實施此函數，並確認您的 JavaScript 檔案版本包含 [!UICONTROL getQueryParam] 外掛程式。

   1. 確定「貼上程式碼」JavaScript 標記位於所有的登陸頁面上。此「貼上程式碼」必須參考在「A 部分」中更改的 [!DNL s_code.js] 版本。

      以下提供在更新 JavaScript 程式庫時務必留意的幾項要點。這些要點列出如下。

      * 查詢字串參數 [!UICONTROL sc_cid] 在最終登陸頁面上的 URL 中必須是可見的，否則將不會記錄任何點進次數轉換。
      * [!UICONTROL sc_cid] 參數是查詢字串參數的範例之一。任何查詢字串參數皆可由 [!UICONTROL getQueryParam] 外掛程式使用及擷取。請確定查詢字串參數僅用於促銷活動追蹤。只要這些參數出現在查詢字串中，其值就會複製到    *`campaign`*。

1. 使用 [!UICONTROL SAINT] 為促銷活動追蹤代碼進行分類。

   [!UICONTROL 「SAINT 促銷活動管理工具」]可用來將追蹤代碼轉換為好記的名稱。它也可用來摘要每個電子郵件促銷活動的成就。下方的步驟 5 中列出了設定電子郵件促銷活動時所須執行的程序。

1. 參閱電子郵件促銷活動的路徑分析 (選用)。

   電子郵件促銷活動的路徑分析在執行時可比照其他促銷活動的路徑分析。您可以使用變數來顯示促銷活動的路徑分析，如下列步驟所說明：

   1. 請向 Adobe [!DNL Customer Care] 洽詢為[!UICONTROL 「自訂分析」]變數 (prop) 開啟路徑分析的相關事宜。

   1. 在所有頁面上，將頁面名稱複製到指定的 [!DNL s.prop] 中。
   1. 在電子郵件登陸頁面上，將電子郵件促銷活動的名稱附加到 prop。結果顯示如下：

      ```js
      s.prop1="Home Page : 123456"
      ```

      為[!UICONTROL 「自訂分析」]變數啟用路徑分析時，您可以使用[!UICONTROL 「路徑」]報表 (例如[!UICONTROL 「下一頁面流量」]或[!UICONTROL 「流失」]) 來檢視訪客從登陸頁面所做的瀏覽。

