---
title: 品牌可見度整合
description: 將Brand Visibility與Adobe Analytics整合
role: User
source-git-commit: 8a2a4637f21bbbe02ea88292d2ca503f4c667ebc
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 1%
---

# Adobe Brand Visibility整合

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hant/docs/llm-optimizer/using/home)是Generative Engine Optimization的創作AI優先應用程式，旨在協助品牌在AI驅動的搜尋環境中提升其可見度、精確度和影響力。 品牌可見度可提供AI產生之答案中品牌存在感的深入分析、提供規範性內容建議，並將最佳化修正作業自動化。

AI已成為主要探索管道。 大型語言模型(LLM)代理程式（例如ChatGPT、Claude、Copilot和Perplexity）會抓取品牌內容。

>[!NOTE]
>
>品牌可見度先前稱為&#x200B;**LLM Optimizer (LLMO)**。 在轉換期間，部分Adobe檔案可能會繼續使用舊版的LLMO術語。


>[!PREREQUISITES]
>
>您必須布建品牌可見度付費方案，並透過受管理的聯結器連線至您的Experience Platform設定。


>[!IMPORTANT]
>
>在此整合中，美國會進行一些品牌可見度資料的臨時處理。 資料最終會儲存在您的Adobe Analytics合約中設定的指定區域。

如果您使用Customer Journey Analytics，更豐富的獨立輸入整合會透過Adobe Experience Platform將相同的基礎CDN流量資料帶入Customer Journey Analytics。 該整合功能將於今日推出。 檢視[與Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/integrations/bv)的品牌可見度整合。 如果您有Customer Journey Analytics，請先檢閱該整合，因為它會公開更多欄位，並支援將品牌可見度資料與其他資料集聯結。 本指南中說明的Analytics整合是針對使用Adobe Analytics但無法存取或取得Customer Journey Analytics授權的客戶所設計。


## 使用案例

您可以透過兩種方式從Adobe Analytics和Brand Visibility之間的整合獲益：

* **傳入整合**：使用Adobe Analytics中的品牌可見度資料，搭配現有的網頁和行動資料測量LLM導向的流量（機器人爬蟲、RAG請求、代理程式活動）。 例如，您可以：

  * 透過代理程式來源與傳統管道一起測量LLM驅動流量。

  * 識別LLM大量使用但在人工轉換中表現不佳的內容。

  * 偵測LLM-agent請求在關鍵路徑上失敗的位置。

  * 在URL和主機層級，比較頁面的LLM機器人需求與網頁資料中的轉換和收入。

* **輸出整合**：將Adobe Analytics效能資料傳送至Brand Visibility，如此一來，您便可以最佳化LLM來源的AI可見性，這些來源會傳送您有價值的流量，例如ChatGPT或Perplexity。 例如，您可以：

  * 檢視哪些LLM來源會傳送繼續轉換或產生收入的人類訪客。 Adobe Analytics會從參照的網路流量（而非機器人資料集）測量這項資訊。
  * 根據LLM來源所傳送之訪客的下游值來排名，然後將您的AI可見度工作集中在績效最佳的來源上。


## 傳入整合

本節說明&#x200B;**→Adobe Analytics**&#x200B;傳入整合的先決條件和設定步驟。


輸入Adobe Analytics聯結器是透過&#x200B;**報告套裝管理員**&#x200B;為每個報告套裝設定的，如第6節所述。

>[!PREREQUISITES]
>
>在啟用Adobe Brand Visibility聯結器之前，每個品牌可見度網站的CDN存取記錄檔必須已轉送至Adobe Analytics並由接收→品牌可見度。
>
>此要求適用於&#x200B;**每個品牌可見度網站**。 除非Adobe確認涵蓋範圍，否則不應假設一個網站、網域或子網域的CDN設定或記錄摘要涵蓋另一個網站。
>
>
>在啟用聯結器之前，請確認：
>
>1. 相關的CDN或記錄管道已設定為將所需的存取記錄轉送至Adobe提供的目的地。
>1. 品牌可見度已確認收到並偵測到相關網站的記錄。
>1. 資料會顯示在該網站的品牌可見度代理流量控制面板中。
>
>BYOCDN記錄轉送提供用於代理流量分析的伺服器端CDN要求資料。 資料並不取決於瀏覽器中執行的JavaScript標籤。 若沒有必要的CDN記錄摘要，聯結器將沒有流量資料可匯入您的報表套裝。
>
>如需詳細資訊，請參閱[BYOCDN記錄檔轉送參考](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)。


