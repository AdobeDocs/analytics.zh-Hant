---
description: 瞭解如何最佳化Report Builder傳送，以及可能發生的錯誤訊息清單。
title: Report Builder 的疑難排解和最佳作法
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 85%

---

# Report Builder 的疑難排解和最佳作法

{{legacy-arb}}

本文介紹可用來最佳化Report Builder的疑難排解和最佳做法。 其中也包含可能顯示的錯誤訊息清單。

## Report Builder 5.0 用戶和開啟 5.1 活頁簿 {#section_C29898775999453FABB5FB0E098415C8}

Adobe 將維度和分類間的分隔符號從底線字元 (_) 變更為 ||。此項變更是為了讓 Report Builder 5.0 用戶在開啟具有分類請求的 Report Builder v5.1 活頁簿時能夠相容。每次開啟 v5.1 之前版本的活頁簿時，其中的所有序列化分類請求都會轉換為這個格式。

這會造成往後相容問題：轉換為 v5.1 後，如果將活頁簿與 Report Builder v5.0 的用戶共用，該用戶將無法辨識分類請求 (事實上，它會尋找 &quot;_&quot; 而非 v5.1 序列化 &quot;||&quot;)。

在開啟具有分類請求的 ARB v5.1 活頁簿時，您會遇到以下副作用：

* 開啟活頁簿時，畫面出現以下警示訊息：「此活頁簿上次使用 Report Builder v5.1 儲存。此版本的部分功能與本電腦安裝的 Report Builder 版本不相容。強烈建議您升級為最新版 Report Builder，再更新此活頁簿。」
* 如果您以滑鼠右鍵按一下具分類的 ARB 請求，不會顯示 Report Builder 快顯功能表 (編輯請求、新增相依請求...)。
* 如果透過按一下第三個按鈕或重新整理「請求管理員」表單中的一組請求，來執行「重新整理所有」，分類請求可以順利執行，不會發生錯誤。但是，無法寫出分類值。
* 您仍然可以編輯請求，方法是開啟「請求管理員」，接著一列一列往下，直到到達正確的請求。
* 如果您編輯請求並將所有參數保持不變，接著按一下「完成」，就能正確寫出回應。編輯請求可以解決問題，是因為會重新序列化「回應配置」參數。所以此問題有解決辦法，只是較為耗時。

## Report Builder 中的驗證問題 {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder 需要驗證身分，才能從您的報表套裝中建立資料請求。視您在[!DNL Analytics]內的設定或您的網路而定，登入Report Builder有時會發生問題。

* **無效的登入公司**：此錯誤最常發生在登入公司輸入不正確，或網路活動發生問題時。 請執行下列動作：
   * 檢查登入公司拼字，確定沒有打錯字或錯誤空格。
   * 請使用相同登入公司來登入 Analytics，以確保登入公司正確無誤。如果無法以這些憑證登入，請聯絡貴公司的管理員以取得正確的登入公司。
* **防火牆**：Report Builder使用連線埠80和443。 請確定已允許這些連接埠通過您組織的防火牆。請參閱 Adobe 的「內部 IP 位址」，了解其他防火牆排除項目。

## 請求最佳化建議 {#section_33EF919255BF46CD97105D8ACB43573F}

以下因素可能會增加請求複雜度，並導致處理延遲。

* **拖慢交付速度的因素**：太多書籤、儀表板和 Report Builder 活頁簿排程在數小時內。此外，還將太多 Report Builder 活頁簿排程幾乎同一時間內完成。當這種情況發生時，報表 API 佇列便會積壓下來。
* **可能會拖慢活頁簿執行階段速度的因素**：分類大幅增加，或隨著時間增加請求日期範圍。
* **導致活頁簿傳送失敗的原因**：活頁簿中複雜的 Excel 公式，尤其是涉及日期和時間的公式。
* **傳回0 （沒有值）的儲存格**： Excel工作表名稱中的撇號或單引號會導致Report Builder沒有傳回值。 (此為 Microsoft Excel 的限制)。
* **個別請求效能**：處理速度可能受下列設定影響：

  | 設定 | 較快的效能 | 較慢的效能 |
  |--- |--- |--- |
  | 劃分項目與劃分順序 | 少數 | 許多 |
  |  | 範例：若您由 A 到 Z 細分，則 A 的項目數一律少於 Z 的項目數。如果是相反情況，則請求時間可能會大幅增加。 |
  | 日期範圍 | 小範圍 | 大範圍 |
  | 篩選 | 特定篩選 | 最受歡迎篩選 |
  | 詳細程度 | 彙總 | 每小時<ul><li>每日</li><li>每週</li><li>每月</li><li>每季</li><li>每年</li></ul> |
  | 項目數 | 小量資料集 | 大量資料集 |

