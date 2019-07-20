---
seo-title: 設定廣告帳戶
title: 設定廣告帳戶
uuid: 4e37caa3-e4 a5-43ad-97c0-12db62 ad5283
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# 設定廣告帳戶

Adobe Analytics 管理員能建立新廣告帳戶，再將多個帳戶對應到多個報表套裝 (1 對 1、1 對多、多對多)。

管理員還可[授權給非管理員](../../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)，使其得以設定廣告帳戶。

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. (僅限首次使用) 接受「一般使用者授權合約」的條款。
1. Click **[!UICONTROL + Add]**.
1. [!UICONTROL 「新增搜尋引擎帳戶」]對話方塊隨即出現:

   ![](assets/aa_new_se_account.png)

1. 依照以下準則填入&#x200B;**[!UICONTROL 「搜尋引擎設定」]:**

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> <p>您有個選項：Google AdWords和Microsoft Bing廣告。 </p> <p>注意: Microsoft Bing 已於 2019 年 3 月 31 日併購 Yahoo Gemini，因此 Yahoo Gemini 廣告帳戶選項已無法繼續使用。  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>帳戶名稱 </p> </td> 
      <td colname="col2"> <p>您可以選擇將此帳戶名稱設定為任何合適的名稱。這是方便記憶的帳戶名稱，並且會顯示於使用者介面中。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>OAuth 代號 </p> </td> 
      <td colname="col2"> <p>注意: OAuth 是存取權限委派的開放標準，普遍用來授權給網站或應用程式，以便在不提供密碼的情況下，使其得以存取自身在其他網站上的資訊。 </p> <p>注意: 您將發現自己已經重新導向至協力廠商 URL (efrontier.com)。Adobe 使用 efrontier 來推動這三個搜尋引擎的 OAuth 驗證程序。 </p> <p>注意: 如果您使用 Internet Explorer 11 (或更早版本)，將無法成功擷取這三個搜尋引擎的 Oauth 代號。請改用其他網頁瀏覽器。 </p> <p>按一下<span class="uicontrol">「擷取代碼」</span>，隨即啟動 OAuth2 驗證程序。也就是說，系統會詢問您是否要使用自己的憑證登入 Google/Bing 搜尋帳戶。依您選擇的搜尋引擎不同，操作程序會有些微差異: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: 提供 Google 帳戶 ID。 </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: 提供 Bing 帳戶 ID 和 Bing 客戶 ID。 </li> 
        </ul> <p>如需這些 ID 的相關資訊，請參閱<a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md#concept_F7F67448F3B44342967E0419E96F384D" format="dita" scope="local">尋找您的帳戶 ID</a> 以取得這些 ID 的相關資訊。 </p> <p>成功登入後，OAuth Token欄位將會顯示 
        <systemoutput>
          已擷取
        </systemoutput>實施流量分類。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 在&#x200B;**[!UICONTROL 「追蹤」]區段，您可以提供 Adobe Analytics 實作如何追蹤搜尋引擎資料的相關資訊。**&#x200B;這是以搜尋引擎資料適度增加 Adobe Analytics 資料的必要步驟。依照以下準則填入&#x200B;**[!UICONTROL 「追蹤設定」]:**

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol">自動</span>: 讓 Advertising Cloud 引擎決定如何將追蹤參數附加到搜尋引擎的追蹤範本/目的地 URL。這是最簡單的方法，但可能不會產生最佳的整合資料集。 <p>重要: 若要在「自動模式」中設定搜尋引擎帳戶，您必須執行以下動作: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">「S_kwcid」參數和值會新增至帳戶中的帳戶追蹤範本或登陸頁面 URL。參數和值會插入 URL 末端。因此，如果您的網站伺服器在 URL 末端需要某個索引鍵/值組，或是需要更新以支援 URL 中的任何新索引鍵/值組，您可能需要執行額外的動作。 </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">此外，關鍵字可以作為「S_kwcid」值的一部份，插入至登陸 URL 中，因此若關鍵字中包含特殊字元或符號，請確認您的網站伺服器可以支援這些字元 (常見特殊字元的範例為「+」，用於「加上廣泛比對修飾符」的關鍵字中)。 </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol">手動</span>: 讓您管理如何將追蹤參數新增到搜尋引擎的追蹤範本/目的地 URL。<a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33" format="dita" scope="local">如需各個搜尋引擎的相關資訊，請參閱這些手動追蹤範例</a>。 </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. 在&#x200B;**[!UICONTROL 「對應」]區段，您可以選擇要與這個搜尋引擎帳戶相連結的報表套裝。**&#x200B;在儲存 Advertising 帳戶之前，您必須先提供至少一個報表套裝。您可以將多個帳戶對應到多個報表套裝 (1 對 1、1 對多、多對多)。請注意，系統只會將 AMO 從搜尋引擎提取的資料複製到任何對應的報表套裝，因此資料不會遭到分割。

   >[!IMPORTANT]
   >
   >Only report suites that have been [mapped to an Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) will be available for selection. If you do not see your report suite listed, refer to [Troubleshoot Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   依照以下準則進行&#x200B;**[!UICONTROL 「對應設定」]:**

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>報表套裝對應 </p> </td> 
      <td colname="col2"> <p>報表套裝對應決定與此搜尋引擎帳戶相連結的報表套裝。換句話說，這會決定要將搜尋引擎資料傳送到哪些報表套裝中。 </p> <p>如果您的報表套裝並未列出，可以使用這個工具<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html" format="html" scope="external">將報表套裝對應到 Experience Cloud 組織</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下&#x200B;**[!UICONTROL 儲存]**。
1. 儲存後，免責聲明會顯示一系列警語。系統會要求確認您已閱讀合約並瞭解其中的條款。Click the checkbox, then click **[!UICONTROL OK]**.

   此時，系統會將您導向 Advertising 帳戶[管理使用者介面](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md#concept_531B99165A4E47B4B8849376B532AFDB)，而新建立的帳戶應該會列示在其中。

>[!NOTE]
>
>您應至少等候24小時，然後搜尋引擎資料才會開始填入您的Analytics報表。

