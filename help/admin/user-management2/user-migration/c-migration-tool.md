---
description: 關於將 Analytics 使用者 ID 移轉至 Adobe Experience Cloud 的 Admin Console，您必須瞭解的事項。
title: Analytics 使用者移轉至 Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Analytics 使用者移轉至 Admin Console{#analytics-user-migration-to-the-admin-console}

關於將 Analytics 使用者 ID 移轉至 Adobe Experience Cloud 的 Admin Console，您必須瞭解的事項。

如需 Admin Console 主題的一般說明 (而非與 Analytics 移轉相關的說明)，請參閱 [Admin Console 使用手冊](https://helpx.adobe.com/tw/enterprise/administering/user-guide.html)。

移轉後，您可 [以在Admin Console中管理Experience Cloud使用者](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html) 和產品。

## 什麼是 Analytics 使用者 ID 移轉？ {#section-adbe49aba10c4e62afa836a97894107c}

Analytics使用者ID移轉可讓管理員輕鬆將Analytics使用者管理中的使用者帳戶移轉至Adobe Admin Console。 在您的使用者進行移轉後，他們將可存取Experience Cloud中提供的解決方案和核心服務。 遷移將分階段向客戶推出。

使用 Admin Console 的好處包括：

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 優點 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>單一登入 </p> </td> 
   <td colname="col2"> <p>Analytics使用者可以使用其Adobe ID或Enterprise ID登入Experience Cloud和所有解決方案。 此登入可讓您存取Experience Cloud中的整合式解決方案和核心服務。 </p> <p>移轉後，系統會將嘗試透過舊版登入頁面 (<span class="filepath">my.omniture.com</span> 和 <span class="filepath">sc.omniture.com</span>) 登入的使用者重新導向至 <span class="filepath">experiencecloud.adobe.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理使用者身分和權限 </p> </td> 
   <td colname="col2"> <p>Analytics 管理員只能在 <a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/) 中管理使用者與權限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理產品和核心服務 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">邀請新使用者 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">建立產品設定檔 </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">授予使用者特定產品與服務的權限 </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">獲得 Adobe Experience Cloud 所提供的<a href="https://docs.adobe.com/content/help/zh-Hant/core-services/interface/experience-cloud.html">跨解決方案核心服務</a>存取權。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉使用者 ID 前的須知事項 (及做法) (常見問題集) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

移轉前可能會有的問與答。

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題／任務 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>我是Analytics管理員，收到移轉前的電子郵件。 第一件事該做什麼？ </p> </td> 
   <td colname="col2"> <p>確認自己擁有 Adobe ID 並且可以存取 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> <p>否則請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。(建議您先聯絡系統或產品管理員，請對方邀請您加入合適的組織。) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM與Analytics的整合 </p> </td> 
   <td colname="col2"> <p> 與Analytics整合的AEM使用者將需要變更其設定，才能使用Analytics共用密碼而非密碼。 </p> <p> 您應在移轉啟用前先執行此動作。 移轉停用後，原本設定的密碼將不再有效。 </p> <p><b>若要在Analytics中取得共用密碼</b> </p> <p> 從 Analytics (<span class="uicontrol">「Analytics</span> &gt; <span class="uicontrol">使用者管理」</span>) 取得共用機密，每個使用者取得的機密都會不同。 </p> <p><b>更新含有共用機密的 AEM 設定</b> </p> <p>請參閱<a href="https://helpx.adobe.com/tw/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">連線 Adobe Analytics 與建立框架</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新 Report Builder </p> </td> 
   <td colname="col2"> <p> <p>重要：請將您安裝的 <a href="https://marketing.adobe.com/resources/help/zh_TW/arb/t_install_arb.html">Report Builder</a> 更新至最新版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>什麼時候開始移轉？ </p> </td> 
   <td colname="col2"> <p>Adobe會透過電子郵件通知Analytics管理員，並說明移轉何時開始。 </p> <p>遷移到Admin Console將以波浪形式進行。 在移轉當天，Adobe會通知Analytics管理員並授與他們移轉工具的存取權。 登入公司達到為每個移轉階段定義的條件後，Adobe 會： </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">設定公司移轉的開始和結束日期。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">在公司目前的Analytics管理員移轉大約30天前，傳送電子郵件通知給他們。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">顯示產品內通知，通知管理員移轉的開始日期。 </li> 
    </ul> <p> 在移轉當天，您先前的權限群組會自動複製至管理控制台。 您將無法在 Analytics「管理工具」中邀請新的使用者或建立新群組。 </p> <p>移轉之後： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理員會使用Admin Console來管理其Analytics使用者和權限。 （您將不再使用「分析&gt;管理&gt;使用者管理」中的使用者管理介面。） </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">使用者需透過 Experience Cloud (而非 <span class="filepath">my.omniture.com</span>)，使用 Adobe ID 或 Enterprise ID 存取 Analytics。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉開始日期當天會有何變化？ </p> </td> 
   <td colname="col2"> <p>移轉開始日期上午 10 點 (UTC)： </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">您在Analytics中的現有權限群組會自動在管理控制台中複製為「產品設定檔」，包括報表套裝、量度、維度、Analytics和報表套裝工具的說明和詳細權限。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">如果您目前的Analytics使用者是在管理控制台中建立的（亦即他們有連結的Adobe/Enterprise ID），則會將他們新增至管理控制台中的適當產品設定檔。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics中「管理」標籤下的「使用者管理」區段將設 <span class="term"> 為唯讀</span>。 您將無法在此處建立新的使用者或權限群組，而必須在 Admin Console 中執行這兩項功能。如需詳細資訊，請參閱 <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Admin Console 中不支援的 Analytics 功能</a>。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">身為管理員，您將獲得使用者ID移 <a href="https://marketing.adobe.com/resources/help/zh_TW/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">轉工具的存取權</a>。 此外，除了說明內容和常見問答集的連結外，還會顯示產品內通知，其中包含移轉的結束日期（通常是未來60天）。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">您將會獲得「管理控制台」中「權限」標籤的存取權，此標籤可讓您使用您在Analytics中熟悉的所有精細選項來建立產品設定檔。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我要如何移轉使用者 ID？ </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. 使用此工具可將使用者新增至「管理控制台」中的產品設定檔（從Analytics的權限群組複製）。 您可以依自己的步調移轉使用者ID。 </p> <p>需要管理權限。 移轉完成後，便無法反轉。 </p> <p>移轉結束日期當天，使用者在登入公司內對 <span class="filepath">my.omniture.com</span> 的存取權限將會停用。使用者 (包括尚未移轉的使用者) 會經由系統重新導向，透過新的 Experience Cloud URL (<span class="filepath">experiencecloud.adobe.com</span>) 登入。 </p> <p>附註：Adobe 建議您藉此機會在移轉前對使用者與群組執行審核。刪除未使用的舊帳戶，或不應該再存取產品的帳戶 (例如組織的離職員工)。 </p> <p>相關主題：<a href="/help/admin/user-management2/user-migration/migrate-enterprise.md">移轉 Enterprise 與 Federated ID 的 Analytics 使用者帳戶</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉是否會影響我的 Analytics 實作項目或收集資料的方式？ </p> </td> 
   <td colname="col2"> <p>不可以。 </p> <p>移轉工具旨在協助您將使用者 ID 和權限，從 Analytics「使用者管理」轉移至 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉程序要多久的時間？ </p> </td> 
   <td colname="col2"> <p>所有目前的Analytics管理員在移轉前四週，都會收到一封移轉前通知電子郵件。 （實際開始日期會顯示在Analytics介面中。） </p> <p>當移轉開始時，管理員有60天的時間完成此程式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以加快移轉程序嗎？ </p> </td> 
   <td colname="col2"> <p>是。然而，Adobe 建議您利用移轉開始前的時間： </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">確認您是「管理控制台」中的Analytics產品管理員。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">向您的使用者群溝通，讓其登入體驗在移轉開始時會改變。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">稽核您目前的使用者和權限，並執行清理活動。 </li> 
    </ul> <p>若要加快移轉速度，請前往 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>聯絡客戶成功經理，提交提早開始日期的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我是Analytics管理員，無法存取「管理控制台」。 誰能協助我取得 Admin Console 的存取權？ </p> </td> 
   <td colname="col2"> <p>擁有貴組織 Admin Console 存取權的系統或產品管理員可以授予您存取權。如果不確定組織內誰擁有 Admin Console 的管理員權限，請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以延後移轉開始日期嗎？ </p> </td> 
   <td colname="col2"> <p>是。請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。 </p> 
    <draft-comment> 
     <p>請參閱下方說明，瞭解從開始日期起您目前的 Analytics 使用者與權限管理功能會有哪些變更。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的公司正要移轉至 Admin Console，我可以在移轉開始日期前於何處建立新的使用者和權限群組？ </p> </td> 
   <td colname="col2"> <p>在移轉開始日期之前，您可以在「管理控制台」或「分析&gt;使用者管理」中建立使用者。 </p> <p>移轉開始後，您只能在管理控制台中建立使用者和權限群組。 </p> 
    <draft-comment> 
     <p>請參閱下方的「移轉」章節，深入瞭解從移轉的開始日期起會有哪些變更。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我何時可以使用 Federated ID 實作單一登入？ </p> </td> 
   <td colname="col2"> <p> Admin Console不久將會提供工具，讓您將ID類型從Adobe ID變更為Federated ID。 在移轉期間，您無法將使用者移轉為Federated ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉期間需知事項(FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

有關遷移過程及其如何影響當前用戶管理的重要資訊。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>權限群組會如何複製到 Admin Console？我的使用者又會有什麼改變？ </p> </td> 
   <td colname="col2"> <p>已移轉的Analytics群組在「管理控制台」中 <i>稱為「產品設定檔</i> 」。 移轉時會保留原始群組的權限設定。 不過，指派給群組的使用者不會移轉。 當使用移轉工具移轉屬於該群組的使用者時，會將該使用者指派給該產品設定檔。 </p> <p>例如，將其成員授權至「報告建立工具」和「分析工作區」（含特定報表套裝、量度、維度）的「西海岸作業」權限群組，將會變成「西海岸作業」產品設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以將移轉作業指派給其他管理員嗎？ </p> </td> 
   <td colname="col2"> <p>移轉開始後，任何透過Experience Cloud存取您Analytics例項的管理員都可以使用移轉工具開始（或繼續）移轉使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以更新未移轉使用者的權限群組成員資格嗎？ </p> </td> 
   <td colname="col2"> <p>是。您可以從「Analytics使用者管理」區段中變更未移轉使用者的群組成員資格。 </p> 
    <draft-comment> 
     <p>請靜候 Ashok 說明已完成的部分。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉開始後，我可以在 Analytics 中建立使用者和權限群組，然後使用移轉工具將它們移到 Admin Console 嗎？ </p> </td> 
   <td colname="col2"> <p> 不可以。移轉開始後，所有新使用者和權限群組（在管理控制台中稱為產品設定檔）都必須在管理控制台中建立。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我使用移轉工具移轉的使用者，會獲派在 Analytics 中擁有的相同權限嗎？ </p> </td> 
   <td colname="col2"> <p>是。使用工具移轉的使用者，將獲得目前在Analytics中擁有的權限。 此外，當他們透過Experience Cloud存取Analytics時，將保留對其Analytics資產（例如區段、專案、計算量度等）的存取權。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我移轉至 Admin Console 的使用者是否仍可繼續透過 <span class="filepath">my.omniture.com</span> 存取 Analytics？ </p> </td> 
   <td colname="col2"> <p>是。已移轉的使用者將可繼續透過 <span class="filepath">my.omniture.com</span> 使用現有的使用者名稱和密碼存取 Analytics，直到移轉結束日期為止；除非您透過移轉工具停用其舊版登入存取權。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的兩個或兩個以上使用者在其Analytics記錄中擁有相同的電子郵件ID。 如果我移轉這類使用者會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>由於管理控制台中的使用者帳戶需要唯一的電子郵件ID，因此當您嘗試移轉多個使用者時，會遇到「重複的電子郵件ID」錯誤。 您可以在重試移轉之前，先在「使用者管理（舊版）」區段下更新未移轉使用者的電子郵件ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 移轉使用者之後，我該做什麼？ </p> </td> 
   <td colname="col2"> <p>停用他們對 <span class="filepath">my.omniture.com</span> 的舊版登入存取權。除非舊版登入已移轉，否則您將無法關閉舊版登入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以追蹤移轉程序嗎？ </p> </td> 
   <td colname="col2"> <p>移轉工具包含控制面板，可顯示成功移轉多少使用者，以及有多少使用者停用了舊版登入。 </p> <p> 理想情況下，當100%的使用者完成移轉並停用舊版登入時，您會將登入公司成功移轉至Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在移轉期間，我需要執行使用者和權限管理。 我可以使用何種工具來執行此工作？ </p> </td> 
   <td colname="col2"> <p>移轉開始後，您將使用Admin Console來建立和管理新使用者和產品設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>當我使用工具移轉使用者時，他們會有什麼體驗？ </p> </td> 
   <td colname="col2"> <p>他們將會收到一封歡迎電子郵件，寄送至其Analytics使用者記錄中的電子郵件ID，通知他們透過Experience Cloud存取Analytics的新方式。 如果他們沒有現有的Adobe ID，將會提示他們建立一個，然後他們就可以使用其Adobe ID存取解決方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>除了使用移轉工具之外，我可以使用 API 來移轉使用者嗎？ </p> </td> 
   <td colname="col2"> <p>不可以。您必須使用移轉工具，以確保所有現有使用者都移轉至管理控制台。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪些 Analytics 使用者管理功能在 Admin Console 中無法使用？ </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">資產轉讓 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">使用者過期 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">用戶日誌 </li> 
    </ul> <p>Analytics使用者管理中仍可供您使用。 </p> <p>如需詳細資訊，請參閱 <a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Admin Console 中不支援的 Analytics 功能</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我們在「管理控制台」中建立了數種設定，並將它們對應至Analytics權限群組。 移轉開始後，這些設定會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>Analytics權限群組會在Admin Console中重新建立為產品設定檔，就像您的所有其他群組一樣。 這表示您將在主控台中看到兩個產品設定檔，其權限實質上是重複的。 您可以從Admin Console刪除重複的產品設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉使用者後的下個步驟是什麼？ </p> </td> 
   <td colname="col2"> <p>在您移轉了特定使用者或一組使用者之後，下一步就是停用他們的 <span class="filepath">my.omniture.com</span> 舊版登入。您可以在移轉工具中選取這些使用者，然後按一下顯示在螢幕頂端的內容相關「停用舊版登入」選項。 請注意，只有在您選取已成功移轉至管理控制台的使用者或使用者集時，才會顯示此選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉結束日期起會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>在移轉結束日期後（從移轉開始60天後），登入公司內的所有使用者都會被重新導向至透過Experience Cloud登入頁面使用其Adobe ID登入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我無法在移轉結束日期前移轉所有使用者。 未移轉的使用者是否會失去 Analytics 的存取權？ </p> </td> 
   <td colname="col2"> <p>在移轉結束日期前仍未移轉的使用者，將會經由系統重新導向至 Experience Cloud 登入頁面 (experiencecloud.adobe.com)，且將無法存取 Analytics。但是您仍可繼續存取移轉工具，以便找到並移轉這些使用者，藉此還原其存取權。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉後需知事項（常見問答集） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題／問題 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>從管理控制台刪除使用者 </p> </td> 
   <td colname="col2"> <p> 在Analytics中，已刪除的使用者會設 <span class="term"> 為過期</span>，但帳戶仍然存在。 保留帳戶可讓轉移資產，例如區段、計算量度、排程報表、專案等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳戶到期 </p> </td> 
   <td colname="col2"> <p> 您可以在「管理工具」的Analytics中手動設定帳戶到期日。 到期日一經到期，使用者將無法存取Analytics，但是無法存取其實際的Experience Cloud使用者帳戶（例如Adobe ID、Enterprise ID、Federated ID等）不會過期。 他們仍可登入Experience Cloud，但是無法點按Analytics。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Admin Console 中不支援的 Analytics 功能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>請詳閱以下您在移轉過程中可能發生的問題。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題／問題 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>登入身分 </p> </td> 
   <td colname="col2"> <p> 移轉至Admin Console的管理員將無法再使用「登入身分」功能存取已移轉至Admin Console的非管理員使用者帳戶。 此功能已從Analytics中取消使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者到期和資產轉移 </p> </td> 
   <td colname="col2"> <p> 管理控制台不支援使用者過期或資產傳輸。 管理員會針對這兩個功能，在Analytics的「管理工具」下方使用「Analytics使用者與資產」區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次存取（上次登入） </p> </td> 
   <td colname="col2"> <p> 有關使用者上次登入日期和時間的詳細資訊，可從「Analytics使用者與資產」連結取得，而不可從「管理控制台」取得。 Analytics 中的上次登入日期專指使用者實際從 Experience Cloud 存取 Analytics 時的登入日期，而不會反映出使用者登入 Experience Cloud 的日期/時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者管理 API <a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">Adobe 支援的身分類型</a> </p> </td> 
   <td colname="col2"> <p> 移轉至 Admin Console 的管理員應設定 Adobe I/O 所提供的<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">使用者管理 API</a>，以程式化存取 Admin Console 中的使用者帳戶。 </p> <p>啟用移轉時，Analytics權限API將會關閉。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網站服務憑證 </p> </td> 
   <td colname="col2"> <p> 使用者的網站服務憑證（及其共用機密）將無法在Admin Console中使用，而且可透過從「Analytics使用者與資產」區段按一下特定使用者來存取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>單一登入 </p> </td> 
   <td colname="col2"> <p> 當您完成移轉後，Analytics單一登入設定將會移除。 在移轉期間，它們仍會保持活動狀態。 使用 Analytics 單一登入的客戶應升級至 <a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">Adobe Federated ID</a>。 </p> <p>Analytics建議您先將使用者移轉為Adobe ID，以輕鬆建立Experience Cloud帳戶，然後將這些帳戶轉換為Federated單一簽署使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>下載權限群組 </p> </td> 
   <td colname="col2"> <p> Analytics管理工具或Adobe管理控制台將不再支援下載權限群組資訊。 客戶應使用adobe.io使用者管理API大量取得權限群組資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳戶建立日期 </p> </td> 
   <td colname="col2"> <p>帳戶建立日期資訊不再受Analytics管理工具或Adobe管理控制台的支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>大量電子郵件 </p> </td> 
   <td colname="col2"> <p>Analytics管理控制台或Adobe管理控制台將不再支援大量電子郵件給使用者。 客戶可從Adobe Admin Console大量匯出其使用者的電子郵件地址，並使用任何他們想要的電子郵件用戶端傳送電子郵件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何通知使用者有關移轉的事宜 {#section-f3b25f672a3a4d03b0559656fd99d20a}

您可能想要主動將此移轉計畫告知目前的使用者。 您可以自訂以下的範本並傳送給所有目前的 Analytics 使用者：

若要以電子郵件寄送所有使用者，請導覽 **[!UICONTROL Analytics]** 至> **[!UICONTROL Admin]** > **[!UICONTROL User Management]** >以電子郵 [件傳送使用者](https://marketing.adobe.com/resources/help/zh_TW/reference/t_email_users.html)。

**主旨：**&#x200B;即將推出 – 登入 Adobe Analytics 和 Adobe Experience Cloud 的新方式。

**內文：** Adobe Analytics 使用者，您好！

敝公司所有的 Adobe Analytics 帳戶即將從 [!DNL https://my.omniture.com/login/] 移轉至 Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/))。透過此移轉，您的Adobe Analytics帳戶將會升級，以便透過Adobe Experience Cloud存取Analytics。 雖然存取Analytics的方法將會變更，但您對報表套裝和工具的所有現有權限將會保留。

**後續步驟：**&#x200B;我們將於以下日期開始移轉使用者：**插入日期**。請留意歡迎訊息，您的新登入位址會列在您的分析帳戶下，並寄送至電子郵件ID。 如果您尚未設定連結至 [您電子郵件地址的Adobe ID](https://helpx.adobe.com/tw/x-productkb/global/adobe-id-account-change.html) ，系統會要求您設定帳戶。

**實用資源：**

[登入及管理個人資料設定](https://marketing.adobe.com/resources/help/zh_TW/mcloud/getting-started-experience-cloud.html).

[關於Experience Cloud中的雲端、核心服務](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) 、解決方案

如果您有任何疑問或顧慮，請連絡您的Analytics管理員。

最好，

Analytics 管理員
