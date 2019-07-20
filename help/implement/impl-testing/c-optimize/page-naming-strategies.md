---
description: pageName 變數中應填入直觀易懂的頁面識別碼。
keywords: Analytics 實施
seo-description: pageName 變數中應填入直觀易懂的頁面識別碼。
seo-title: 頁面命名策略
solution: Analytics
title: 頁面命名策略
topic: 開發人員和實施
uuid: a829d0c7-6ef-459a-b403-5e9 c05161 e5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 頁面命名策略

pageName 變數中應填入直觀易懂的頁面識別碼。

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

*`pageName`* 變數是識別使用者行為的核心，但Adobe建議使用多個變數來指出頁面資訊。最理想的頁面命名策略，是為您網站內的每個階層層級使用不同的變數，如下所示: 

* 此&#x200B;*`channel`* 變數可用來指出網站區段。
* *`pageName`* 變數可用來顯示內容類型。
* [!UICONTROL 自訂分析]變數 (prop1) 可用於詳細內容。

詳細程度會隨屬性而不同，如下所示: 

| 變數 | 詳細程度 | 範例 |
|---|---|---|
| Channel | 一般區域 | 電子裝置 |
| Prop1 | 子區域 | 運動: 當地運動 |
| PageName | 一般內容說明 | 貸款: 房屋貸款: 利率比較 |
| Prop2 | 詳細的內容說明 | 電子裝置: 筆記型電腦: 詳細規格: IBM Thinkpad T20 |

網站的分層越多，用於識別頁面內容的變數也應越多。公司也會發現變數之間可重疊有其效用。例如，一個較詳細的變數不僅可包含所檢視之產品的相關資訊，也可包含網站區段與子區段的相關資訊。當某產品或文章出現在網站上的多個區域時，此作法尤可奏效。

下列頁面命名策略將說明如何填入&#x200B;*`pageName`* 變數。雖然使用者傾向於選擇最容易實施的頁面命名策略，但頁面命名策略在相當大的程度上決定了所有[!UICONTROL 「路徑」]及[!UICONTROL 「頁面」]報表的可用性。在決定頁面的命名方式時，應審慎判斷。

## 每個頁面的唯一名稱 {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

最有效的頁面命名方法，是為每個頁面指定一個讓您的組織內所有的 [!DNL Analytics] 使用者都容易理解的唯一識別碼。舉例來說，頁面名稱可以是「首頁」、「電子部門首頁」、「運動: 地方運動: 高中」。

[!DNL Analytics] 使用者大多會發現，階層頁面名稱對於識別頁面在網站上的位置及其目的都很有幫助。下表顯示不同產業的一些範例頁面名稱: 

| 轉換 | 媒體 | 金融 |
|---|---|---|
| 首頁 | 首頁 | 首頁 |
| 電子裝置 | 技術 | 房屋貸款 |
| 電子裝置: 筆記型電腦 | 技術: 新型小工具 | 房屋貸款: 利率比較 |
| 電子裝置: 筆記型電腦: 產品頁面 | 技術: 新型小工具: 文章頁面 | 房屋貸款: 利率比較: 10 年期固定 |

## 檔案路徑 (不是「完整的 URL」) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

某些網站的檔案路徑清晰易讀。任何商業使用者皆可讀取 URL，並確定檔案路徑所參照的頁面。若您的網站是這樣，您可以使用伺服器端變數，將檔案路徑填入&#x200B;*`pageName`* 變數中，如下所示: 

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* 網域和頁面路徑並不始終顯示為相同。例如，下列四個 URL 會傳回同一個頁面: 

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* 有些頁面 (例如表單) 是自身發佈的，由此消除了原始表單和輸出結果之間的區別。
* 當您的頁面被搜尋引擎或其他線上工具轉譯成另一種語言時，頁面的 URL 會是搜尋引擎的 URL (而不是您的網站的 URL)。

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. 有些瀏覽器會以不同的方式解譯 HTML 標題，而可能導致 [!DNL Analytics] 從不同的瀏覽器接收到不同的頁面名稱。

使用 HTML 標題的最好做法是將各頁面的現有標題複製到一個單獨的變數或內容管理元素中。當您決定為達到搜尋引擎最佳化或其他目的而變更 HTML 標題時，[!DNL Analytics] 的頁面名稱不會受到影響。若一個頁面名稱在 [!DNL Analytics] 內發生改變，它將會變成一個新的頁面，且不再與舊的頁面名稱連結，無論相關聯的 URL 為何。
