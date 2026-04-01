---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 89cc33528d3907d955a543f3e43774a1065e149a
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 40%

---

# Adobe Analytics 目前的發行說明 (2026 年 3 月)

**上次更新日期**：2026年3月11日

以下發行說明涵蓋2026年3月發行期。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新數次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **面板劃分**<br/>&#x200B;面板的拖放區域現在提供額外功能，可[根據維度劃分](/help/analyze/analysis-workspace/c-panels/panels.md#break-down-a-panel) （而非區段）面板。 | 2026年3月31日 | 2026年3月31日 |
| **依多欄排序表格** <br/>您現在可以在Analysis Workspace中依多欄排序自由表格的資料，不論是維度或量度皆然。<p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序進行排序。優先順序編號會顯示在排序圖示旁邊。</p><p>如需詳細資訊，請參閱[篩選和排序自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026年3月4日 <p>（原計畫於2026年2月18日推出）</p> |
| **Report Builder：管理員可看見所有已排程的活頁簿**<br/> Report Builder Excel增益集包含新的篩選選項，可讓管理員檢視指定組織的所有已排程活頁簿，無論排程對象為何。 此篩選選項僅適用於Analytics管理員。 檢視排程活頁簿時，「活頁簿」索引標籤和「舊版」索引標籤都會提供此功能。<p>在分散式團隊間移轉活頁簿時，檢視所有已排程活頁簿的功能特別實用，因為它可讓管理員在移轉活頁簿之前輕鬆找到所有舊版活頁簿。</p><p>以前，管理員只能看到他們排程的活頁簿，看不到其他使用者排程的活頁簿。</p><p>如需詳細資訊，請參閱[受管理的排程活頁簿](/help/analyze/report-builder/manage-schedules-reportbuilder.md)。</p> | | 2026年3月10日 |
| **更新至Approximate Count Distinct函式**<br/> Approximate Count Distinct函式中使用的HLL機率演演算法即將更新。 使用此函式的數字之結果輸出可能會和歷史數字稍有不同，如下所示：</p><ul><li>計算極少量不重複值時，結果將改善為使用精確計數，而不是使用預估值。</li><li>計算任何較大的數字時，計數估計將保持本次更新之前的準確性（估計準確性在準確數字的5%以內，即時間的95%）。</li></ul><p>如需Approximate Count Distinct函式的詳細資訊，請參閱[進階函式](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | 2026年3月10日 |
| **Analysis Workspace的實作教學課程**<br/>&#x200B;現在提供新的實作教學課程，引導新使用者瞭解在Analysis Workspace中使用面板、視覺效果和元件的基本知識。 <p>如需詳細資訊，請參閱[Adobe Analytics登陸頁面](/help/analyze/landing.md)。</p> | | 2026年3月18日 |
| **流失視覺效果改善**<br/>&#x200B;流失視覺效果包含下列增強功能：<ul><li>改善的拖放體驗。<br/>只要將滑鼠指標暫留在接觸點上，並將它拖曳到視覺效果中的新位置即可。<br/>之前，您必須先按一下接觸點上的編輯圖示，才能拖曳它。</li><li>使用拖放結合接觸點時語言更清晰。<br/>將接觸點拖曳到另一個接觸點時，會顯示「合併」文字，表示兩個接觸點正在合併。<br/>先前顯示「新增」文字，無論接觸點是否移至視覺效果內的新位置或與其他接觸點結合。</li><li>重新設計工具提示。<br/>將滑鼠懸停在接觸點上時顯示的工具提示更直覺且清晰易讀。</li><li>更易探索的內容功能表。<br/>工具提示包含新的「按一下以分析」選項，可讓您方便地存取接觸點的內容功能表。<br/>過去，內容功能表只有在以滑鼠右鍵按一下接觸點時才能使用。</li></ul><p>如需詳細資訊，請參閱[設定流失視覺效果](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)。</p> | | 2026年3月25日 |
| **將劃分套用至面板**<br/>&#x200B;您現在可以將劃分套用至面板。 在面板層級套用劃分時，劃分會套用至面板內所有自由表格中的所有欄。 | 2026 年 3 月 | 2026 年 5 月 |
| **串流媒體服務：支援排程資料** <br/>您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤觀看率。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-440336、AN-440216、AN-440121、AN-438445、AN-438216、AN-437856、AN-437776、AN-437765、AN-437365、AN-432793、AN-432094、AN-431557、AN-431200、AN-429621、AN-429424、AN-427973、AN-426089、AN-425883、AN-424359、AN-、AN-
**分類**： AN-440143、AN-439891、AN-439844、AN-438994、AN-438057、AN-438052、AN-437986、AN-437896、AN-435387、AN-435335、AN-435150、AN-433050、AN-432062、AN-431873、AN-429642
**資料摘要和Data Warehouse**：AN-439441、AN-437086、AN-433064、AN-432121、AN-431755、AN-428239、AN-427049、AN-425036、AN-424972、AN-423509、AN-335417、AN-283958、AN-256948
**移轉**：
**匯出**： AN-432030
**Report Builder**： AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**報告**： AN-434545、AN-431206、AN-428043
**排程報告**：
**分段**：
**Other**： AN-440076、AN-434783、AN-434542、AN-434233、AN-433368、AN-432138、AN-431322、AN-431012、AN-429067、AN-423285


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **直播串流處理改善** | 2026年1月14日 | Adobe計畫改善和變更LiveStream裝載的格式。 這些更新讓LiveStream和其他Adobe Analytics功能（例如Analysis Workspace）之間的對等性更佳。 預覽端點可供您測試計畫的變更。 如需變更的完整清單和預覽端點詳細資訊，請參閱[LiveStream發行說明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe計畫在2026年4月13日將硬式轉換至更新的裝載格式。 |
| **移除TLS 1.2加密套件** | 2026年2月11日 | 管理員須知： Adobe預計於2026年5月27日從Adobe資料收集伺服器上移除下列TLS 1.2加密套裝的支援。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>大部分實施不需要客戶採取任何動作。 這項變更主要影響從使用過時TLS程式庫的舊版原生應用程式傳送的Analytics資料，以及在過時瀏覽器或作業系統上的少數網頁訪客。 移除對這些加密套裝的支援，可增強安全性，並使Adobe符合現代化的加密標準。 目前，不到0.1%的資料收集流量依賴這些加密套件。</p> |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [串流媒體服務發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新
