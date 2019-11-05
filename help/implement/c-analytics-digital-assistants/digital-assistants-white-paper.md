---
description: 'null'
seo-description: 'null'
seo-title: 對數位助理實作 Analytics
title: 對數位助理實作 Analytics
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: b7a92c7b7305c5456e6764b4329c51ad13f2609e

---


# 實作數位助理的Analytics

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

隨著雲計算、機器學習和自然語言處理領域的最新進展，數位助理正成為日常生活的一部分。 消費者開始與他們的裝置交談，期待他們能像人一樣理解和回應。 隨著這些平台變得愈加成熟，品牌便可以同樣真實與擬真的方式，向消費者展現其服務。舉例來說，消費者可能問這樣問:

* 「Alexa，我的車什麼時候需要換機油。」
* 「Cortana，我的支票帳戶餘額多少?」
* 「Siri，從我的銀行應用程式轉給小明 20 美元，付昨晚的晚餐錢。」

本頁概述如何使用Adobe Analytics來評估和最佳化這些體驗類型。

## 數位體驗架構概觀

![](assets/Digital-Assitants.png)

當今大多數的數位助理都按照類似的高階架構:

1. **裝置:** 配備麥克風的裝置 (例如 Amazon Echo 或手機)，可讓使用者詢問問題。
1. **數位助理:** 這個裝置再與提供數位助理技術支援的服務互動。這裡，語音被轉換成可為機器理解的意圖，進而剖析要求的詳細內容。只要理解了使用者的意圖，數位助理便將意圖和要求詳情傳遞給負責處理要求的應用程式。
1. **「應用程式」:** 應用程式可指手機應用程式或語音應用程式。應用程式負責回應要求。應用程式向數位助理回應，而數位助理再向使用者回應。

## 適合實施 Analytics 的位置

其中一個最適合實施 Analytics 的位置是在應用程式內部。應用程式會從數位助理接收意圖和詳細資訊，然後應用程式會決定如何回應。

在請求期間，有兩次可能會有助於將資料傳送至Adobe Analytics。

1. 請求傳送至您的應用程式時。
1. 一是應用程式傳回回應後。

如果您只對記錄客戶行為感興趣，以便未來的最佳化作業，則在傳回回應後將要求傳送至 Adobe Analytics。您將可完整瞭解要求的內容以及系統的回應方式。

## 新安裝

對於某些數位助理，當有人安裝技能時，您會收到通知，尤其是當涉及驗證時。 Adobe建議透過設定上下文資料變數來傳送「安裝」事件 `a.InstallEvent=1`。 這項功能並非所有數位助理都提供，但當它出現在檢視保留率時，會有所幫助。 下列程式碼範例會將「安裝」事件、「安裝日期」和AppID值傳送至上下文資料變數。

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## 多個助理或多個應用程式

您的組織可能需要適用於多種平台的應用程式。 最佳作法是在每個要求中納入應用程式 ID。This variable can be set in the `a.AppID` context data variable. 請遵照 `[AppName] [BundleVersion]` 格式，例如 Alexa 1.2 為 BigMac:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 使用者／訪客身分識別

Adobe Analytics使用 [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) ，將不同時間的互動關聯至同一個人。 大部分數位助理都 `userID` 會傳回可供您用來為不同使用者保留活動的資訊。 在大多數情況下，此值是您可以作為唯一識別碼傳入的值。 有些平台傳回的識別碼長於允許的100個字元。 在這些情況下，Adobe建議您使用標準雜湊演算法（例如MD5或Sha1），將唯一識別碼雜湊成固定長度值。

使用ID服務可在跨不同裝置（例如，網路到數位助理）對應ECID時提供最大的價值。 如果您的應用程式是行動應用程式，請依現狀使用Experience Platform SDK，並使用方法傳送使用者 `setCustomerID` ID。 However, if your app is a service, use the user ID provided by the service as the ECID, as well as setting it in `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 作業階段

因為數位助理採對話方式運作，故通常具備作業階段的概念。例如:

**消費者:**「Ok Google，幫我叫台計程車」

**Google:**「沒問題，您希望在什麼時間搭車呢?」

**消費者:**「晚上八點半」

**Google:**「好主意，司機八點半會準時到達」

研討會對於保持情境十分重要，而且有助於收集更多細節，讓數位助理更自然。 在對話上實作Analytics時，啟動新作業時需執行兩項動作：

1. **存取 Audience Manager:** 取得包含使用者的相關區段，這樣您便可自訂回應。(舉例來說，此人目前符合多管道折扣資格。)
2. **傳入新作業階段或啟動事件:** 請在首次將回應傳入 Analytics 時納入啟動事件。通常可透過設定 `a.LaunchEvent=1` 的內容資料來傳送。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## 意圖

每個數位助理都有演算法可偵測意圖，再將意圖傳遞至「應用程式」，讓應用程式知道要做哪些工作。這些意圖都以精簡方式表示要求。

舉例來說，若使用者說「從我的銀行應用程式轉給小明 20 美元，付昨晚的晚餐錢」，則意圖可能會表示為 *sendMoney*.

透過以eVar傳入每個請求，您可以針對對話應用程式的每個意圖執行路徑分析報表。 請確定您的應用程式也能處理請求，但無意。 Adobe建議將「未指定意圖」傳入目的上下文資料變數，而不要移除變數。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

或

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## 參數/槽/實體

除了意圖外，數位助理通常有一組鍵／值配對，可提供意圖的詳細資訊。 這些可稱為槽、實體或參數。 例如，「Siri,Send John $20 for dinner from my banking app」（昨晚從我的銀行應用發送Siri,Send John $20吃晚餐）將包含下列參數：

* 人物 = 小明
* 數量 = 20
* 原因 = 晚餐

您的應用程式中通常有有限數量的這些值。 若要在Analytics中追蹤這些值，請將其傳送至上下文資料變數，然後將每個參數對應至eVar。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 錯誤狀態

有時候，數位助理會提供您的應用程式不知道如何處理的輸入。 例如，「Siri,Send John 20 pags for dinner from my bankapp」

當發生這種情況時，請您的應用程式要求您加以澄清。 此外，將指出應用程式有錯誤狀態的資料傳送至Adobe，並附上eVar，以指定發生錯誤的類型。 請務必包含輸入不正確的錯誤和應用程式有問題的錯誤。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 裝置功能

雖然大部份的平台都不會公開使用者所接觸的裝置，但是卻會公開裝置的功能。 例如，音訊、螢幕、視訊等。 這項資訊很有用，因為它定義了與使用者互動時可使用的內容類型。 在測量裝置功能時，最好串連它們（依字母順序）。

範例: `":Audio:Camera:Screen:Video:"`

前導和尾隨冒號有助於建立區段。 例如，顯示所有具有功能的 `:Audio:` 點擊。

* [使用Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) Alexa的Amazon功能
* [使用Google](https://developers.google.com/actions/assistant/surface-capabilities) 上動作的Google功能

## 範例

| 「人」 | 裝置回應 | 動作/意圖 | 取得要求 |
| --- | --- | --- | --- | ---|
| 安裝 Spoofify | 無回應 | 安裝 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 播放 Spoofify | "好，玩假臉" | 播放 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 變換曲目 | "好吧，你想要哪首歌？" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 播放《小鯊魚》 | "好吧，玩粉紅方的"小鯊魚" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 變換播放清單 | "好吧，你想要什麼播放清單？" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 播放我最愛的歌曲播放清單 | "好，播放您最愛的歌曲播放清單" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 關閉音樂 | 沒有反應，音樂關閉 | 關閉 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
