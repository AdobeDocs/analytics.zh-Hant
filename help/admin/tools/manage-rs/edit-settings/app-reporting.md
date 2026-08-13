---
description: 啟用用於行動應用程式追蹤的維度和量度。
title: 應用程式報告
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 543
ht-degree: 11%

---

# 應用程式報告

「應用程式報表」介面可讓您啟用專用於行動應用程式追蹤的生命週期維度和量度。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報告套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 應用程式管理]** > **[!UICONTROL 應用程式報告]**

>[!IMPORTANT]
>
>這些功能一旦啟用，就無法停用。 啟用指定功能後，Analysis Workspace會永久使用其各自的維度和量度。

## [!UICONTROL 應用程式報表]

[!UICONTROL 應用程式報表]維度和量度用於下列用途：

* **贏取**：追蹤應用程式下載行銷活動的反向連結URL。
* **生命週期**：由每次應用程式啟動時傳送的測量所提供的基礎層級報表。
* **應用程式動作**：以應用程式內動作為基礎的報表和路徑。
* **期限值**：使用應用程式KPI （例如購買、廣告檢視次數、視訊結束、社交分享、像片上傳）瞭解使用者如何隨時間累加值。
* **計時事件**：測量關鍵應用程式動作（例如首次購買前的時間）之間經過的時間（應用程式內和總時間）。

啟用[!UICONTROL 應用程式報表]時，可使用下列維度：

* [!UICONTROL 動作名稱] （具有[Entry](/help/components/dimensions/entry-dimensions.md)和[Exit](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 應用程式ID]
* [!UICONTROL 贏取內容]
* [!UICONTROL 贏取Medium]
* [!UICONTROL 贏取名稱]
* [!UICONTROL 贏取Source]
* [!UICONTROL 贏取詞語]
* [!UICONTROL 星期(SDK)]
* [!UICONTROL 首次使用後間隔天數]
* [!UICONTROL 上次使用後間隔天數]
* [!UICONTROL 裝置名稱(SDK)]
* [!UICONTROL 小時(SDK)]
* [!UICONTROL 首次啟動日期]
* [!UICONTROL 啟動次數]
* [!UICONTROL 期限值(evar)]
* [!UICONTROL 作業系統版本(SDK)]
* [!UICONTROL 解析度(SDK)]

可使用下列量度：

* [!UICONTROL 應用程式中的動作時間]
* [!UICONTROL 動作時間總計]
* [!UICONTROL 當機]
* [!UICONTROL 首次啟動]
* [!UICONTROL 啟動]
* [!UICONTROL 期限值 (事件)]
* [!UICONTROL 工作階段長度總計]
* [!UICONTROL 升級]

## [!UICONTROL 位置追蹤]

[!UICONTROL 位置追蹤]維度用於下列用途：

* 追蹤經緯度資料
* 識別、建立及視覺化特定地標。 地標必須在行動SDK設定檔案中定義。
* 追蹤藍芽信標（UUID、主要、次要和近似程度）。

啟用[!UICONTROL 位置追蹤]時，可使用下列維度：

* [!UICONTROL 主要信標] （具有[Entry](/help/components/dimensions/entry-dimensions.md)和[Exit](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 次要信標] （具有[Entry](/help/components/dimensions/entry-dimensions.md)和[Exit](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 鄰近地區信標] （具有[進入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 信標UUID] （具有[Entry](/help/components/dimensions/entry-dimensions.md)和[Exit](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 位置 (10 公里以內)]
* [!UICONTROL 位置 (100 公尺以內)]
* [!UICONTROL 位置 (1 公尺以內)]
* [!UICONTROL 興趣點名稱]
* [!UICONTROL 至興趣點中心的距離]
* [!UICONTROL 興趣點ID]

## [!UICONTROL 語音和聊天機器人]

[!UICONTROL 語音和聊天機器人]維度和量度可讓您測量語音助理，例如Alexa或Google首頁。 它也能讓您測量本土的聊天機器人。 測量屬性包括：

* **生命週期**：任何應用程式的基礎層級報表，例如啟動次數和平台型別。
* **交談**：測量與交談相關的意圖、回應及其他量度和維度。

當您啟用[!UICONTROL 語音和聊天機器人]時，下列維度可供使用：

* [!UICONTROL 語音裝置功能] （具有[進入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)維度）
* [!UICONTROL 語音驗證]
* [!UICONTROL 語音錯誤型別]
* [!UICONTROL 語音色彩比對方式]
* [!UICONTROL 語音應用程式回應]
* [!UICONTROL 語音語言]

可使用下列量度：

* [!UICONTROL 語音結束工作階段]
* [!UICONTROL 語音錯誤]
* [!UICONTROL 語音語音]

## 背景點按數的舊式報告和歸因

舊版報表表示應用程式在背景時產生的點選會被視為一般的前景點選。 它們會顯示在報表中並影響歸因。 此舊版設定通常用於維持與舊版實作的一致性。

Adobe建議您停用舊版報表，使背景點選不會顯示。 如果您想在分析中包含背景點選，可以啟用[虛擬報表套裝](/help/components/vrs/vrs-about.md)設定&#x200B;**[!UICONTROL 包含背景點選]**。
