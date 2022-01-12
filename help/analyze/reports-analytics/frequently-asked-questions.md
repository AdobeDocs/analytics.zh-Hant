---
description: 針對 Analytics 的最常問問題提供解答和疑難排解建議。
keywords: Analytics 疑難排解
title: 常見問答
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
source-git-commit: 0733884351c64935d9e39c24320d200cc46e6a61
workflow-type: ht
source-wordcount: '840'
ht-degree: 100%

---

# 常見問答

針對 Reports &amp; Analytics 的部分常見問題提供解答和疑難排解建議。如需了解實施作業方面有哪些常見問題，請參閱「實施作業」使用指南中的[常見問題集](/help/implement/faq.md)。

>[!IMPORTANT]
>自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 Reports &amp; Analytics 及其隨附的報告和功能。 Reports &amp; Analytics 及其所有報告和時間表目前都將停止運作。 支援 Reports &amp; Analytics 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。 大部分的 Reports &amp; Analytics 功能都可在 Analysis Workspace 中使用。 自 Analysis Workspace 在 2015 年發佈以來，Reports &amp; Analytics 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。 本通知說明生命週期結束程序。

**我的帳戶遭到鎖定，該如何解鎖？**

若要重新啟用帳戶，請連絡組織內部的管理員。另請參閱 Technotes 使用指南中的 [Adobe Analytics 登入問題疑難排解](/help/technotes/troubleshoot-login.md)。

**為何我確定已確實收集資料，卻仍看到空白報表？**

若要進行報表資料疑難排解，請檢查以下幾項：

* 檢查所使用的量度：Reports &amp; Analytics 中的部分報表會預設為「收入」。請確認您所檢視的量度與報表相關。
* 檢查日期範圍：有些日期範圍 (尤其是組織資料保留原則以外的日期範圍) 可能不會傳回資料。請確認日期範圍已正確設定。
* 檢查內部 URL 篩選器：有些流量來源報表需等到您正確定義內部 URL 篩選器後才能運作。

**為何導覽功能表中遺漏了某些報表？**

針對功能表中遺漏報表的問題，最常見的原因是權限受限或功能表經過自訂。請連絡組織內部的產品管理員，確認您擁有所有所需維度和量度的存取權，且報表套裝的功能表結構並未經過自訂。

**為何有些長度較長的值遭到截斷？**

Adobe Analytics 絕大多數的變數都有字元限制。「頁面名稱」的字元限制為 100 個，自訂轉換變數 (eVar) 則以 255 個字元為上限。Adobe 建議，傳送至 Adobe 的值務必簡明扼要，以避免截斷。

**為何報表會嚴重延遲？**

即時報表可在數分鐘內提供某些流量量度的資料，而轉換和其他需密集處理的資料通常可在 30 至 90 分鐘內提供。雖然 Experience Cloud 平台十分健全，但偶爾仍可能發生報表延遲的情形。這類延遲稱為報表延遲。如需詳細資訊，請參閱 Technotes 使用指南中的[延遲](/help/technotes/latency.md)。

**為何無法在 iPhone 上看到裝置版本？**

Apple 裝置會在使用者代理程式字串中顯示其韌體版本，而非裝置版本。查看 Adobe Analytics 的可用資訊難以判斷 iPhone 裝置版本。如需詳細資訊，請參閱 Analytics 知識庫的[比較 iPhone 裝置版本](https://helpx.adobe.com/tw/analytics/kb/comparing-iphone-device-versions.html)。

**為何加總所有值時，報表底部的總計並不相符？**

維度項目常會套用至多個位置，例如跨夜的瀏覽活動，或同一訂單的多項產品。維度項目會統計所有適用條列項目的數據，但報表的總計欄會刪除重複的值。如需詳細資訊，請參閱 Analytics 知識庫中的[比較條列項目的總合和報表總計](https://helpx.adobe.com/tw/analytics/kb/sum-line-items-different-from-total.html)。

**如何在報表套裝中排除特定 IP 位址的資料？**

您可以在報表中消除內部網站活動的資料，例如網站測試和員工使用情形。此功能可讓您和您的同事瀏覽網站，但不影響流量資料的準確度。如需詳細資訊，請參閱「管理員」使用指南中的[依 IP 位址排除](/help/admin/admin/exclude-ip.md)。

**我可以刪除報表套裝嗎？**

您無法刪除報表套裝。不過，您可以在 Adobe Analytics 的所有檢視中隱藏報表套裝。請注意，傳送至隱藏報表套裝的伺服器呼叫，仍會計入您每月的合約上限。如需詳細資訊，請參閱「管理員」使用指南中的[隱藏報表套裝](/help/admin/company/c-hide-report-suites.md)。

**使用區段時，應使用哪個容器？頁面檢視、瀏覽，還是訪客？**

您應使用的區段容器取決於您擷取資料的範圍。頁面檢視容器只會顯示符合區段條件的點擊，此容器適合用來篩選掉不相關的瀏覽。瀏覽容器會鎖定有一或多個點擊符合區段條件的瀏覽，顯示其中包含的所有點擊，此容器適合用來查看一般工作階段的資訊。訪客容器會顯示有一個點擊符合區段條件的所有瀏覽，此容器適合用來查看訪客。您可以選擇以分析人員的身分，判斷最適合使用的區段容器。如需詳細資訊，請參閱「元件」使用指南中的[區段概觀](/help/components/segmentation/seg-overview.md)。

**為何資料倉儲未顯示我的區段？**

由於資料倉儲具有獨特的處理架構，平台無法以最佳方式處理某些類型的資料，例如路徑分析。如需詳細資訊，請參閱「元件」使用指南中的[資料倉儲區段相容性](/help/components/segmentation/seg-reference/seg-compatibility.md)。