>[!IMPORTANT]
>
>在此整合中，美國會進行一些品牌可見度資料的臨時處理。 資料最終會儲存在您的Adobe Analytics合約中設定的指定區域。


### 運作方式

Adobe Analytics整合→傳入品牌可見度會新增一組&#x200B;**保留變數**&#x200B;至您的報表套裝。 這些變數攜帶有關在網站上偵測到的機器人和自動化代理程式流量的摘要層級資料，包括LLM型流量，這些流量來自[必要條件](#inbound-integration)中所述的相同CDN存取記錄檔。

此流量通常不會執行瀏覽器JavaScript標籤，也不會透過您現有的Adobe Analytics實作來擷取。 保留的變數可讓您在您已用於網站的相同報表套裝中檢視此流量。

聯結器啟用時，會新增下列保留變數：

| 回報為 | 類型 | 附註 |
|---|---|---|
| URL | 維度 | 與請求相關聯的頁面URL。 |
| 機器人類型 | 維度 | 發出請求的機器人或自動化代理程式型別（例如，命名的AI爬蟲）。 |
| 使用者代理 | 維度 | 機器人或代理程式報告的使用者代理字串。 |
| 狀態 | 維度 | 針對請求傳回的HTTP狀態代碼。 |
| Referer | 維度 | 請求的HTTP參照值（若存在）。 |
| 請求 | 量度 | 機器人和代理程式CDN要求的計數。 |


#### 比較Customer Journey Analytics的涵蓋範圍

CJA輸入整合建置在更廣泛的CDN請求摘要資料集上，並支援其他欄位（例如主機和CDN提供者）以及與Customer Journey Analytics中的其他資料集結合。 Adobe Analytics整合是一組較小的報表套裝原生保留變數，旨在搭配Analytics的現有資料模型運作。 如果您的報告需求超出上述欄位，請評估CJA整合。

#### 重要限制

- 不包含訪客ID、ECID、造訪或不重複使用者資料。 這是彙總、非訪客相關的摘要資料。
- 保留的變數不支援配置型別或到期型別設定，因為它們未繫結至訪客。
- 無法像在Customer Journey Analytics中一樣將資料與其他Analytics資料集或維度連結。
- 使用&#x200B;**要求**&#x200B;量度來測量機器人和代理程式流量。 請勿將其與報表套裝中其他位置的造訪或點選型量度互換使用。

聯結器啟用後，應針對報表套裝的變數設定確認確切的可用欄位集。

### 責任

