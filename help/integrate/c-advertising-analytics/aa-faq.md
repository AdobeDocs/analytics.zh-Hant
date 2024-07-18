---
description: 有關 Advertising Analytics 的常見問題集。
title: Advertising Analytics 的常見問題集
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 02b6c4f4504785353f9b2457099d3332cd25a852
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 37%

---

# 常見問答

## 存取/權益 {#access}

+++ 我需要是Adobe Advertising Cloud或Adobe Advertising Cloud (AMO)客戶才能存取這項功能嗎？

否，此功能適用於非Advertising Cloud和非AMO客戶。

AMO 客戶能運用現有的 Analytics-AMO 整合，因此不需要使用 Ad Analytics。

+++

+++ 哪些Adobe Analytics SKU授予您使用Advertising Analytics的權益？

Advertising Analytics適用於Adobe Analytics

* [選取](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)

* [Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html)

+++

+++ 使用Advertising Analytics需要額外付費嗎？

不需要，除了適當的SKU布建，Advertising Analytics不需要額外付費。

+++

+++ Advertising Analytics是否會計入我的伺服器呼叫使用量

否，Advertising Analytics使用特殊的資料來源型別，因此不會產生伺服器呼叫成本。

+++

+++ 如果我已經使用Advertising Cloud/AMO，還可以使用Advertising Analytics功能嗎？

任何相容的搜尋引擎帳戶都會傳入Advertising Analytics，並顯示為唯讀。 所有編輯或更新作業都應該在 Advertising Cloud/AMO 中處理。

+++

+++ 我擁有正確的SKU，但無法存取Advertising Analytics，為什麼？

Advertising Analytics僅適用於Adobe Analytics管理員，不過管理員可以向非管理員授予存取權。 如需存取權限，請聯絡您的管理員。

+++

## 使用 Advertising Analytics {#using}

+++ Advertising Analytics包含哪些搜尋引擎帳戶？

搜尋引擎帳戶包括Google AdWords和Microsoft Bing。

+++

+++ 若要存取Advertising Analytics，我該前往何處？

登入Adobe Analytics後，請導覽至[!UICONTROL 管理員]。 然後選取[!UICONTROL Advertising Analytics]以新增您的搜尋引擎帳戶。

+++

+++ 資料收集和傳遞至Analytics的方式為何？

Advertising Analytics運用一系列自訂API，透過Adobe Advertising Cloud將資料從搜尋引擎傳遞至Analytics。

+++

+++ 這項整合能提供給我哪些搜尋資料？

您將獲得

* 曝光數
* 點擊數
* 成本
* 品質分數
* 直接來自搜尋引擎的平均位置，以及
* AMO ID例項（按一下「例項」）。

+++

+++ 我可以根據其他Advertising Analytics資料（量度/維度）劃分Analytics資料嗎？

否，原始搜尋資料將以獨立資料集的形式提供。 不過，您可以根據其他 Analytics 資料劃分實例版本的點選資料。

+++ 帳戶中各種狀態指標（擱置中、作用中、已暫停等）的定義是什麼？ 這些狀態指標中的每一項都可識別每個搜尋引擎帳戶的生命週期階段。

* [!UICONTROL 擱置中]
* [!UICONTROL 已暫停]表示帳戶先前已設定，但目前處於非作用中狀態。
* [!UICONTROL 作用中]表示帳戶已完全設定，而且正在提取搜尋資料。

+++

+++ 我正在嘗試將我的Advertising Analytics帳戶對應到特定的報表套裝，不過在報表套裝強制回應中找不到帳戶。 原因為何？

