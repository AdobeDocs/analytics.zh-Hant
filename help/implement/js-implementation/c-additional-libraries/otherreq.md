---
description: 要在不使用 JavaScript 的情況下實施 Analytics，會有其他需求和設定需要考量。
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
title: 不使用 JavaScript 指南實作
topic: Developer and implementation
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 不使用 JavaScript 指南實作

要在不使用 JavaScript 的情況下實施 Analytics，會有其他需求和設定需要考量。

您可以檢視範例程式碼，以進一步瞭解實施方式。下列資訊列出其他需求和設定:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**區分大小寫**

參數名稱 (`pageName`、`purchaseID` 等) 會區分大小寫，且除非如[查詢參數](/help/implement/js-implementation/data-collection/query-parameters.md)中所示之表格指定的方式顯示，否則將無法正確記錄資料。

**為查詢參數編碼**

每個查詢字串參數的值都必須進行 URL 編碼。URL 編碼可將顯示於查詢字串時通常屬非法的字元 (例如空白字元)，轉換為以 `%` 開頭的編碼字元。例如，空白字元可轉換為 `%20`.

這項功能的 JavaScript 版本稱為逸出 (escape)，而解碼則稱為解除逸出 (unescape)。Microsoft IIS 5.0 版也具有可用於查詢字串編碼的逸出和解除逸出功能。其他 Web 伺服器指令碼語言也提供編碼/解碼公用程式。

**最大變數長度**

每個變數都有其最大長度。各個變數的這個長度都會指定於  [Analytics 變數](/help/implement/js-implementation/c-variables/sc-variables.md).超過變數的最大長度時，將導致此變數的值在儲存及顯示於 Analytics 時遭截斷。

**無效字元**

字元碼超過十進位數 128 的字元無效，128 以下的非列印字元碼也是如此。HTML 格式 ("&lt;h1&gt;") 也無效，商標、註冊商標和版權符號也是如此。

**安全 (&lt;https:&gt; ，相對於不安全 (&lt;http:&gt;)) 影像要求**

在透過 https (安全通訊協定) 存取的頁面上，影像要求的 URL 部分會進行變更，以因應不同的資料收集伺服器集合。

下列資訊列出用於安全和不安全影像要求的不同 URL。

* 上例 URL 中的 `*` 表示 Adobe 顧問提供給您的資料中心特定 URL。Adobe 使用了數個資料中心，您必須實施組織所被指派的正確 URL。任何在您的公司帳戶中從「管理控制台」下載的程式碼，都會自動被提供正確的資料中心。從外部來源提供的程式碼可能需經過更正，才會指向正確的資料中心。
* 使用多個報表套裝的客戶只應列在目錄區段中，而不列在 URL 的網域區段中，如下所示。
* 上例 URL 中的 `*` 表示 Adobe 顧問提供給您的資料中心特定 URL。Adobe 使用了數個資料中心，您必須實施組織所被指派的正確 URL。

**URL 和反向連結 URL**

URL 和反向連結 URL 可透過 `g=` 和 `r=` 變數從伺服器填入。請使用 Request ServerVariables (`HTTP\_REFERRER`)、Reequest ServerVariables `(URL) (IIS/ASP)` 或適當的變數做為您的伺服器/指令碼技術。在追蹤反向連結 URL、網域、搜尋引擎和搜尋詞時，反向連結 URL `( r=)` 是極為重要的。

若未使用 pageName，就必須以不重複的方式填入目前的 URL 欄位。若 pageName 或目前的 URL `(g=)` 皆未填入，記錄即無效，且不會受到處理。無論如何，URL 都是處理記錄時的必要欄位。

**快取的影響**

HTML 和其他網頁可由位於訪客與提供內容的網站之間的瀏覽器或伺服器快取。快取會使頁面檢視和其他事件的計數失去精確性，除非您使用了「防快取」技術。

Adobe 的標準 JavaScript 具有動態方法可變更影像要求，以避免頁面和影像快取，而保有正確的頁面檢視計數。

但在建立伺服器端影像要求時，此隨機機制並不會運作。使用伺服器端影像要求時，頁面重新載入和快取的頁面 (在瀏覽器的快取中，或 Proxy 伺服器中) 在某些情況下並不會計數。

SSL (`https:`) 頁面依定義不會進行快取，因此這項警告僅適用於不安全 (`http:`) 頁面。此外，對於具有參數 (`https://www.samplesite.com/page.asp?parameter=1`) 或特定副檔名 (`.asp`、`.jsp` 等) 的頁面，也不會進行快取。

下列範例也說明先在伺服器端聚集影像要求，然後在瀏覽器中添加隨機數字的基本 JavaScript 解決方案。此方法可克服在透過 https: 通訊協定存取的靜態 HTML 頁面上所將發生的快取問題。

**nameSpace 變數**

nameSpace 查詢字串參數是實施非 JavaScript 時的必要項目。

範例: ns=nameSpace

請連絡您的 Adobe 顧問或客戶經理，以取得組織的 nameSpace 值。