* **排程時間**：24 小時期間內的交錯排程 (請參見下表)。將現有書籤、儀表板及 Report Builder 活頁簿排得太接近，可能會引發延遲。在凌晨時排定較大、較複雜的請求，以允許在營業日進行手動提取與重新整理作業。

  | 排程時間 | 早上 1 點 – 早上 2 點 | 早上 2 點 – 早上 7 點 | 早上 7 點 – 下午 6 點 | 下午 6 點 – 午夜 |
  |--- |--- |--- |--- |--- |
  | Report Builder 使用狀況 | 安靜 | 很忙碌 | 用戶端用法。<br>在本機重新整理且請求「立即傳送」的用戶數量較多時。<br>此外，請確認當排程的活頁簿逾時之際，API 佇列是否已清除。 | 不忙碌 |

* **逾時**：任何排程報告在四小時後逾時。 系統會再嘗試排程三次，而且可能導致失敗(一般而言，當資料集越大，所需執行時間就會越久)。[!DNL Analytics] 報表與 Report Builder 會顯示下列項目：

## 範例錯誤訊息說明 {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

本節包含使用Report Builder時可能發生的錯誤訊息清單範例。

>[!NOTE]
>
>這是錯誤訊息的範例，並非完整清單。 如需解決錯誤的詳細資訊，請聯絡管理員。

* **此功能只適用於已開啟的活頁簿。**：如果未在Excel中開啟任何活頁簿（試算表檔案），且您按一下Report Builder工具列中的其中一個圖示，則會顯示此訊息。 此外，工具列將成為停用狀態，直到您開啟試算表為止。然而，在工具列仍為啟用狀態時，您可以按一下線上說明圖示而不致發生此錯誤。
* **您必須先退出[!UICONTROL 「請求精靈」]，才可啟動[!UICONTROL 「請求管理員」]。**：由於「[!UICONTROL 請求管理員]」和「[!UICONTROL 請求精靈]」在功能上是相連的，因此在「[!UICONTROL 請求精靈]」中執行的動作完成或取消之前，您不能操作「[!UICONTROL 請求管理員]」。
* **無任何請求與此範圍相關聯。**：當試算表的儲存格不含任何請求時，如果您按一下「[!UICONTROL 請求管理員]」中的「[!UICONTROL 從工作表]」按鈕，此錯誤訊息便會出現。若要識別試算表中含有請求的儲存格，請在[!UICONTROL 「請求管理員」]中按一下表格列示的個別請求。如果儲存格有相關聯的請求，當您選擇表格中的請求時，系統將會反白顯示儲存格。
* **選擇的範圍無效。請選擇其他範圍。**：當選擇的試算表儲存格已有對應的請求時，此錯誤便會發生。請刪除對應至儲存格的請求，或選擇其他儲存格範圍來進行對應。如果您想要刪除儲存格，請務必先找出含有請求的儲存格並刪除請求，然後再刪除儲存格 (移除列或欄)。
* **使用此功能之前，請先退出目前所在的 Excel 儲存格。**：如果您處於&#x200B;*‭編輯模式*，當您按一下任何 Report Builder 圖示時，此錯誤訊息便會出現。要在 Excel 儲存格內使用編輯模式，您必須先選擇儲存格，且游標位在儲存格內。當您直接在 Excel 頂端的「[!UICONTROL 公式]」列或「[!UICONTROL 名稱方塊]」中輸入文字時，也會處於 Excel 儲存格內的編輯模式。
* **選擇的範圍與其他請求的範圍相交。請變更您的選擇。**：如果將一組儲存格對至試算表時，便會顯示此錯誤。
* **修復活頁簿 (已移除記錄：公式來自 /xl/calcChain.xml 部分)**：有時候，在儲存或傳輸活頁簿時，活頁簿的公式會損毀。開啟檔案時，Excel 會嘗試執行這些公式但會失敗。您可以從試算表移除 `calcChain.xml`，強制 Excel 重新整理其公式計算，即可解決此問題。
   1. 將活頁簿的副檔名從 `.xlsx` 重新命名為 `.zip`。
   2. 解壓縮內容並開啟 `/xl/` 檔案夾。
   3. 刪除 `calcChain.xml`。
   4. 重新壓縮內容，並將副檔名變更回 `.xlsx`。
   5. 在 Excel 中開啟活頁簿，並重新整理所有 Report Builder 請求。
* **與輸入篩選器或輸出範圍有關聯的 Excel 儲存格可能已刪除**：Report Builder 會使用 Excel 名稱將資料請求附加至儲存格。如果從「名稱管理員」刪除 Excel 名稱，您會看到此錯誤。 如果刪除 Excel 名稱，則無法復原請求。 如果活頁簿已排定時間，您可以從「排程管理員」下載副本，或開啟先前傳送的活頁簿副本。