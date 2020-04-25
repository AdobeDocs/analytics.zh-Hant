---
description: 成功事件是可追蹤的動作。成功事件的條件由您決定。例如，若有訪客購買了一件物品，該購買事件即可被視為成功事件。
keywords: event
title: 成功事件概觀
topic: Admin tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# 成功事件概觀

成功事件是可追蹤的動作。成功事件的條件由您決定。例如，若有訪客購買了一件物品，該購買事件即可被視為成功事件。

存取報表套裝設定中的「成功事件」頁面：

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Click the 9-grid button at the top, then click [!UICONTROL Analytics].
3. Navigate to [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. 選取所要的報表套裝，然後導覽至「 [!UICONTROL 編輯設定] > [!UICONTROL 轉換] > [!UICONTROL 成功事件]」。
5. 找出所要的事件，並將「唯一事 [!UICONTROL 件記錄」下拉式清單修改] 為「每次瀏覽記錄一次 [!UICONTROL 」或「使用] 事件ID 」。

成功事件有多種類型，視您的網站類型而定。這些類型包括：

* **零售**：產品檢視、結帳、購買
* **媒體**：訂閱、競標註冊、頁面檢視、影片檢視
* **金融**：申請書提交、登入、自助服務工具使用
* **旅遊**：預訂 (購買)、內部促銷活動 (點進)、搜尋 (詢價)
* **通訊**：購買、銷售機會、自助服務工具使用
* **高科技**：白皮書下載、RFP、表單填寫、支援要求
* **汽車**：銷售機會提交、要求報價、手冊下載

[s.events](https://marketing.adobe.com/resources/help/zh_TW/sc/implement/events.html) 變數會定義成功事件。

## 成功事件頁面 - 說明 {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 成功事件」]**

「成功事件」頁面可讓您設定在您網站上使用的事件變數。可最多新增 1,000 個成功事件。事件 81-1,000 僅適用於 H22 代碼或更高版本。

| 元素 | 說明 |
|--- |--- |
| Event | 事件的原始名稱。 |
| 名稱 | 提供有意義的名稱給您網站上使用的成功事件。例如，如果 event1 用於追蹤註冊，則可在此處變更名稱，讓 event1 可以在所有「轉換」報告中都顯示為「註冊」量度。 |
| 類型 | 選取的類型將決定該事件是計數器 (標準)、數值或貨幣事件。數值或貨幣事件可讓您新增多個量度。計數器事件是用來即時記錄事件，而貨幣事件則是用來記錄十進位數字，如稅金或運費。傳遞給貨幣事件的值在收到時，會從頁面貨幣轉換為報表套裝的基本貨幣。如需使用貨幣事件的詳細資訊，請聯絡 Adobe 代表。數值事件用於報告非貨幣數量，如訂單中使用的優惠券數量。貨幣事件用於追蹤稅金和運費。用於「資料來源」之「標準」類型的事件必須為數值或貨幣事件。 |
| 極性 | 極性量度可讓您指定當特定自訂事件 (量度) 上升時，Adobe Analytics 是否應該將其視為好事或壞事。這可讓 Adobe Analytics 為各種量度顯示方向指示 (箭頭) 以增加上下文 (例如每過一週的比較)。範例：如果「提交錯誤」每週都上升，Adobe Analytics 應將其視為好事或壞事？電子郵件註冊增加可能是好事。但表單提交錯誤增加可能是壞事。在 Analysis Workspace 中，極性適用於：「自由表格」條件式格式、「摘要變更」視覺效果，以及「地圖」視覺效果的「正/負片」色彩配置。 |
| 說明 | 事件用途與用法的簡短說明。 |
| 獨特事件記錄 | **每次瀏覽記錄一次**:將特定事件與訪客的作業系結。 相同瀏覽中指定事件的後續計數會被忽略。 這類事件序列化不需要任何實作變更。<br>**使用事件ID **:將指定事件系結至自訂ID。 會忽略具有相同事件ID之指定事件的後續計數。 這類事件序列化需要點擊中的自訂ID來去重複化值。 See[Event ID serialization](../../../implement/vars/page-vars/events/event-serialization.md)in the Implement user guide. |
| 參與率 | 請參閱[量度參與率](/help/components/c-variables/c-metrics/metrics-participation.md)。 |
| 警告 (貨幣事件) | 將事件類型變更為貨幣事件或改為不使用貨幣事件時，會顯示訊息，告知歷史資料無法用於報表。不同的事件類型使用不同的資料表格，且無法同時使用。如果使用者回復事件類型，部分歷史資料可加以還原。不過，在初次變更後收集的資料都無法使用。變更事件類型時請謹慎。 |

