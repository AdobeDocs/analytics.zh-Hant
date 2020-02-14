---
title: 行銷渠道的處理規則
description: 行銷渠道處理規則確定了訪客點按是否符合要指定給渠道的標準。規則會處理訪客在您網站的每次點按。當規則不符合渠道標準，或如果未正確設定規則，系統會將點按指派給「未識別渠道」。
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# 行銷渠道的處理規則

行銷渠道處理規則確定了訪客點按是否符合要指定給渠道的標準。規則會處理訪客在您網站的每次點按。當規則不符合渠道標準，或如果未正確設定規則，系統會將點按指派給「未識別渠道」。

以下是建立規則的重要指引: 

* 依據所需的處理順序來排序規則。
* 在清單結尾，加入一個包羅廣泛的規則，例如「其他」。此規則可識別外部流量，但不識別內部流量。

   請參閱[未識別管道](/help/components/c-marketing-channels/c-faq.md)。

> [!NOTE] 雖然這些規則不影響行銷管道外部的報表，但會影響行銷管道資料收集。使用這些規則收集的資料一律是永久性的，而在收集資料後更改的規則無法溯及以往。It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## 必備條件

* 檢視行銷管道快 [速入門的概念資訊](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* 建立一個或多個渠道，以便為它們指定規則。See [Add marketing channels.](/help/components/c-marketing-channels/c-channels.md)

## 建立行銷管道處理規則

建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。

此程序使用電子郵件規則做為範例。此範例假設您已新增電子郵件渠道至「行銷渠道管理員」頁面上的渠道清單中。

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 選取報表套裝。

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![步驟結果](assets/marketing_channel_rules.png)

1. 從菜單 **[!UICONTROL Add New Rule Set]** 中，選擇 **[!UICONTROL Email]**。

   您在此處並非選擇渠道，而是選擇範本並以數個必要參數填入規則。

   ![步驟結果](assets/example_email.png)

   使用布林邏輯 (if/then 陳述式) 來設定規則。例如，在電子郵件渠道規則中，您提供下列規則陳述式中強調的設定或資訊: 

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   在此範例中，*`<value>`* 是用於電子郵件促銷活動的查詢字串參數，例如 *`eml`*
1. 若要繼續建立規則，請按一下 **[!UICONTROL Add Rule]**。
1. 若要排列規則優先順序，請將它們拖放至適當位置。
1. 按一下 **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [常問問題和範例](/help/components/c-marketing-channels/c-faq.md)


## 行銷渠道規則條件

此參考表格定義您可以在「行銷渠道處理規則」頁面上選取的欄位、選項和點按屬性。

| 術語 | 定義 |
|--- |--- |
| 全部 | 僅當編號規則中的全部規則均為 true 時，啟用該渠道。 |
| 任何 | 當規則集中的任何規則為 true 時，啟用該渠道。該選項僅當編號規則中存在多個規則時方可用。 |
| AMO ID | Advertising Cloud 與 Advertising Analytics 整合所使用的主要追蹤程式碼。當其中一項整合啟用時，追蹤程式碼首碼可用來識別 Advertising Cloud 專用的管道。「AMO ID」的開頭使用「AL」代表 Search，「AC」代表 Display，「AO」則代表 Social。行銷管道中使用 AMO ID 時，點按/成本/曝光量度可歸因為正確的管道 (若未設定，這些量度將變為「直接」或「無」)。 |
| AMO ED ID | Advertising Cloud 使用的次要追蹤程式碼。此追蹤程式碼的主要用途是作為將資料傳回 Ad Cloud 的金鑰。不過，如果您想要將 ClickThroughs 和 ViewThroughs 視為兩個不同的行銷管道，也可以用它來識別 Display ClickThroughs 與 Display ViewThroughs。方法是為以「:d」結尾 (代表 Display ClickThroughs) 或結尾為「:i」(代表 Display ViewThroughs) 的「AMO EF ID」設定行銷管道邏輯。如果您不想將 Display 分割為兩個管道，請改用 AMO ID 維度。 |
| 轉換變數 | 包含為該報表套裝啟用的 eVar，並僅當透過頁面上的 Adobe 代碼設定這些變數時套用。請參閱  實施指南。 |
| 存在 | 具備多個可用選擇，包括:<ul><li>**不存在**: 指定請求上並不存在點按屬性。例如，在反向連結網域中，如果使用者輸入 URL 或按一下書籤，反向連結網域屬性並不存在。</li><li>**為空**: 指定點按屬性存在，通常為 eVar 或查詢字串參數，但沒有與點按屬性相關的值。</li><li>**不包含**: 例如，讓您指定某反向連結網域不包含特定數值 (與選項「 &quot;包含&quot;.)</li></ul> |
| 將該渠道識別為 | 將規則與新增至行銷渠道管理員頁面的行銷渠道相關聯。請參閱新增行銷管道。 |
| 匹配付費搜尋的偵測規則 | Adobe 偵測的付費搜尋。付費搜尋是指公司付款以將其網站列入搜尋引擎。付費搜尋通常顯示在搜尋結果的頂部或右側。 |
| 匹配免費搜尋的偵測規則 | Adobe 報表偵測的免費搜尋。 |
| 反向連結匹配內部 URL 篩選器 | 瀏覽的頁面 URL 與內部 URL 篩選器匹配，該內部 URL 篩選器是為「管理工具」的報表套裝而定義的。 |
| 反向連結不匹配內部 URL 篩選器 | 反向連結 URL 與一個內部 URL 篩選器不相符，並且這是為「管理工具」的報表套裝而定義的。此設定可搭配使用頁面 URL  和存在來設定範圍廣泛的規則，如此一來就不會有任何造訪落在報表的未識別管道區段中。 |
| 忽略符合內部 URL 篩選條件的點按 | (適用於反向連結) 僅跟蹤來自外部反向連結網站的點按。通常，除非您想要包含內部流量，否則此設定保留啟用。 |
| 是第一個瀏覽的頁面 | 由 Adobe 報表偵測到的瀏覽首頁。 |
| 頁面 | 您網站上使用 Adobe 網站信標所標記的網頁之頁面名稱。此值等同於  s.pageName 。例如 `Home Page` 和 `About Us`。 |
| 頁面網域 | 訪客著陸的頁面網域，例如 `products.example.co.uk`。 |
| 頁面網域和路徑 | The domain and path, such as `products.example.co.uk/mens/pants/overview.html` . |
| 頁面根網域 (TLD+1) | 訪客著陸的頁面根網域，例如 example.co.uk。 |
| 頁面 URL | 您網站某個網頁的 URL。 |
| 反向連結網域 | 訪客在瀏覽您的網站前所處的網域，例如，源自 `abcsite.com` 與 `xyzsite.com` 的反向連結。 |
| 查詢字串參數 | If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then page and cat are both query string parameters. (如需此工具的其他相關資訊，請參閱 `https://en.wikipedia.org/wiki/Query_string`.)  您可為每個規則集僅指定一個查詢字串參數。To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. |
| 反向連結 | 訪客在來到您網站之前所處的網頁位置 (完整 URL)。反向連結存在於您所定義網域之外。 |
| 反向連結網域和路徑 | 反向連結網域和 URL 路徑的串連例如:     `www.example.com/products/id/12345` 或 `ad.example.com/foo` |
| 反向連結參數 | 反向連結 URL 上的查詢字串參數。例如，如果訪客來自 `example.com/?page=12345&cat=1`，則 page 和 cat 為反向連結參數。 |
| 反向連結根網域 | 反向連結的根網域。反向連結存在於您所定義網域之外。 |
| 搜尋引擎 | 類似 Google 或 Yahoo! 將訪客帶至您網站的搜尋引擎。 |
| 搜尋關鍵字 | 使用搜尋引擎來執行搜尋的一個詞。 |
| 搜尋引擎 + 關鍵字 | 搜尋關鍵字和搜尋引擎的串連，以唯一識別搜尋引擎。例如，如果搜尋 computer，則搜尋引擎和關鍵字的識別如下所示: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**注意:**n = 免費; p = 付費 |
| 設定該渠道的值為 | 除了瞭解為您網站帶來訪客的行銷管道之外，您還能知道管道內的哪些橫幅廣告、搜尋關鍵字或電子郵件促銷活動為訪客的網站活動獲得評分。該 ID 是與渠道一同儲存的渠道值。該值通常為內嵌於著陸頁面或反向連結 URL 中的促銷活動 ID，有時也是搜尋引擎和搜尋關鍵字組合，或是最近識別特定渠道中訪客的反向連結 URL。 |

## 內部 (工作階段重新整理) 管道

內部管道 (經常重新命名為「工作階段重新整理」) 由網站的造訪組成，該網站的反向連結 URL 與 Admin Console 中的「內部 URL 篩選器」設定相符，亦即訪客的造訪來自該網站。

![](assets/int-channel1.png)

### 覆寫最佳實務

建議取消勾選直接和內部管道的覆寫上次接觸選項，如此這些管道就不會從其他持續沿用的上次接觸管道取走評分 (或互相取走評分)。

>[!NOTE]本文件假設直接和工作階段重新整理管道皆已取消勾選覆寫設定。

![](assets/int-channel2.png)

### 參與期間

訪客的首次和上次接觸管道在該瀏覽器上閒置 30 天後，都會經過重設。

>[!NOTE] 30 天為預設值，如有需要，可透過管理員設定加以修改。

如果訪客經常使用該網站，則參與回溯期會計入這些管道。管道必須閒置達 30 天，該期間才會過期，且管道才會重設。範例:

* 第 1 天: 使用者因顯示而造訪網站。系統會將首次和上次接觸管道設為顯示。

* 第 2 天: 使用者因免費搜尋而造訪網站。首次接觸仍會維持為顯示，而上次接觸則設為免費搜尋。

* 第 35 天: 使用者未造訪網站達 33 天，而且使用在瀏覽器中開啟的分頁返回。在具有 30 天參與回溯期的前提下，該回溯期將已關閉，且行銷管道 Cookie 將會過期。系統會重設首次接觸和上次接觸管道，且由於使用者來自內部 URL，因而會設為工作階段重新整理。

### 首次和上次接觸的關係

若要瞭解首次接觸與上次接觸之間的互動關係，並確認覆寫功能正常運作，您可以提取與上次接觸管道報表具有子關聯的首次接觸管道報表，當中含有您新增的關鍵成功量度 (請參閱以下範例)。此範例說明了首次和上次接觸管道之間的互動關係。

![](assets/int-channel3.png)

首次接觸與上次接觸彼此相等的交集之處以橘色顯示。「直接」和「工作階段重新整理」必須同時也是首次接觸管道，才能取得上次接觸管道的評分，因為它們無法從其他持續沿用的管道 (以灰色顯示的列) 取得的評分。

### 為什麼會發生工作階段重新整理?

我們已知上次接觸管道的「工作階段重新整理」只會在同時也是首次接觸管道時發生，而下列案例則說明「工作階段重新整理」在何種情況下會成為首次接觸管道。

**案例 1: 工作階段逾時**

訪客造訪網站後，將分頁維持在瀏覽器中開啟，以便日後使用。訪客的參與期間過期 (或自行刪除 Cookie)，且使用開啟的分頁再次造訪網站。由於反向連結 URL 是內部網域，該次造訪會分類為「工作階段重新整理」。

**案例 2: 並非所有網頁都經過標記**

訪客登陸未經標記的頁面 A，接著移至已標記的頁面 B。系統會將頁面 A 視為內部反向連結，而該次造訪會分類為「工作階段重新整理」。

**案例 3: 重新導向**

如果重新導向未經妥善設定，以致無法將反向連結資料傳遞至新的登陸頁面，則真實的登入反向連結資料就會遺失，而重新導向頁面 (可能是內部頁面) 會因此顯示為反向連結網域。該次造訪將會分類為「工作階段重新整理」。

**案例 4: 跨網域流量**

訪客從會觸發套裝 A 的網域移至會觸發套裝 B 的另一個網域。如果套裝 B 的內部 URL 篩選器包含第一個網域，則套裝 B 的該次造訪將記錄為內部，因為行銷管道會將之視為第二個套裝中的新造訪次數。該次造訪將會分類為「工作階段重新整理」。

**案例 5: 登入頁面載入時間過長**

訪客登陸了內容繁多的頁面 A，而 Adobe Analytics 程式碼位於該頁面底部。在系統載入所有內容 (包括 Adobe Analytics 影像要求) 之前，訪客點擊了頁面 B，頁面 B 也觸發了自身的 Adobe Analytics 影像要求。由於頁面 A 的影像要求並未載入完畢，第二個頁面就會在 Adobe Analytics 中顯示為該次造訪的第一次點擊，而頁面 A 則為反向連結。該次造訪會分類為「工作階段重新整理」。

**案例 6: 清除 Cookie 中繼網站**

訪客造訪網站，而中繼工作階段清除了 Cookie。首次和上次接觸管道都會重設，而該次造訪會分類為「工作階段重新整理」(因為反向連結為內部連結)。
