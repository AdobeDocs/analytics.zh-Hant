---
description: 針對 Analytics 的最常問問題提供解答和疑難排解建議。
keywords: Analytics 疑難排解
seo-description: 針對 Analytics 的最常問問題提供解答和疑難排解建議。
seo-title: 常問的問題
title: 常問的問題
uuid: 285b0ea4-aa07-4d39-a74 f-37b1 d02 d19 f1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# 常見問答集

針對報告與分析中最常詢問的Analytics問題提供解答和疑難排解建議。For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**我的帳戶已鎖定；我要如何解除鎖定？**

若要重新啓用帳戶，請聯絡組織內的管理員。See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**為甚麼我知道資料已收集，為甚麼會看到空白報表？**

要疑難排解報表資料，需檢查幾項：

* 檢查使用的度量：有些報表預設為「報告與分析」中的收入。確定您檢視的量度與報表相關。
* 檢查日期範圍：日期範圍(尤其是組織的資料保留原則)無法傳回任何資料。檢查以確定您的日期範圍已正確設定。
* 檢查內部URL篩選器：在您正確定義內部URL篩選器後，有些流量來源報表才會運作。

**為何導覽功能表中缺少某些報表？**

從功能表中最常源自限制權限或功能表自訂的功能表中遺失任何報表。請與組織中的產品管理員聯絡，以確保您有權存取所需的所有維度和度量，且報表套裝的功能表結構不會加以自訂。

**為甚麼有些長值會被切斷？**

Adobe Analytics中幾乎所有變數都有字元限制。頁面名稱的字元限制為100個字元，而自訂轉換變數(eVar)則有255個字元限制。Adobe建議您確保傳送給Adobe的值簡明扼要，以避免截斷。

**為甚麼報告的延遲會大延遲？**

即時報告可讓某些流量度量在幾分鐘內推出，而轉換和其他處理密集資料通常會在30-90分鐘內提供。雖然 Experience Cloud 平台十分健全，但偶爾仍可能出現報告延遲的情形。此延遲稱為延遲。See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**為何我無法在iPhone上看到裝置版本？**

Apple裝置會在使用者代理字串中報告韌體版本，而非裝置版本。使用Adobe Analytics提供的資訊來判斷iPhone裝置版本很困難。See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**為甚麼我的報表底部總計值不符合值？**

維度值通常適用於多個位置；例如，跨午夜的瀏覽或屬於單一訂單的多個產品。維度值會報告所有適用行項目，但會在報表總計中進行去重復化。See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**如何從報表套裝中的特定IP位址排除資料？**

您可以消除報告中的內部網站活動資料，例如網站測試和員工使用情形。此功能可讓您和您的同事拜訪您的網站，但不影響流量資料的準確性。See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**我可以刪除報表套裝嗎？**

無法刪除報表套裝。不過，報表套裝可從Adobe Analytics中的所有檢視中隱藏。請注意，傳送至隱藏報表套裝的伺服器呼叫仍會計入您的每月合約限制。See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**使用分段時，我應該使用哪個容器？Page view, visit, or visitor?**

您使用的區段容器取決於您要擷取資料的廣度。頁面檢視容器只會出現符合區段標準的點擊，用於篩選瀏覽中無關的部分。瀏覽容器會將一次瀏覽的所有點擊放入一或多個符合區段標準的點擊，以便一般檢視工作階段。訪客容器會引入點擊符合區段標準的所有存取，對查詢人員有用。您是決定哪個區段容器最適合使用的分析師。See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**為甚麼我的區段無法顯示在資料倉庫中？**

由於資料倉庫獨特的處理架構，平台並未最佳化來處理某些類型的資料，例如路徑分析。See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
