---
title: 如何在 Advertising Analytics 中設定 Advertising 帳戶
description: 可讓您建立新的 Advertising 帳戶，並將多個帳戶對應到多個報表套裝。
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 91%

---

# 設定 Advertising 帳戶

Adobe Analytics 管理員能建立新廣告帳戶，再將多個帳戶對應到多個報表套裝 (1 對 1、1 對多、多對多)。

管理員還可[授權給非管理員](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)，使其得以設定廣告帳戶。

![](assets/aa_accounts.png)

1. 在 Adobe Analytics 中，導覽至&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL Advertising 帳戶」]**。
1. (僅限首次使用) 接受「一般使用者授權合約」的條款。
1. 按一下&#x200B;**[!UICONTROL 「+ 新增」]**。
1. [!UICONTROL 「新增搜尋引擎帳戶」]對話方塊隨即出現：

   ![](assets/aa_new_se_account.png)

1. 依照以下準則填入&#x200B;**[!UICONTROL 「搜尋引擎設定」]**：

   | 設定 | 說明 |
   | --- | --- |
   | 類型 | 您有 2 個選項：Google AdWords 和 Microsoft Bing Ads。注意：Microsoft Bing 已於 2019 年 3 月 31 日併購 Yahoo Gemini，因此 Yahoo Gemini 廣告帳戶選項已無法繼續使用。 |
   | 帳戶名稱 | 您可以選擇將此帳戶名稱設定為任何合適的名稱。這是方便記憶的帳戶名稱，並且會顯示於使用者介面中。 |
   | OAuth 代號 | **注意:** OAuth 是存取權限委派的開放標準，普遍用來授權給網站或應用程式，以便在不提供密碼的情況下，使其得以存取自身在其他網站上的資訊。您將注意到您將被路由到第三方URL(efrontier.com)。 Adobe 使用 efrontier 來推動這三個搜尋引擎的 OAuth 驗證程序。如果使用Internet Explorer 11（或更早版本），則無法成功檢索三個搜索引擎中任何一個的Oauth令牌。 請改用其他網頁瀏覽器。<p>按一下&#x200B;**[!UICONTROL 「擷取代碼」]**，隨即啟動 OAuth2 驗證程序。系統將要求您使用您的憑據登錄您的Google/必應搜索帳戶。 依您選擇的搜尋引擎不同，操作程序會有些微差異： <ul><li>Google廣告：提供Google帳戶ID</li><li>Microsoft Bing：提供 Bing 帳戶 ID 和 Bing 客戶 ID。</li></ul>如需這些 ID 的相關資訊，請參閱[尋找您的帳戶 ID](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md)。成功登錄後， **[!UICONTROL OAuth令牌]** 欄位顯示 **[!UICONTROL 已檢索]**。 |

1. 在&#x200B;**[!UICONTROL 「追蹤」]**&#x200B;區段，您可以提供 Adobe Analytics 實施作業如何追蹤搜尋引擎資料的相關資訊。這是以搜尋引擎資料適度增加 Adobe Analytics 資料的必要步驟。依照以下準則填入&#x200B;**[!UICONTROL 「追蹤設定」]**：

   | 設定 | 說明 |
   | --- | --- |
   | 類型 | <ul><li>**自動：**&#x200B;讓 Advertising Cloud 引擎決定如何將追蹤參數附加到搜尋引擎的追蹤範本/目的地 URL。這是最簡單的方法，但可能不會產生最佳的整合資料集。<br>**重要：**&#x200B;若要在「自動模式」中設定搜尋引擎帳戶，您必須執行下列動作：<br>-「s_kwcid」參數和值將新增至要新增之帳戶中的帳戶追蹤範本或登陸頁面 URL。參數和值會插入 URL 末端。因此，如果您的網站伺服器在 URL 末端需要某個索引鍵/值組，或是需要更新以支援 URL 中的任何新索引鍵/值組，您可能需要執行額外的動作。**注意：**&#x200B;進一步瞭解您是否應將此參數新增至您的[內容安全性原則](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html)。<br>- 此外，關鍵字可以作為 &quot;S_kwcid&quot; 值的一部分，插入至著陸 URL 中，因此若關鍵字中包含特殊字元或符號，請確認您的網站伺服器可以支援這些字元 (常見特殊字元的範例為「+」，用於「加上廣泛比對修飾符」的關鍵字中)。</li><li>**手動：**&#x200B;讓您管理如何將追蹤參數新增到搜尋引擎的追蹤範本/目的地 URL。[如需各個搜尋引擎的相關資訊，請參閱這些手動追蹤範例](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md)。</li></ul> |

1. 在&#x200B;**[!UICONTROL 「對應」]**&#x200B;區段，您可以選擇要與這個搜尋引擎帳戶相連結的報表套裝。在儲存 Advertising 帳戶之前，您必須先提供至少一個報表套裝。您可以將多個帳戶對應到多個報表套裝 (1 對 1、1 對多、多對多)。請注意，系統只會將 AMO 從搜尋引擎提取的資料複製到任何對應的報表套裝，因此資料不會遭到分割。

   >[!IMPORTANT]
   >
   >只有對應至 Experience Cloud 組織的報表套裝才可供選取。 如果畫面並未列出您的報表套裝，請參閱[疑難排解 Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)。

   依照以下準則進行&#x200B;**[!UICONTROL 「對應設定」]**：

   | 設定 | 說明 |
   | --- | --- |
   | 報表套裝映射 | 報表套裝對應決定與此搜尋引擎帳戶相連結的報表套裝。換句話說，這會決定要將搜尋引擎資料傳送到哪些報表套裝中。 |


1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 儲存後，免責聲明會顯示一系列警語。系統會要求確認您已閱讀合約並了解其中的條款。按一下核取方塊，再按一下&#x200B;**[!UICONTROL 「確定」]**。

   此時，系統會將您導向 Advertising 帳戶[管理使用者介面](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)，而新建立的帳戶應該會列示在其中。

>[!NOTE]
>
>搜尋引擎資料會在 24 小時之後開始填入 Analytics 報表，請耐心等候。
