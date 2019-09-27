---
description: 流量來源報表能讓您深入瞭解訪客與您網站的互動。
seo-description: 流量來源報表能讓您深入瞭解訪客與您網站的互動。
seo-title: 流量來源報表
solution: Analytics
title: 流量來源報表
topic: Ad Hoc Analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 流量來源報表

流量來源報表能讓您深入瞭解訪客與您網站的互動。

## 流量來源報表 {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

流量來源報表能讓您深入瞭解訪客與您網站的互動。

流量來源報表可讓您:

* 分析訪客行為的重要方面。
* 監視和瞭解流量模式。
* 確定流行的網站內容。
* 以任何可度量的標準劃分訪客。

**通用持續性**

在[!UICONTROL 「流量來源」]中，所有報告值均會保留並接收評分，直至被覆寫或瀏覽結束 (以最先發生的為準)。以前，僅保留關鍵字和反向連結網域。例如，如果訪客執行  "DVD" Google 搜尋，並因此前往您的網站進行 $100 購買，則報告會將 $100 評分分配給關鍵字 "DVD" 以及 Google 搜尋引擎。This functionality is unalterable, regardless of [!DNL Admin Console] settings.

## 搜尋關鍵字 {#concept_071FDCBD0A3B4242BA00744786D1C59C}

顯示所有、付費、免費搜尋的關鍵字劃分。

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL 搜尋關鍵字 - 全部]**: 顯示用於尋找您網站的每個搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

**[!UICONTROL 搜尋關鍵字 - 付費]**: 顯示用於尋找您網站的每個付費搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

**[!UICONTROL 搜尋關鍵字 - 免費]**: 顯示用於尋找您網站的每個免費搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

## 搜尋引擎 {#concept_351CDE4F5FC44371B6B657064E125134}

顯示訪客用來進行所有、付費、免費搜尋的搜尋引擎。

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL 搜尋引擎 - 所有]**: 顯示訪客使用哪些搜尋引擎找到您的網頁。圖表顯示用於尋找您網站的搜尋引擎的百分比劃分。

**[!UICONTROL 搜尋引擎 - 付費]**: 顯示訪客使用哪些付費關鍵字搜尋引擎找到您的網頁。圖表顯示用於尋找您網站的搜尋引擎的百分比劃分。

**[!UICONTROL 搜尋引擎 - 免費]**: 顯示訪客使用哪些免費關鍵字搜尋引擎找到您的網頁。圖表顯示用於尋找您網站的搜尋引擎的百分比劃分。

## 反向連結網域 {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

顯示對網站「成功量度」影響最大的客戶的引薦網域。反向連結分為 2 種主要類別: 網域與 URL。「網域」指的是網域名稱，以不含查詢字串或子目錄的基本網域形式出現。URL 包括基本網域名稱，亦包括任意查詢字串或子目錄。

## 原始反向連結網域 {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

顯示為您的網站帶來客戶的原始反向連結。客戶可以多次瀏覽您的網站，而每次瀏覽有不同的反向連結。該報表顯示客戶首次瀏覽您網站時的反向連結資訊。您可以透過該等資訊瞭解是否客戶繼續使用原始反向連結和檢視模式。您可以檢視原始反向連結產生的訪客數量，或每個原始反向連結對網站收入的貢獻。可在訪客每次存取您網站時填入反向連結報告，即使此訪客在一個工作階段中 (瀏覽過期之前) 多次存取此網站。

## 反向連結 {#concept_40CF9C2D10B94E82819BC65A232F05C3}

顯示訪客在到達您網站前的網域或 URL、訪客找到您的網站時所使用的方法，以及由這些反向連結位置產生的瀏覽次數。

<!-- 

c_reports_referrers.xml

 -->

例如，如果訪客從網站 A 點按連結找到您的網站，如果網站 A 沒有定義為您的網域的一部分，它就是反向連結。在 Marketing Reports &amp; Analytics 實施中，您的實施顧問會幫助您定義屬於您網站一部分的網域和 URL。(此變更在實作期間後即可完成。) 

任何非這些已定義網域和 URL 之一部分的網域或 URL，就會被視為反向連結。例如，將網頁 A 和網頁 B 新增至內部 URL 篩選器，但網頁 C 沒有加入。在這種情形下，網頁 C 就會被視為反向連結。

See [Internal URL Filters](https://marketing.adobe.com/resources/help/en_US/reference/internal_URL_filter_admin.html) in the [!DNL Admin Console] help for more information.

>[!NOTE]
>
>Marketing reports and analytics records a referring domain as an email when visitors click an emailed message link containing the protocol [!DNL imap://] or [!DNL mail://] and arrive at your site. 例如，來自 [!DNL https://mail.yahoo.com] 的任何點按不會被計算為電子郵件反向連結，因為通訊協定為 [!DNL https://]。來自 Outlook 的電子郵件會報告到「分類/建立書籤」明細項目，而任何已知搜尋引擎網域處的 HTTP 通訊協定反向連結會報告到「搜尋引擎」明細項目。

## 反向連結類型 {#concept_689E42D8F96C450DA41C7167C7388198}

透過追蹤並記錄每次瀏覽的訪客反向連結位置，您可以瞭解每次瀏覽中訪客找到您網站的方式。

<!-- 

c_reports_ref_types.xml

 -->

下列清單定義反向連結的各種類型:

* *訪客點按其他網頁 (未定義為您網站的一部分) 上的連結進入您的網站時，會記錄其他網站反向連結。*
* *訪客使用搜尋引擎存取您的網站時，會記錄搜尋引擎反向連結。*
* 以下情形會記錄&#x200B;*分類/建立書籤*&#x200B;反向連結:

   * 如果訪客透過非瀏覽器連結進入您的網站 (例如透過電子郵件)。
   * 如果訪客在瀏覽器中直接輸入您網站的 URL。
   * 如果訪客按一下其個人硬碟上的 HTML 連結。
   * 如果訪客經由選取瀏覽器書籤而存取您的網站。

**定義**

執行此報表時可能會顯示下列明細項目:

**網站內**: 這些項目是指被內部 URL 篩選器加上標記的 URL。這些項目不會計為反向連結例項，但可在報告其他量度時顯示。

**無Java Script**:沒有JavaScript，因此類型無法識別（未知）。 這表示瀏覽器上的用戶端未提供反向連結資訊，因而未回報可支援 Javascript。這些項目不會計為「反向連結例項」，但可在報告其他度量時顯示。

**USENET (新聞群組)**: 這表示反向連結的 URL 是以 `news://` :// 開頭的。因此，反向連結被發佈在 Usenet 新聞群組上，而不是網頁上。

>[!NOTE]
>
>Referrer Type logic matches other traffic sources reports (such as [!UICONTROL Referrers] and [!UICONTROL Referring Domains]). 這應該會使[!UICONTROL 「反向連結類型」]報表中較少或完全不會出現「網站內」和「無 JavaScript」 明細項目。

