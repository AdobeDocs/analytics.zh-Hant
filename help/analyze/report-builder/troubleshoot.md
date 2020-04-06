---
description: 您可用來最佳化 Report Builder 遞送的方式，以及偶而會發生的錯誤訊息清單。
title: Report Builder 的疑難排解和最佳作法
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Report Builder 的疑難排解和最佳作法

您可用來最佳化 Report Builder 遞送的方式，以及偶而會發生的錯誤訊息清單。

## Report Builder 5.0 使用者和開啟 5.1 活頁簿 {#section_C29898775999453FABB5FB0E098415C8}

Adobe將維度和分類之間的分隔符號從底線字元(_)變更為||. 此變更對於開啟Report Builder v5.1活頁簿且含有分類請求的Report Builder 5.0使用者有相容性影響。 每次開啟v5.1以前版本的活頁簿時，其所有序列化分類請求都會轉換為此格式。

這會造成往後相容問題：轉換為 v5.1 後，如果將活頁簿與 Report Builder v5.0 的使用者共用，該使用者將無法辨識分類請求 (事實上，它會尋找 &quot;_&quot; 而非 v5.1 序列化 &quot;||&quot;）。

在開啟具有分類請求的 ARB v5.1 活頁簿時，您會遇到以下副作用：

* 開啟活頁簿時，畫面出現以下警示訊息：「此活頁簿上次使用 Report Builder v5.1 儲存。此版本的部分功能與本電腦安裝的 Report Builder 版本不相容。強烈建議您升級為最新版 Report Builder，再更新此活頁簿。」
* 如果您以滑鼠右鍵按一下具有分類的ARB請求，Report Builder內容功能表（編輯請求、新增相依請求……）將不會顯示。
* 如果您執行「全部重新整理」、按一下第三個按鈕，或重新整理「請求管理員」表單中的一組請求，分類請求將會執行而無錯誤。 不過，分類值不會寫出來。
* 您仍可以開啟「請求管理員」，然後逐行切換，直到達到正確的請求為止，以編輯請求。
* 如果您編輯請求並保留所有參數相同，然後按一下「完成」，則會正確寫出回應。 事實上，編輯請求可解決問題，因為回應配置參數會重新序列化。 因此，我們有因應措施，雖然這相當耗時。

## Report Builder 中的驗證問題 {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder 需要驗證身分，才能從您的報表套裝中建立資料請求。視您在 [!DNL Analytics] 內的設定或您的網路而定，登入 Report Builder 有時會發生問題。

**無效的登入公司**

當登入公司輸入錯誤或發生網路活動問題時，最常發生此錯誤。 請執行下列動作：

* 檢查登入公司的拼字檢查，以確保沒有錯字或錯誤的空格。
* 請使用相同登入公司來登入 Analytics，以確保登入公司正確無誤。如果無法以這些憑證登入，請聯絡貴公司的管理員以取得正確的登入公司。

**防火牆**

報告建立工具使用埠80和443。 請確定這些埠可透過您組織的防火牆。 請參閱 Adobe 的「內部 IP 位址」，了解其他防火牆排除項目。

## 請求最佳化建議 {#section_33EF919255BF46CD97105D8ACB43573F}

以下因素可能會增加請求複雜度，並導致處理延遲。

**導致遞送延遲的因素**

* 排程的書籤、控制面板和報告建立工具活頁簿太多，只需數小時
* 大約同時排程了太多的「報告建立工具」活頁簿。 當這種情況發生時，報表 API 佇列便會積壓下來。

**可能會減緩活頁簿執行階段效率的因素**

* 分類大幅增加。
* 隨時間增加請求日期範圍。

   **範例**：假設您使用目前的年份設定建立趨勢化請求，並依「日」細分。到了年末，請求所傳回的期間，會多於年初時建立的期間。

   `(January 1 - January 30 versus January 1 - December 31.)`

**導致活頁簿遞送失敗的原因**

活頁簿中複雜的 Excel 公式，特別是涉及日期與時間的公式。

**儲存格傳回 0 (沒有值)**

Excel工作表名稱中的縮寫符號或單引號將導致報告建立工具無法傳回任何值。 （這是Microsoft Excel的限制。）

**個別請求效能**

處理速度可能受下列設定影響：

| 設定 | 更快速的效能 | 效能變慢 |
|--- |--- |--- |
| 劃分項目與劃分順序 | 少數 | 多 |
|  | 範例：若您由 A 到 Z 細分，則 A 的項目數一律少於 Z 的項目數。如果是相反情況，則請求時間可能會大幅增加。 |
| 日期範圍 | 小範圍 | 廣泛範圍 |
| 篩選 | 特定篩選 | 最受歡迎篩選 |
| 粒度 | 彙總 | 每小時<ul><li>每日</li><li>每週</li><li>每月</li><li>每季</li><li>每年</li></ul> |
| 參加項目數 | 小型資料集 | 大型資料集 |


**排程時間**

24 小時期間內的交錯排程 (請參見下表)。將現有的書籤、控制面板和報告建立工具活頁簿排得較近，可能會造成延遲。

在清晨排程更大、更複雜的要求，以便在工作日期間進行手動提取和重新整理。

| 排程時間 | 上午1點-凌晨2點 | 凌晨2點上午7點 | 早上7點下午6時 | 下午6點-午夜 |
|--- |--- |--- |--- |--- |
| 報告建立工具的使用狀況 | 安靜 | 非常忙 | 用戶端使用。<br>在本機重新整理且請求「立即傳送」的使用者數量較多時。<br>此外，請確認當排程的活頁簿逾時之際，API 佇列是否已清除。 | 不忙 |

**逾時**

任何排程的報表都會在四小時後逾時。 系統會再嘗試排程三次，而且可能導致失敗(一般而言，當資料集越大，所需執行時間就會越久)。[!DNL Analytics] 報表與 Report Builder 會顯示下列項目：

* [!DNL Analytics]: **[!UICONTROL Favorites]** > **[!UICONTROL Scheduled Reports]**

* Report Builder: Click **[!UICONTROL Management]** in the [!UICONTROL Add-ins] tab in Excel.

## 錯誤訊息說明 {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

以下是在使用 Report Builder 時偶爾會顯示的錯誤訊息清單。

>[!NOTE] 以下內容只是錯誤訊息的選集，並非完整清單。如需解決錯誤的詳細資訊，請聯絡管理員。

**此功能只適用於已開啟的活頁簿。**

如果Excel中未開啟任何活頁簿（試算表檔案），而您按一下報告建立工具工具列中的其中一個圖示，就會顯示此訊息。 此外，工具列也會停用，直到您開啟試算表為止。 不過，您可以在工具列仍啟用時按一下線上說明圖示，而不會造成此錯誤。

**您必須先退出，[!UICONTROL Request Wizard]才能啟動[!UICONTROL Request Manager]。**

雖然和 [!UICONTROL Request Manager] 在功 [!UICONTROL Request Wizard] 能上是連結的，但在完成或取消中採取的 [!UICONTROL Request Manager] 操作之前，無法開始使用 [!UICONTROL Request Wizard]。

**無任何請求與此範圍相關聯。**

This error message occurs if you click on the [!UICONTROL From Sheet] button in the [!UICONTROL Request Manager] when a cell of the spreadsheet contains no requests.

To identify which cells in the spreadsheet contain requests, click individual requests listed in the table in the [!UICONTROL Request Manager]. 如果請求與儲存格相關聯，在表格中選取請求時，儲存格會反白顯示。

**選擇的範圍無效。請選擇其他範圍。**

如果已選取試算表的儲存格，且已有對應的請求，就會發生此錯誤。 刪除映射至儲存格的請求，或選擇要映射的其他儲存格範圍。

當您要刪除儲存格時，請務必先找出包含請求的儲存格，然後刪除請求，再刪除儲存格（移除列或欄）。

**使用此功能之前，請先退出目前所在的 Excel 儲存格。**

如果您在Excel儲存格 *中處於編輯模式* ，並按一下其中一個「報告建立工具」圖示，則會出現此錯誤訊息。 Excel儲存格中的編輯模式表示已選取儲存格，而游標會出現在儲存格中。 當您直接在Excel頂端的列或列中輸入時，也會處 [!UICONTROL Formula] 於Excel儲存 [!UICONTROL Name Box] 格的編輯模式。

**選擇的範圍與其他請求的範圍相交。請變更您的選擇。**

如果您已將一組儲存格對應至試算表，則會顯示此錯誤。

在新增請求前，要判斷已映射哪些儲存格的一種方式是關閉 [!UICONTROL Request Wizard] 並開啟 [!UICONTROL Request Manager]。 然後，逐一選擇請求摘要表格中列出的項目。 每當您在清單中選取請求時，會反白顯示試算表中包含請求映射的對應儲存格。

這是您在將多個儲存格對應至多個區域之前，應考慮使用反白顯示、列或欄資訊或格式設定樣式來標籤儲存格的原因之一。
