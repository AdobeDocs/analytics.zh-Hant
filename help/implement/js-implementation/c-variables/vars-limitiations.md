---
description: 以高階方式查看變數及其限制。
keywords: Analytics Implementation;variable;limitations;limits
subtopic: Variables
title: 變數和限制
topic: Developer and implementation
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 變數和限制

以高階方式查看變數及其限制。

>[!NOTE]
>
>若要深入瞭解最常見的 Analytics 變數，請參閱[設定變數](/help/implement/js-implementation/c-variables/configuration-variables.md)和[頁面變數](/help/implement/js-implementation/page-variables/page-variables.md)。

下列的表格提供有關 [!DNL Analytics] 變數的簡單資訊:

| 變數 | 說明 |
|---|---|
| s_account | 判斷資料儲存及報告所在的報表套裝。 |
| browserHeight | 顯示瀏覽器視窗的高度。 |
| browserWidth | 顯示瀏覽器視窗的寬度。 |
| campaign | 識別用以吸引訪客進入網站的促銷活動。此 *`campaign`*&#x200B;的值通常取自查詢字串參數。 |
| channel | 通常會識別您的網站的區段。例如，某零售商的網站擁有如電子產品、玩具或服飾等區域。媒體網站可能會有新聞、運動或商業等區段。 |
| charSet | 將網頁的字元集轉換為 UTF-8。 |
| colorDepth | 顯示畫面的每個像素上用以顯示顏色的位元數。 |
| connectionType | (在 Microsoft Internet Explorer 中) 指出瀏覽器是設定於 LAN 還是數據機連線。 |
| cookieDomainPeriods | 判斷頁面 URL 的網域中所含的時段數，以決定 [!DNL Analytics][!UICONTROL  訪客 ID] (s_vi) Cookie 設定所在的網域。若為 `www.mysite.com`，*`cookieDomainPeriods`* 應為「2」。若為 `www.mysite.co.jp`，*`cookieDomainPeriods`* 應為「3」。 |
| cookieLifetime | 讓 JavaScript 和 [!DNL Analytics] 伺服器用來決定 Cookie 的有效期限。 |
| cookiesEnabled | 指出第一方工作階段 Cookie 是否可由 JavaScript 設定。 |
| currencyCode | 決定收入在進入 [!DNL Analytics] 資料庫時所要套用的轉換率。[!DNL Analytics] 資料庫會以您所選擇的貨幣來儲存所有金額。若該貨幣與 *`currencyCode`* 中指定的貨幣相同，或 *`currencyCode`* 空白，則不會套用轉換。 |
| dc | 可讓您設定您的資料所要傳送到的資料中心。 |
| doPlugins | *`doPlugins`* 是 *`s_doPlugins`* 函數的參考。可允許在 JavaScript 檔案內的適當位置呼叫 *`s_doPlugins`* 函數。 |
| dynamicAccountList | 動態選取資料所要傳送到的報表套裝。此&#x200B;*`dynamicAccountList`* 變數包含用來決定目標報表套裝的規則。 |
| dynamicAccountMatch | 使用 DOM 物件來擷取套用了  *`dynamicAccountList`* 中所有規則的 URL 區段。此變數只有在 *`dynamicAccountSelection`* 設為「True」時有效。 |
| dynamicAccountSelection | 可讓您根據各頁面的 URL 動態選取報表套裝。 |
| dynamicVariablePrefix | 可讓您在部署中為動態填入的變數加上標記。Cookie、要求標題和影像查詢字串參數皆可動態填入。 |
| eVarN | 用來建置 [!DNL Analytics][!UICONTROL  轉換模組]內的自訂報表。當 eVar 設為訪客的值時，[!DNL Analytics] 會記住該值，直到它過期為止。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。 |
| events | 記錄一般購物車成功事件和自訂成功事件。 |
| fpCookieDomainPeriods | 判斷頁面的網域中所含的時段數，以決定[!DNL Analytics]訪客 ID[!UICONTROL  (s_vi) Cookie 以外的 ] Cookie 設定所在的網域。 |
| hierN。 | 判斷某個頁面在您的網站階層中的所在位置。此變數對於擁有超過三層結構的網站尤其實用。 |
| homepage | (在 Internet Explorer 中) 指出目前的頁面是否設為使用者的首頁。 |
| javaEnabled | 指出瀏覽器中是否啟用了 Java。 |
| javascriptVersion | 顯示瀏覽器支援的 JavaScript 版本。 |
| linkDownloadFileTypes | 以逗號分隔的副檔名清單。若您的網站包含檔案的連結，且檔案具有其中任何副檔名，這些連結的 URL 將出現在[!UICONTROL 「檔案下載」]報表中。 |
| linkExternalFilters | 若您的網站含有許多外部網站的連結，而您不想追蹤所有的退出連結，您可以使用  *`linkExternalFilters`* 來報告退出連結的特定子集。 |
| linkInternalFilters | 決定您網站上的哪些連結是退出連結。這是篩選器的逗號分隔清單，它表示屬於網站組成部分的連結。 |
| linkLeaveQueryString | 決定是否應將查詢字串納入[!UICONTROL 「退出連結」]和[!UICONTROL 「檔案下載」]報表中。 |
| linkName | 一個用於[!UICONTROL 連結追蹤]中的可選變數，可判斷自訂、下載或退出連結的名稱。在一般情況下不會使用 *`linkName`* 變數，因為此變數會由 *`tl()`* 函數中的第三個參數取代。 |
| linkTrackEvents | 包含應隨自訂、下載和退出連結而傳送的事件。只有在 *`linkTrackVars`* 包含「事件」時，才會考量此變數。 |
| linkTrackVars | 以逗號分隔，會隨自訂、退出與下載連結而傳送的變數清單。如果將 *`linkTrackVars`* 設為 「」，則所有擁有值的變數都會隨連結資料傳送。 |
| linkType | 一個用於連結追蹤中的可選變數，可判斷會出現連結名稱或 URL 的報表 (自訂、下載或退出連結)。*`linkType`* 在一般情況下不需使用，因為 *`tl()`* 函數中的第二個參數會加以取代。 |
| mediaLength | 指定所要播放之媒體的總長度。 |
| mediaName | 指定視訊或媒體項目的名稱。此變數只能透過[!UICONTROL 「資料插入 API」]和[!UICONTROL 「完整處理資料來源」]來使用。 |
| mediaPlayer | 指定用來使用視訊或媒體項目的播放器。 |
| mediaSession | 指定所使用的視訊或媒體資產區段。 |
| Media.trackEvents | 識別哪些事件應隨媒體點擊而傳送。此變數僅適用於 JavaScript [!UICONTROL ActionSource]。 |
| Media.trackVars | 識別哪些變數應隨媒體點擊而傳送。此變數僅適用於 JavaScript [!UICONTROL ActionSource]。 |
| mobile | 控制使用 Cookie 和訂閱者 ID 來識別訪客的順序。 |
| s_objectID | 應在連結的 [!UICONTROL onClick] 事件中設定的全域變數。透過為頁面上的連結或連結位置建立唯一的物件 ID，您將可改善訪客點按對映追蹤，或使用訪客點按對映來報告連結類型或位置，而不是連結 URL。 |
| pageName | 包含您的網站上各個頁面的名稱。若 *`pageName`* 空白，則會以 URL 表示 [!DNL Analytics] 中的頁面名稱。 |
| pageType | 用途僅止於指定 404 (找不到頁面) 錯誤頁面。此變數只有一個可能的值，即 "errorPage"。在 404 錯誤頁面上，*`pageName`*&#x200B;變數不應填入。 |
| pageURL | 極少數的情況下，頁面的 URL 不會是您要在 [!DNL Analytics] 中報告的 URL。為因應這些情況，[!DNL Analytics] 提供 *`pageURL`* 變數，可覆寫頁面的實際 URL。 |
| 外掛程式 | 在 Netscape 和 Mozilla 瀏覽器上，列出瀏覽器中所安裝的外掛程式。 |
| 產品 | 用來追蹤產品和產品類別，以及購買數量和購買價格。此&#x200B;*`products`*&#x200B;變數一律應與成功事件一起設定。您可以視需要選擇使用 *`products`* 變數追蹤自訂數值和貨幣事件，以及[!UICONTROL 商品銷售] eVar。 |
| propN | 用來建置 [!DNL Analytics][!UICONTROL  流量模組]內的自訂報表。[!UICONTROL prop] 可作為計數器 (用以計算頁面檢視的傳送次數)、用於路徑分析報表，或用於關聯報表中。 |
| purchaseID | 讓 [!DNL Analytics] 用來防止重複計算同一份訂單。只要您的網站上使用購買事件，則應使用 *`purchaseID`* 變數。 |
| referrer | 還原遺失的反向連結資訊。 |
| 解析度 | 顯示檢視網頁之訪客的螢幕解析度。 |
| server | 顯示網頁的網域 (以指出訪客進入的網域) 或為頁面提供服務的伺服器 (以供負載平衡快速參考之用)。 |
| state | 擷取網站訪客居住所在的州別。 |
| trackDownloadLinks | 若您要在網站上追蹤可下載檔案的連結，請將 *`trackDownloadLinks`* 設為 'true'。若 *`trackDownloadLinks`* 為「true」，則 *`linkDownloadFileTypes`* 會判斷哪些連結是可下載的檔案。 |
| trackExternalLinks | 若 *`trackExternalLinks`* 為「true」，則 *`linkInternalFilters`* 和 *`linkExternalFilters`* 會判斷所點按的任何連結是否為退出連結。 |
| trackingServer | 用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。用於非安全頁面。 |
| trackingServerSecure | 用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。用於安全頁面。 |
| trackInlineStats | 決定是否蒐集訪客點按對映資料。 |
| transactionID | 將離線資料連結至線上交易 (例如在線上產生的潛在客戶或購買)。每個傳送至 Adobe 的唯一 *`transactionID`* 都會記錄下來，以便[!UICONTROL 資料來源]上傳有關該交易的離線資訊。請參閱[資料來源指南](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。 |
| s_usePlugins | 若 *`s_doPlugins`* 函數可供使用且包含有用的程式碼，則 [!UICONTROL s_usePlugins] 應設為「true」。當 [!UICONTROL usePlugins] 設為「true」時，則會在每個影像要求之前呼叫 *`s_doPlugins`* 函數。 |
| visitorID | 訪客可由  *`visitorID`* 標籤來識別，或由 IP 位址/使用者代理識別。*`visitorID`* 最多可達 100 個英數字元，且不可含有連字號。 |
| visitorNamespace | 如果 JavaScript 檔案中使用了 *`visitorNamespace`*，請勿將其刪除或更改。此變數可用來識別 Cookie 設定所在的網域。如果 *`visitorNamespace`* 有所變更，則 中報告的所有訪客都可能變成新訪客。[!DNL Analytics]簡言之，未經 Adobe 顧問許可，請勿更改此變數。 |
| zip | 擷取網站訪客居住地的郵遞區號。 |