您必須先[布建所需的報表套裝，才能將報表套裝指派給Advertising Analytics帳戶，以進行Advertising Analytics報表](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
您可以透過個別的「管理員」頁面完成指派作業，請依序存取： 「管理員>報表套裝> `[select report suite]` >編輯設定> Advertising Analytics設定」。

+++

+++ 是否可以將虛擬報表套裝指派至Advertising Analytics帳戶？

虛擬報表套裝不會收集資料，因此您無法直接將Advertising Analytics帳戶對應至虛擬報表套裝。 不過，您可以將Advertising Analytics帳戶對應至您想要在其中檢視資料的虛擬報表套裝的父報表套裝。 搜尋引擎量度（點選次數/成本/曝光數）可能不會顯示在虛擬報表套裝中，除非您在以AMO ID （或其分類）為基礎的區段邏輯中加入「或」條件。 例如：新增「有 AMO ID 的所有點擊」後，區段中就會包含搜尋引擎量度。

+++

+++ Advertising Analytics量度可以在&#x200B;*行銷管道*&#x200B;報表中報告嗎？

不可以，行銷管道報表不含這些度量。

+++

+++ 系統會在什麼時候將搜尋資料提取至 Analytics?

系統從搜尋引擎提取搜尋資料的時間，大約是在您所屬 Analytics 資料中心當地時區的上午 6 點 (06:00)。這也是收集 AMO 資料並將其插入報表套裝的時間。 該資料接著會在資料插入 Analytics 的過程中轉換為報表套裝的時區。

+++

+++ 在點按&#x200B;*之前*&#x200B;可擷取哪些內容？ 我們是否在未點擊前就帶來了曝光數、成本、平均位置等資料？

AMO ID會擷取搜尋引擎量度：曝光數、成本、點按數、平均位置和平均品質分數。 如果沒有點擊次數，但是有曝光次數，則曝光數/位置/品質分數仍然會傳送到 Analytics。一般來說，如果沒有點擊數，也就不會有成本。

+++

+++ 會在哪個層級擷取此資料？ *訪客？點擊？*

搜尋引擎量度會在點選層級擷取，並連結至AMO ID （及其分類）。 這是屬於摘要層級資料，不會連結至造訪/訪客。因此，搜尋引擎量度只能用在屬於點擊層級範圍並且是以 AMO ID (而非其分類) 為基礎的區段。

AMO ID 也會在點擊登陸頁面時在該頁面擷取 (連結至造訪/訪客)，而且持續的下游行為會為其他 Analytics 量度取得分數 (直到該 AMO ID 過期或是由新的 AMO ID 覆寫為止)。它會像其他 eVar 一樣完全整合到資料集中。

+++

+++ 我們是否僅擷取google.com或&#x200B;*國家/地區版本* (例如google.co.uk、google.it、google.fr或google.de)？

「廣告平台」分類會擷取「Google Adwords」和「Bing Ads」等值。 常用的最佳作法就是將國碼納入行銷活動命名的一部分。接著，您就可以往下篩選或區隔 (例如，如果所有的行銷活動是以 countrycode_ 開頭，您可建立一個區段，讓其中的行銷活動 (AMO ID) 是以「UK_」為開頭，就能取得英國的資料)。

+++

+++ 「AMO成本」量度是按照搜尋引擎的報告為每個關鍵字/廣告支付的成本。 這是淨成本或總成本？

「AMO成本」僅為支付給搜尋引擎的成本。 不包括任何廣告商或搜尋最佳化/管理平台費用。

+++

+++ 是否計畫包含其他廣告管道，例如&#x200B;*顯示*&#x200B;或&#x200B;*社交*？

否，目前我們在藍圖中沒有針對這些其他管道的計畫。

+++


## 自動與手動追蹤 {#section_7437C4698A6D482EB7ED94A948390119}

+++ 設定我的Advertising帳戶時，系統指出&#x200B;*自動追蹤*&#x200B;可能會導致非預期的結果。 可能會發生哪幾種結果？

自動模式會嘗試以正確格式將URL引數附加至追蹤範本/目的地URL的結尾。 不過，您還是必須負責確認新增的URL引數正確無誤，才能順利前往最終的登陸頁面。 自動模式能將關鍵字插入登陸 URL，不過網站伺服器可能不支援含特殊字元的關鍵字。

+++

+++ 如果一開始設定了手動或自動追蹤，稍後可以切換至另一個追蹤模式嗎？ 有什麼影響？

可以，您可以切換追蹤模式，但在切換之前需要移除舊的追蹤邏輯。 這可能導致切換當天的追蹤中斷 (特別是從手動切換至自動的情況)。因此，除非絕對必要，否則建議不要切換。

* 從手動切換至自動：移除追蹤範本的手動新增專案，然後在Advertising Analytics使用者介面中，從手動切換至自動並儲存設定。 請注意，系統可能需要幾個小時才能填入自動追蹤代碼。

* 從自動切換至手動：在Advertising Analytics設定使用者介面中，從自動切換至手動，然後儘可能快速地部署手動追蹤代碼。 部署手動追蹤代碼時，若在搜尋引擎追蹤範本中看到自動追蹤代碼，請將其移除。

+++
