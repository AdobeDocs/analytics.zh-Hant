---
description: 'Data connectors DFA 整合在啟動之後，將可為您的 Adobe Analytics 報表提供下列量度 '
keywords: DFA
title: 整合功能
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 整合功能{#integration-features}

Data connectors DFA 整合在啟動之後，將可為您的 Adobe Analytics 報表提供下列量度:

* 閱覽
* DFA 點按
* 曝光數
* (可選) DFA 成本資料
* (可選) DFA 查詢錯誤、逾時

> [!NOTE] 此整合不支援點按追蹤器（先前稱為點按命令）。 點按追蹤可用來記錄對網站上的文字連結、電子郵件訊息中的連結或其他硬式編碼元素的點按次數。

Data connectors DFA 整合會自動從 DFA 所傳回的資料建構 DFA 追蹤代碼。所建構的這些追蹤代碼，會用來唯一識別廣告及其相關聯的版面和創作。以下將根據整合的版本概述追蹤代碼的結構。1.5 版顯示如下:

![](assets/DFA_id_struct1_5.png)

2.0 版顯示如下:

![](assets/DFA_id_struct2.png)

這些 ID 會作為 Genesis 與 DFA 之間的共用索引鍵，為分類和量度產生正確的關聯。

| 網站 ID | 廣告所在的第三方網站。「網站名稱」分類會提供此網站 ID 的敘述性名稱。 |
|---|---|
| 廣告 ID | 傳送給使用者之商業訊息的 ID。「廣告名稱」分類包含您的組織在 DFA 系統中定義的廣告名稱。例如: `Hybrid Coup Textlink - Build`. |
| 版面 ID | 代表您在其中購買了廣告空間的網站、網站的某部分或網站群組的 DFA 帳戶。 |
| 創作 ID | 預計要對訪客顯示的影像、Flash SWF 或其他資源。「創作名稱」分類包含您在 DFA 介面中提供給此創作的名稱。 |

另外兩個分類，即傳送工具 (DoubleClick for Advertisers) 和管道 (橫幅廣告)，針對任何的 DFA 促銷活動都具有相同的值，有助於區分 DFA 匯入的資料。

## SearchCenter 重複資料刪除 {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

Adobe SearchCenter 現在已可辨識 DFA 整合。透過「資料連接器」精靈啟用SearchCenter重複資料消除，搜尋導向的訪客將不會從DFA的Floodlight伺服器提取資料，而且 *`s.campaign`* DFA將不會填入資料，因此SearchCenter可以填入資料。 此外，DFA 和 SearchCenter 現在會將重複資料刪除值填入每項產品的變數中。

下列清單列出啟用 SearchCenter 重複資料刪除功能時所將啟用的邏輯:

If **[!UICONTROL DFA]** &gt; **[!UICONTROL SearchCenter deduplication]** is selected in the wizard:

* 若是DFA點進，整合會將字串「DFA點進」填入設定的SCM eVar。
* 若是DFA檢視，整合會將字串「DFA檢視」填入SCM eVar。

If **[!UICONTROL SearchCenter]** &gt; **[!UICONTROL DFA deduplication]** is selected in the wizard:

* 若是DFA檢視，整合會將字串「DFA檢視」填入SCM eVar。

> [!NOTE] 如果啟用SearchCenter &gt; DFA重複資料消除，並設定SearchCenter查詢字串參數，則不會將瀏覽視為DFA處理。 這表示，SearchCenter 查詢字串參數應不同於 DFA 點進參數，且不應有「顯示」廣告設定 SearchCenter 查詢字串參數。

