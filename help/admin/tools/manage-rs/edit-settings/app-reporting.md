---
description: 啟用用於行動應用程式追蹤的維度和量度。
title: 應用程式報告
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

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

下列為可使用的度量:

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
* 追蹤藍牙信標 (UUID、主要、次要及鄰近地區)。

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

下列為可使用的度量:

* [!UICONTROL 語音結束工作階段]
* [!UICONTROL 語音錯誤]
* [!UICONTROL 語音語音]

## 背景點選數的舊式報表和歸因

舊版報表表示應用程式在背景時產生的點選會被視為一般的前景點選。 它們會顯示在報表中並影響歸因。 此舊版設定通常用於維持與舊版實作的一致性。

Adobe建議您停用舊版報表，使背景點選不會顯示。 如果您想在分析中包含背景點選，可以啟用[虛擬報表套裝](/help/components/vrs/vrs-about.md)設定&#x200B;**[!UICONTROL 包含背景點選]**。
