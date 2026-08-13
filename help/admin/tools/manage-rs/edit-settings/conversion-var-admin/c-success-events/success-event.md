---
description: 成功事件是可追蹤的動作。 成功事件的條件由您決定。 例如，若有訪客購買了一件物品，該購買事件即可被視為成功事件。
keywords: 事件
title: 成功事件概觀
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
TQID: https://experienceleague.adobe.com/wOWG6t9fsrfkd4FE-BNkwIrPW6DEGxBKDc2XItyRaoc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 962
ht-degree: 35%

---

# 成功事件

成功事件 (也稱為轉換事件或自訂事件) 是可以被追蹤的行動。 成功事件的條件由您決定。 例如，若有訪客購買了一件物品，該購買事件即可被視為成功事件。

如需成功事件的影片概觀，請參閱Analytics教學課程指南中的[轉換事件簡介](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events)。

## 成功事件範例

成功事件種類繁多，端視您的網站型別而定。 這些類型包括：

* **零售**：產品檢視、結帳、購買
* **媒體**：訂閱、競標註冊、頁面檢視、影片檢視
* **金融**：申請書提交、登入、自助服務工具使用
* **旅遊**：預訂 (購買)、內部促銷活動 (點進)、搜尋 (詢價)
* **通訊**：購買、銷售機會、自助服務工具使用
* **高科技**：白皮書下載、RFP、表單填寫、支援要求
* **汽車**：銷售機會提交、要求報價、手冊下載

[s.events](/help/implement/vars/page-vars/events/event-serialization.md)變數會定義成功事件。

## 設定成功事件

您可以設定在您網站上使用的事件變數。 您最多可以新增1,000個成功事件。 事件81至1,000只有在您使用H22程式碼或更高版本時才有作用。

若要設定成功事件：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**。
1. 選取您要設定成功事件的報表套裝。
1. 選取&#x200B;**[!UICONTROL 編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 成功事件]**。

   ![步驟結果](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. 在&#x200B;[!UICONTROL **Event**]&#x200B;欄中，識別您要當作成功事件使用的事件名稱。

1. 在&#x200B;**[!UICONTROL 名稱]**&#x200B;欄中，選取專案旁的核取方塊以啟用編輯，然後指定所要的名稱。

   為您網站上使用的成功事件指定有意義的名稱。 例如，如果event1是用來追蹤註冊，請在此變更名稱，讓event1在所有轉換報表中都會顯示為「註冊」量度。

1. 在&#x200B;**[!UICONTROL 型別]**&#x200B;欄中，選取專案旁的核取方塊以啟用下拉式清單，然後選取所要的型別。

   >[!IMPORTANT]
   >
   >變更事件型別時，請考量下列事項：<ul><li>您可以變更計數器與數值之間的事件型別，而不會失去先前擷取資料的存取權。</li><li>將事件型別變更為貨幣事件或改為不使用貨幣事件時，會顯示訊息，指出歷史資料無法用於報表。 不同的事件型別使用不同的資料表，而且不能同時使用。 如果使用者還原事件型別，則可以還原某些歷史資料。 不過，初始變更後收集的任何資料都無法使用。</li></ul>

   您選取的型別會決定事件是計數器（標準）、數值或貨幣事件。 <p>計數器事件可用來及時記錄事件。</p><p>數值事件用於報告非貨幣數字，例如訂單中使用的優惠券數目。</p> <p>貨幣事件會記錄小數位數，如稅金或運費。 傳遞給貨幣事件的值會在收到後從頁面貨幣轉換為報表套裝的基本貨幣。 貨幣事件可用來追蹤稅捐與運費。 如需使用貨幣事件的詳細資訊，請聯絡Adobe代表。<p>數值和貨幣事件可讓您新增多個量度。</p><p>在標準型別的資料來源中使用的事件必須是數值或貨幣事件。</p>

1. 在&#x200B;**[!UICONTROL 極性]**&#x200B;欄中，選取核取方塊，然後從下拉式功能表中選擇此量度的趨勢上升是好事或壞事。

   這可讓您指示Adobe Analytics將給定的自訂事件（量度）上升的情況視為好事或壞事。 它會啟用各種度量的方向指示（箭頭）來新增上下文（例如每過一週的比較）。  範例：如果「提交錯誤」每週都上升，Adobe Analytics 應將其視為好事或壞事？ 電子郵件註冊增加可能是好事。 但表單提交錯誤增加可能是壞事。  在 Analysis Workspace 中，極性適用於：「自由格式表格」條件式格式、「摘要變更」視覺效果，以及「地圖」視覺效果的「正/負片」色彩配置。

1. 在「**[!UICONTROL 可見性]**」欄中，選取核取方塊，然後從下拉式功能表中選擇是否要隱藏「功能表」、「量度選擇器」、「計算量度產生器」和「區段產生器」中的標準（內建）量度、自訂事件和內建事件。

   此設定不會影響該量度或事件的資料彙集作業，只會影響其使用者介面的可見性，如下所示：

   有以下設定可使用：

   | 設定 | 顯示於 | 在中不可見 |
   |---------|----------|---------|
   | [!UICONTROL **隨處可見**] | <ul><li>Analysis Workspace</li><li>區段產生器</li><li>計算量度產生器</li></ul> | 不適用 |
   | [!UICONTROL **建置器**] | <ul><li>區段產生器</li><li>計算量度產生器</li><li>Analysis Workspace</li></ul> |  |
   | [!UICONTROL **隨處隱藏**] | 不適用 | <ul><li>Analysis Workspace</li><li>區段產生器</li><li>計算量度產生器</li></ul> |

1. 在&#x200B;[!UICONTROL **Description**]&#x200B;欄中，選取核取方塊，然後提供說明。
1. 在「[!UICONTROL **獨特事件記錄**]」欄中，選取核取方塊，然後從下拉式功能表選擇是否一律記錄事件。

   提供下列選項：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **每次造訪記錄一次**] | 繫結特定事件和訪客的工作階段。 同一次瀏覽中，特定事件的後續計數會被忽略。 就這類事件序列化而言，實施上不需任何變更。 |
   | [!UICONTROL **使用事件ID**] | 繫結特定事件和自訂ID。 擁有相同事件 ID 之特定事件的後續計數會被忽略。 在這類事件序列化作業中，需使用點擊中的自訂 ID 刪除重複數值。 請參閱實施使用手冊中的[事件 ID 序列化](/help/implement/vars/page-vars/events/event-serialization.md)。 |

1. 在&#x200B;[!UICONTROL **參與率**]&#x200B;欄中，選取核取方塊，然後選擇啟用或停用參與率。 啟用後，系統會為造訪的所有維度專案給予滿分的歸因評分。

   >[!NOTE]
   >
   >您可以啟用的參與率最多可達 100 個自訂事件。 除此之外，您還可在[計算量度](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)產生器中建立參與率量度。

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。