傳入聯結器的設定和組態會同時為[Adobe](#adobe-managed-responsibilities)和[您身為客戶](#customer-owned-responsibilities)負責。

#### Adobe管理的責任

1. 偵測並確認每個已上線品牌可見度網站的CDN記錄檔轉送。
2. 在確認BYOCDN記錄轉送後，讓保留的變數可用於布建。
3. 為報告套裝啟用聯結器後，執行90天的回填並持續每小時同步。

#### 客戶擁有的責任

1. 正在為每個網站完成品牌可見度上線和BYOCDN記錄轉送。
2. 在啟用聯結器之前，確認資料顯示在品牌可見度代理流量儀表板中。
3. 選擇每個品牌可見度網站連線的報表套裝（每個報表套裝一個網站）。
4. 透過「報告套裝管理器」啟用聯結器。
5. 建立使用[中列出的保留變數的報表、區段或資料檢視（如果適用）。運作方式](#how-it-works)。

### 開始之前

啟用聯結器前，請確認下列事項：

- 您已為要連線的網站完成Adobe Brand Visibility上線。
- 已為該網站設定並確認BYOCDN記錄轉送（請參閱[先決條件](#inbound-integration)）。
- 資料會顯示在該網站的Adobe Brand Visibility代理流量控制面板中。
- 您知道要將網站連線到哪個報告套裝。

每個Adobe Brand Visibility網站只會連線至一個報表套裝。 如果您想要帶入多個品牌可見度網站的資料，請將每個網站連結至個別的報表套裝。


### 啟用聯結器

聯結器從報告套裝的&#x200B;**編輯設定**&#x200B;功能表開啟或關閉。

若要開啟報表套裝的Adobe Brand Visibility設定：

1. 登入Adobe Analytics。
1. 移至&#x200B;**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**。
1. 選取您要連線的報表套裝。
1. 選取&#x200B;**[!UICONTROL 編輯設定]**。
1. 從內容功能表中，選取&#x200B;**[!UICONTROL Adobe Brand Visibility]**。

提供聯結器：

1. 選取&#x200B;**布建Adobe Brand Visibility Data Connector**。
1. 檢閱將新增至此報表套裝的維度和量度（列於[運作方式](#how-it-works)）。
1. 在&#x200B;**選取Adobe Brand Visibility網站**&#x200B;下，選擇要連線至此報表套裝的網站。 連線後，網站的摘要資料會每小時同步至此報表套裝。
1. 選取&#x200B;**啟用**。

   這些變數一經啟用，即無法從此報表套裝中移除。 啟用聯結器會開始90天的回填，將過去90天的Adobe Brand Visibility資料匯入此報表套裝。

   啟用聯結器之前，請確認您已完成[中所述的步驟。開始之前](#before-you-start)，這包括驗證資料是否已顯示在您的Adobe Brand Visibility代理流量儀表板中。

啟用聯結器後，請留出時間讓初始回填和第一個小時同步完成。 然後確認[中提到的保留變數運作方式](#how-it-works)已填入您的報表套裝中。 請參閱第8節第3步)。

### 停用聯結器

>[!WARNING]
>
>停用聯結器為&#x200B;**不可還原**。 停用將停止每小時同步並刪除此報表套裝的Adobe Brand Visibility歷史資料。

若要停用聯結器：

1. 移至&#x200B;**管理→報表套裝→編輯Adobe Brand Visibility→的設定**。
1. 選取&#x200B;**取消布建Adobe Brand Visibility Data Connector**。
1. 確認列出的Adobe Brand Visibility網站為您要中斷連線的網站。
1. 選取&#x200B;**停用**。
1. 確認警告以進行確認。

如果您只想暫時暫停報告，請勿停用聯結器。 請聯絡您的Adobe客戶團隊，討論在停用之前暫停報告的選項。

### 設定完成條件

確認下列所有專案後，傳入整合即可供報告：

* Adobe Brand Visibility會轉送網站的CDN記錄檔並加以接收。
* 資料會顯示在該網站的Adobe Brand Visibility代理流量控制面板中。
* 聯結器已透過報告套裝管理員針對預期的報告套裝啟用。
* 初始回填和至少每小時同步處理已完成。
* 第4節中的保留變數會在報表中傳回預期值。

### 驗證程式

驗證程式包含下列步驟：

1. 確認品牌可見度網站和CDN記錄檔整備：

   * 確認您計畫連線的確切網站或網域。
   * 確認該網站的CDN記錄檔正在轉送，且品牌可見度已確認接收。
   * 確認該網站的代理流量控制面板中可看見資料。

1. 確認聯結器已啟用：

   1. 移至&#x200B;**管理→報表套裝→編輯目標報表套裝→Adobe Brand Visibility**&#x200B;的設定。
   1. 確認頁面將聯結器顯示為已啟用，並列出已連線的品牌可見度網站。

1. 確認報告中的資料：

   1. 針對連線的報表套裝開啟Analysis Workspace （或您的標準報表工作流程）。
   1. 使用依&#x200B;**機器人型別**&#x200B;劃分的&#x200B;**請求**&#x200B;量度來建置表格或視覺效果。
   1. 確認最近日期範圍的請求數量。
   1. 確認&#x200B;**URL**、**使用者代理程式**、**狀態**&#x200B;和&#x200B;**Referer**&#x200B;維度傳回預期值。

   資料出現的確切時間取決於[啟用聯結器](#enable-the-connector)中所述的回填和同步處理排程。



### 疑難排解

請參閱下列問題以及如何疑難排解這些問題。

| 問題 | 疑難排解 |
|---|---|
| 聯結器將不會啟用，或網站清單是空的。 | 檢查是否：<ul><li>網站的Adobe Brand Visibility上線已完成。</li><li>已設定並確認網站的BYOCDN記錄轉送。</li><li>您使用正確的報表套裝。</li></ul> |
| 聯結器已啟用，但未顯示任何資料。 | 檢查是否： <ul><li>資料會顯示在已連線網站的「代理流量」控制面板中（如果沒有，則問題位於Analytics的上游）。</li><li>初始90天回填的時間已足夠，而且至少每小時同步一次。</li><li> — 報表中選取的日期範圍包含聯結器啟用後的時段。</li></ul> |
| 資料顯示不完整或未預期。 | 檢查是否： <ul><li>報表套裝也不可接收其他品牌可見度網站的資料（每個報表套裝只會連線至一個網站）。</li><li>您正在讀取&#x200B;**請求**&#x200B;量度，而不是計算報表套裝中其他位置的列或點選。</li><li>您檢視的維度符合第4節中的清單；相同報表套裝中無關的evar或事件不屬於此整合。</li></ul> |

>[!MORELIKETHIS]
>
>[品牌可見度/LLMO整合參考](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/integrations/bv)
>[BYOCDN記錄檔轉送參考](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

## 檔案的草稿說明（非出版）

此區段供內部檢閱，發佈前應先移除此區段。

- **使用的Source真實值：**&#x200B;欄位名稱、保留的變數清單，以及「報表套裝管理員」工作流程來源為[AN-468884](https://jira.corp.adobe.com/browse/AN-468884) （David Wardell，截至2026-08-28為「新增」狀態），這比原始檔案請求[AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der Maur， status New)更新且更具體。 Provision/Deprovision畫面的頁面復本整合了2026-08-28年度內部稽核(`2026-08-28-an468884-abv-report-suite-ui-review.md`)的措辭細化，在面對客戶的文字中，將原始票證的「ABV」縮寫取代為「Adobe Brand Visibility」。
- **在發佈之前要調解的欄位集不一致：** AN-449989的原始維度清單為「主機」、「URL/頁面路徑」、「CDN提供者」、「使用者代理程式」和「LLM機器人型別」，以及單一代理程式要求計數量度。 AN-468884的實際保留變數清單為URL、機器人型別、使用者代理、狀態和反向連結，並具有單一請求事件。 主機和CDN提供者在AN-468884中不是以個別的保留變數存在；狀態是新的。 本草稿遵循AN-468884作為引擎票證的權威性，但兩者應與Aaron Kern / David Wardell進行調解，才能最終完成，因為客戶看到的欄位名稱可能不符合客戶團隊使用舊版AN-449989語言所描述的欄位名稱。
- **尚未確認，請勿在發佈的版本中陳述為事實：**
  - 完全相同的正式發行日期。 AN-431416攜帶FixVersion H2 2026 （2026-11-30版本視窗），並且從2026-09-01開始處於「執行」狀態；AN-468884 （保留變數實施）和AN-449989 （本檔案）都是「新」狀態。 直到送出工程後才發佈。
  - 生產環境中保留的eVar是否完全抑制配置型別/到期型別。 2026-08-28年回顧標幟測試報告套裝目前顯示這些evar的「配置」設定為「最近（上一個）」，這可能是需要清除的預設值，而不是確認的最終行為。
  - IMS組織列出ABV網站的LLMO API端點（填入「網站選擇」下拉式清單）和取消布建/停用API在2026-08-26票證評論中仍由Joe Bass擱置。
  - 精確的CJA欄位計數比較。 AN-449989的原始票證聲稱CJA具有「9個額外的維度」和「5個額外的量度」，但其中幾個維度（LLM工作階段貯體、LLM唯一工作階段計數、LLM請求重複計數）在2026-06-18年稽核時未確認存在於已傳送的`cdn-requests-summary`欄位群組中。 此草稿會因此刻意避免引述CJA比較中的特定計數。
  - 此AA路徑的同步步調在此以每小時表示，並符合AN-468884的票證語言（「執行每小時同步」/「每小時同步程式」）。 這尚未針對生產AA資料來源行為和CJA步調一樣進行獨立驗證。


## 傳出整合

本指南僅涵蓋傳入品牌可見度整合，會在Analytics報表套裝中新增機器人和自動代理程式流量資料。 發佈的整合檔案也說明輸出方向，其中提供Analytics效能資料供品牌可見度產品內品牌可見度。 該方向不在本指南的範圍之內。 如需傳出整合的詳細資訊，請參閱[品牌可見度檔案](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/resources/adobe-analytics-integration)。