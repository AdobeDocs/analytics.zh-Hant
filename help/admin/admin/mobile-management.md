---
description: 啟用行動管理會啟用行動解決方案變數，以便用於擷取行動應用程式的生命週期及其他量度。
seo-description: 啟用行動管理會啟用行動解決方案變數，以便用於擷取行動應用程式的生命週期及其他量度。
seo-title: 行動管理
solution: Analytics
title: 行動管理
topic: 管理工具
uuid: d09edf72-bb91-422d-b22 c-7b6971 f228 de
translation-type: tm+mt
source-git-commit: 6184104b5a46242c5973552298964e96ff671d7c

---


# 行動管理

啟用行動管理會啟用行動解決方案變數，以便用於擷取行動應用程式的生命週期及其他量度。

Adobe Analytics 與 Mobile Services 之間的整合

* 讓您從 Mobile Services 共用您的 KPI (關鍵績效指標) 資料至 Adobe Analytics。
* 讓您啟用位置追蹤。
* 在「Analytics &gt; 報表 &gt; 行動應用程式」下方新增報表。
* 增加 25 個全新 Adobe Mobile 分類。
* 增加 5 個全新 Adobe Mobile 量度。
* 增加全新 Adobe Mobile 維度。
* 每 15 分鐘同步資料至 Analytics

**[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理]** &gt; **[!UICONTROL 報表套裝]** &gt; **[!UICONTROL 編輯設定]** &gt; **[!UICONTROL 行動管理]** &gt; **[!UICONTROL 行動應用報表]**」。

## 步驟 1. 啟用 App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

啟用 App Reports v3.0 以測量以下量度:

* **贏取**: 追蹤應用程式下載行銷活動的反向連結 URL。
* **生命週期**: 由每次應用程式啟動時傳送的測量所提供的基礎層級報表。
* **應用程式動作**: 根據應用程式內動作的報表和路徑。
* **期限值**: 使用應用程式 KPI (如購買、廣告檢視次數、視訊結束、社交分享、相片上傳) 了解使用者如何隨時間累加值。
* **計時事件**: 測量關鍵應用程式動作 (例如首次購買前的時間) 之間經過的時間 (應用程式內和總時間)。

## 步驟 2.啟用位置追蹤 {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

啟用位置追蹤讓您可以:

* 追蹤緯度和經度資料並在 Analysis Workspace 和 Mobile Services 中提出相關報表。
* 於 Mobile Services 中辨識、建立和視覺化特定興趣點 (POI)。POI 必須在行動 SDK 設定檔案中加以設定。
* 追蹤藍牙信標 (UUID、主要、次要及鄰近地區)。

## 步驟 3. (可選) 啟用/停用背景點擊數的傳統報表和屬性 {#section_1708BCAA87AA4884986F7532759C5DD4}

啟用背景點擊數 (當應用程式在背景運作時產生的點擊數) 代表這些點擊數被視為一般的前景點擊數。這些點擊數會在一般報表顯示，並會影響屬性。此設定通常僅為了與傳統實作內容保持一致。

相反地，我們建議您將「包含背景點擊次數」加入[虛擬報表套裝](../../components/vrs/vrs-about.md)。這讓您可以看到點擊數，但不會對瀏覽和訪客數量產生不良影響。Mobile classifications are enabled after you enable **[!UICONTROL Mobile Management]** &gt; **[!UICONTROL Mobile Application Reporting]**.

分類用於將值分組，然後依群組級別匯報。 例如，您可以將所有「付費搜尋」促銷活動歸為「流行音樂術語」類別，並匯報此類別中與量度（如「例項」，亦稱為「點進
」）相關的成功，然後轉換為成功事件。

| 分類 | 定義 |
|--- |--- |
| 首次發行日期 | 安裝或重新安裝後首次啟動的日期。MM/DD/YYYY |
| 應用程式 ID | 以下列格式儲存應用程式名稱和版本:   `[AppName] [BundleVersion]`  例如, `myapp 1.1.` |
| 啟動次數 | 應用程式啟動或在背景執行的次數。 |
| 首次使用後間隔天數 | 自首次執行起的天數。 |
| 上次使用後間隔天數 | 距離上次使用的天數。 |
| 小時 | 測量應用程式的啟動時數，並使用 24 小時數字格式。用於時間分界，以判斷尖峰使用時間。 |
| 星期 | 應用程式啟動的工作日數。 |
| 裝置名稱 | 儲存裝置名稱。以逗號分隔的兩位數字串，用以識別裝置。第一個數字通常代表裝置代別，第二個數字通常提供裝置系列的不同成員版本。 |
| 作業系統版本 | OS 版本。 |
| 解析度 | 寬 x 高 (以實際像素表示)。 |
| 期限值 (eVar) | 由 trackLifetimeValue 方法填入。 |
| 贏取來源 |  |
| 贏取媒體 |  |
| 贏取詞彙 |  |
| 贏取內容 |  |
| 贏取名稱 |  |
| 位置 (10 公里以內) | 由 trackLocation 方法填入。 |
| 位置 (100 公尺以內) | 由 trackLocation 方法填入。 |
| 位置 (1 公尺以內) | 由 trackLocation 方法填入。 |
| 興趣點名稱 | 當裝置處於定義地標範圍內時由 trackLocation 方法填入。 |
| 至興趣點中心的距離 | 當裝置處於定義地標範圍內時由 trackLocation 方法填入。 |
| 應用程式內訊息 ID |  |
| 線上應用程式內訊息 |  |
| 推送選擇加入 |  |
| 裝載 ID |  |

