---
description: DFA 的 Genesis 整合採用 DFA Floodlight 設定 ID (dfa_SPOTID)，這可以提升 DFA 與 Adobe 資料收集系統之間的報表一致性。
keywords: DFA
seo-description: DFA 的 Genesis 整合採用 DFA Floodlight 設定 ID (dfa_SPOTID)，這可以提升 DFA 與 Adobe 資料收集系統之間的報表一致性。
seo-title: 更新網站的資料收集代碼
solution: Analytics
title: 更新網站的資料收集代碼
topic: Data connectors
uuid: a97d1b62-f883-48b1-9516-4f889e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 更新網站的資料收集代碼{#update-your-web-site-s-data-collection-code}

DFA 的 Genesis 整合採用 DFA Floodlight 設定 ID (dfa_SPOTID)，這可以提升 DFA 與 Adobe 資料收集系統之間的報表一致性。

>[!NOTE]
>
>在Google DFA的最新版本中，「精選」一詞已變更為Floodlight。 JavaScript 參數 `dfa_SPOTID` 是根據 Spotlight 術語而命名的，但用於兩個版本中。

若要在您的網站上啟用 DFA 整合，您必須新增下列項目，以更新您的 JavaScript 資料收集代碼:

* DFA 的整合模組
* 新增至您的收集代碼

## DFA 的整合模組 {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

The DFA integration leverages the Adobe Experience Cloud Integrate Module, which adds functionality to your core JavaScript data collection code ( `s_code.js`). 當您從「程式碼管理員」下載AppMeasurement for Javascript程式碼時，「整合模組」會做為。zip檔案的一 [部分](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。 只有在您需要其他協助才能找到Adobe顧問時，才與您聯絡。

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## 新增至您的收集代碼 {#section-8f98c727f1ba414fb8b4f02d696b8791}

Data connectors 會根據您在整合精靈中啟動 DFA 整合時所做的選取，產生對您 JavaScript 資料收集代碼的自訂新增項目，並透過電子郵件傳送給您。請在 `s_code.js` 檔案的主要區段中插入此代碼 (而不是插入至 `doPlugins` 函數或任何其他函數)。

下方顯示的範例代碼僅供說明之用；請使用您完成「Data connectors 整合精靈」之後透過電子郵件收到的代碼。

收集代碼由下列元件組成:

* DFA 整合設定
* 整合所需的外掛程式

**DFA 整合設定**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA 整合設定區塊會設定 DFA 整合所需的變數。其中每個變數的值分別來自於下列來源:

**CSID**: 客戶端 ID。在您完成整合精靈後，隨即由 DFA 產生。Data connectors 會以您的 DFA CS ID 預先填入此變數，並且在您完成整合精靈後，透過設定電子郵件將此值傳送給您。如果您的帳戶啟用了「進階廣告服務」，則不需要此變數。

**SPOTID**: Floodlight 設定 (先前稱為 Spotlight ID)。Data connectors 會根據您在整合精靈中指定的 DFA 帳戶資訊，以您的 DFA Floodlight 設定 ID 預先填入此變數。

**tEvar**: 傳送變數。Data connectors 會以您在整合精靈中為閱覽變數指定的 Analytics 變數名稱，來預先填入此變數。在變更此值時，請務必使用 Adobe Engineering 或 Engineering 服務審慎協調。

**errorEvar**: 錯誤變數。Data connectors 會以您在整合精靈中為 DFA 查詢失敗變數指定的 Analytics 變數名稱，來預先填入此變數。

**timeoutEvent**: 逾時事件。Data connectors 會以您在整合精靈中為逾時事件變數指定的 Analytics 變數名稱，來預先填入此變數。

**requestURL**: 用來查詢廣告資訊的遠端 DFA 主機。未經 Adobe 的指示，請勿變更此值。

**maxDelay**: 指定 JavaScript 資料收集代碼等待 DFA Floodlight 伺服器發出回應的時間長度，以毫秒為單位。Adobe 建議您根據自己的網站流量，使用此值試驗出最適合的值。例如，增加此值通常可收集到較多 DFA 資料，但也會提高失去基本訪客資料的風險 (如果訪客在延遲時段內離開網站)。降低此值可減少失去點擊資料的風險，但可能也會減少與 Adobe 點擊資料一起傳送的 DFA 資料量。

**visitCookie**: 用來將 DFA 呼叫限定為每次造訪執行一次之 cookie 的名稱。

**clickThroughParam**: 一個查詢字串，通常包含在所有廣告中，用來通知整合模組有點按動作發生。查詢字串中若有此參數存在，則無論在過去 30 分鐘內是否查詢過訪客，都會執行對 DFA Floodlight 伺服器的要求。

**newRsidsProp**: (可選) 對應至未使用的流量屬性變數。DFA 整合會收集此值並將其存放在造訪 cookie 中，以識別對特定訪客收集資料的報表套裝。只有在使用 Adobe Engineering 服務進行自訂實施時，才需要此屬性。

**整合所需的外掛程式**

收集代碼新增項目加入了其他外掛程式，可改善 DFA 整合的作業效能:

* 將 DFA 查詢限定為每次造訪執行一次
* 提供 cookie 名稱彈性。雖然大部分的組織都使用 s_dfa，但對於 DFA 整合，您可以使用任何有效的 cookie 名稱。
* 消除非必要的重新導向。由於閱覽資料會以即時的方式收集，因此 Adobe 收集伺服器和 DFA 有可能會在每一次的頁面檢視交換資料。如果資訊不是必要的，外掛程式將會封鎖這些資料交換。

>[!CAUTION]
>
>外掛程式用來消除不必要DFA查詢的其中一個機制是網域型瀏覽Cookie。 如果訪客在 DFA 有所影響的閱覽或點進執行之後跨越了多個網域，跨越多個網域的整合報表套裝將會誇大點進和閱覽資料。

