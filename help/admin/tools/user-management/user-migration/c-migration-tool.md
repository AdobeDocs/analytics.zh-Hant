---
description: 關於將 Analytics 使用者 ID 移轉至 Adobe Experience Cloud 的 Admin Console，您必須瞭解的事項。
title: Analytics 使用者移轉至 Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
role: Admin
TQID: https://experienceleague.adobe.com/bCf6DWIpIVALcGPAi3tL8zlZ5V8lzPR-9XNCm4HuFnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 2971
ht-degree: 67%

---

# Analytics 使用者移轉至 Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

關於將 Analytics 使用者 ID 移轉至 Adobe Experience Cloud 中的 Adobe Admin Console 需知。

如需 Adobe Admin Console 主題的一般說明 (而非與 Analytics 移轉相關的說明)，請參閱 [Admin Console 使用手冊](https://helpx.adobe.com/tw/enterprise/administering/user-guide.html)。

移轉以後，您就可以在 Adobe Admin Console 中[管理 Experience Cloud 使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=zh-Hant)。

## 什麼是 Analytics 使用者 ID 移轉？ {#section-adbe49aba10c4e62afa836a97894107c}

Analytics 使用者 ID 移轉可以讓管理員將 Analytics User Management 中的使用者帳戶輕鬆移轉至 Adobe Admin Console。 移轉使用者後，他們就能存取Experience Cloud提供的解決方案和核心服務。 移轉程式會分階段向客戶推出。

使用 Adobe Admin Console 的好處包括：

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
   <td colname="col2"> <p>Analytics使用者可使用其Adobe ID或Enterprise ID登入Experience Cloud及所有解決方案。 此登入可讓您存取Experience Cloud中的整合式解決方案和核心服務。 </p> <p>移轉後，系統會將嘗試透過舊版登入頁面 (<span class="filepath">my.omniture.com</span> 和 <span class="filepath">sc.omniture.com</span>) 登入的使用者重新導向至 <span class="filepath">experiencecloud.adobe.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理使用者身分識別和權限 </p> </td> 
   <td colname="col2"> <p>Analytics 管理員只能在 <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> 中管理使用者與權限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理產品和核心服務 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">邀請新使用者 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">建立產品設定檔 </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">授予使用者對特定產品和服務的許可權 </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">獲得 Adobe Experience Cloud 所提供的<a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=zh-Hant">跨解決方案核心服務</a>存取權 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉使用者 ID 前的須知事項 (及做法) (常見問答) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

移轉前可能會有的問與答。

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題/任務 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>我是Analytics管理員，收到移轉前電子郵件。 第一件事該做什麼？ </p> </td> 
   <td colname="col2"> <p>確認自己擁有 Adobe ID 並且可以存取 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> <p>否則請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。 (建議您先聯絡系統或產品管理員，請對方邀請您加入合適的組織。) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM與Analytics整合 </p> </td> 
   <td colname="col2"> <p> 與Analytics整合的AEM使用者需要變更其設定，改用Analytics共用機密而非密碼。 </p> <p> 您應在啟用移轉之前執行此動作。 一旦停用移轉，原先設定的密碼將不再有效。 </p> <p><b>若要在Analytics中取得共用機密</b> </p> <p> 從 Analytics (<span class="uicontrol">「Analytics</span> &gt; <span class="uicontrol">使用者管理」</span>) 取得共用機密，每個使用者取得的機密都會不同。 </p> <p><b>更新含有共用機密的 AEM 設定</b> </p> <p>請參閱<a href="https://helpx.adobe.com/tw/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">連線 Adobe Analytics 與建立框架</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新 Report Builder </p> </td> 
   <td colname="col2"> <p> <p>重要：請將您安裝的 <a href="/help/analyze/report-builder/report-builder-setup.md">Report Builder</a> 更新至最新版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>什麼時候開始移轉？ </p> </td> 
   <td colname="col2"> <p>Adobe會透過電子郵件通知Analytics管理員，告知他們何時開始移轉。 </p> <p>移轉至 Adobe Admin Console 的程序會分階段執行。 移轉當天，Adobe會通知Analytics管理員，並授予他們移轉工具的存取權。 登入公司達到為每個移轉階段定義的條件後，Adobe 會： </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">設定公司移轉的開始和結束日期。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">傳送電子郵件通知給公司目前的Analytics管理員，約在移轉前30天進行。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">顯示產品內通知，通知管理員移轉的開始日期。 </li> 
    </ul> <p> 移轉當天，系統會將您先前的權限群組會自動複製到 Adobe Admin Console。 您將無法在 Analytics「管理工具」中邀請新的使用者或建立新群組。 </p> <p>移轉之後： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理員會透過 Adobe Admin Console 管理 Analytics 使用者和權限。 (您將無法再使用「Analytics &gt; 管理 &gt; 使用者管理」中的使用者管理介面)。 </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">使用者需透過 Experience Cloud (而非 <span class="filepath">my.omniture.com</span>)，使用 Adobe ID 或 Enterprise ID 存取 Analytics。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉開始日期當天會有何變化？ </p> </td> 
   <td colname="col2"> <p>移轉開始日期上午 10 點 (UTC)： </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Analytics 中的現有權限群組將會自動複製到 Adobe Admin Console 中作為「產品設定檔」，包括涵蓋報告套裝、量度、維度、Analytics 及「報告套裝工具」之說明與精細的權限。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">如果您目前有任何 Analytics 使用者是在 Adobe Admin Console 中建立的 (表示他們擁有相連結的 Adobe/Enterprise ID)，系統會將這些使用者新增到 Adobe Admin Console 中相應的產品設定檔。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics「管理」標籤下的「使用者管理」區段將會設為<span class="term">唯讀</span>。 您將無法在此處建立新的使用者或權限群組，而必須在 Adobe Admin Console 中執行這兩項功能。 如需詳細資訊，請參閱 <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Adobe Admin Console 中不支援的 Analytics 功能</a>。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">您身為管理員，將會被授與<a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">使用者 ID 移轉工具</a>的存取權。 此外，畫面上會出現產品內通知，除了說明內容和常見問題的連結外，也會告知您移轉的結束日期 (通常是 60 天後)。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">您將獲得 Adobe Admin Console「權限」標籤的存取權，以便使用熟悉的所有 Analytics 精細選項來建立「產品設定檔」。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我要如何移轉使用者 ID？ </p> </td> 
   <td colname="col2"> <p> 按一下管理頁面上「使用者管理」下方的<a href="/help/admin/tools/user-management/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9">移轉使用者 ID</a>。 使用工具將使用者新增到 Adobe Admin Console 中的產品設定檔 (從 Analytics 的權限群組複製)。 您可以依照自己的步調移轉使用者ID。 </p> <p>需要管理許可權。 移轉一旦完成，即無法回覆。 </p> <p>移轉結束日期當天，使用者在登入公司內對 <span class="filepath">my.omniture.com</span> 的存取權限將會停用。 使用者 (包括尚未移轉的使用者) 會經由系統重新導向，透過新的 Experience Cloud URL (<span class="filepath">experiencecloud.adobe.com</span>) 登入。 </p> <p>註解：Adobe 建議您藉此機會在移轉前對使用者與群組執行審核。 刪除未使用的舊帳戶，或不應該再存取產品的帳戶 (例如組織的離職員工)。 </p> <p>相關主題：<a href="/help/admin/tools/user-management/user-migration/migrate-enterprise.md">移轉 Enterprise ID 與 Federated ID 的 Analytics 使用者帳戶</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉是否會影響我的 Analytics 實作項目或收集資料的方式？ </p> </td> 
   <td colname="col2"> <p>不可以。 </p> <p>移轉工具旨在協助您將使用者 ID 和權限，從 Analytics「使用者管理」轉移至 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉程序要多久的時間？ </p> </td> 
   <td colname="col2"> <p>所有目前的Analytics管理員都會在移轉的四週前收到移轉前通知電子郵件。 （實際開始日期會顯示在Analytics介面中。） </p> <p>移轉開始時，管理員有60天的時間完成此程式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以加快移轉程序嗎？ </p> </td> 
   <td colname="col2"> <p>是。 然而，Adobe 建議您利用移轉開始前的時間： </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">確認自己是 Adobe Admin Console 的 Analytics 產品管理員。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">向您的使用者群傳達，他們的登入體驗將在移轉開始時變更。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">稽核您目前的使用者和許可權，並執行清理活動。 </li> 
    </ul> <p>若要加快移轉速度，請透過<a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html"> Adobe客戶服務</a>聯絡您的Adobe客戶團隊，並提交提早開始日期的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我是 Analytics 管理員，但沒有 Adobe Admin Console 的存取權。 誰能協助我取得 Adobe Admin Console 的存取權？ </p> </td> 
   <td colname="col2"> <p>擁有貴組織 Adobe Admin Console 存取權的系統或產品管理員可以授予您存取權。 如果不確定組織內誰擁有 Admin Console 的管理員權限，請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以延後移轉開始日期嗎？ </p> </td> 
   <td colname="col2"> <p>是。 請聯絡 <a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Adobe 客戶服務</a>。 </p><p>請參閱下方說明，瞭解從開始日期起您目前的 Analytics 使用者與權限管理功能會有哪些變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的公司正要移轉至 Adobe Admin Console，我可以在移轉開始日期前於何處建立新的使用者和權限群組？ </p> </td> 
   <td colname="col2"> <p>在移轉開始日期前，您可以在 Adobe Admin Console 或依序前往「Analytics &gt; 使用者管理」建立使用者。 </p> <p>移轉開始後，您便只能在 Adobe Admin Console 中建立使用者和權限群組。 </p><p>請參閱下方的「移轉」一節，以詳細了解從移轉開始日期起將會發生的事情。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我何時可以使用 Federated ID 實作單一登入？ </p> </td> 
   <td colname="col2"> <p> 您很快就能在 Adobe Admin Console 中取得工具，將 ID 類型從 Adobe ID 變更為 Federated ID。 在移轉期間，您無法以Federated ID移轉使用者。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉期間須知（常見問題集） {#section-d394524aa6d046d79025bbd7499792bc}

有關移轉程式以及它如何影響目前使用者管理的重要資訊。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>權限群組會如何複製到 Adobe Admin Console？ 我的使用者又會有什麼改變？ </p> </td> 
   <td colname="col2"> <p>已移轉的 Analytics 群組在 Adobe Admin Console 中稱為<i>產品設定檔</i>。 原始群組的許可權設定會保留在移轉中。 但是，指派給群組的使用者不會移轉。 當使用移轉工具移轉屬於該群組的使用者時，會將該使用者指派給該產品設定檔。 </p> <p>例如，「West Coast Operations」許可權群組若為其成員授予Report Builder和Analysis Workspace （包含特定報表套裝、量度、維度）的許可權，將成為「West Coast Operations」產品設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以將移轉作業指派給其他管理員嗎？ </p> </td> 
   <td colname="col2"> <p>移轉一旦開始，任何透過Experience Cloud存取您的Analytics執行個體的管理員都可以使用移轉工具來開始（或繼續）移轉使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以更新未移轉使用者的權限群組成員資格嗎？ </p> </td> 
   <td colname="col2"> <p>是。 您可以在「 Analytics使用者管理」區段中變更未移轉使用者的群組成員資格。 </p><p>請靜候 Ashok 說明已完成的部分。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉開始後，我可以在 Analytics 中建立使用者和權限群組，然後使用移轉工具將它們移到 Adobe Admin Console 嗎？ </p> </td> 
   <td colname="col2"> <p> 否。 一旦移轉開始後，所有的新使用者和權限群組 (在 Adobe Admin Console 中稱為「產品設定檔」) 都必須在 Adobe Admin Console 中建立。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我使用移轉工具移轉的使用者，會獲派在 Analytics 中擁有的相同權限嗎？ </p> </td> 
   <td colname="col2"> <p>是。 使用此工具移轉的使用者將獲得目前在Analytics中的許可權。 此外，他們透過Experience Cloud存取Analytics時，仍可保留其Analytics資產（例如區段、專案、計算量度等）的存取權。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我移轉至 Adobe Admin Console 的使用者是否仍可繼續透過 <span class="filepath">my.omniture.com</span> 存取 Analytics？ </p> </td> 
   <td colname="col2"> <p>是。 已移轉的使用者將可繼續透過 <span class="filepath">my.omniture.com</span> 使用現有的使用者名稱和密碼存取 Analytics，直到移轉結束日期為止；除非您透過移轉工具停用其舊版登入存取權。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的兩名或更多使用者在其Analytics記錄中具有相同的電子郵件ID。 如果我移轉這類使用者會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>由於 Adobe Admin Console 中的使用者帳戶需使用不重複電子郵件 ID，因此當您嘗試移轉多位有這類情況的使用者時，就會看見「電子郵件 ID 重複」錯誤。 在重試移轉之前，您可以在「使用者管理（舊版）」區段下方更新未移轉使用者的電子郵件ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 移轉使用者之後，我該做什麼？ </p> </td> 
   <td colname="col2"> <p>停用他們對 <span class="filepath">my.omniture.com</span> 的舊版登入存取權。 除非舊版登入已移轉，否則您將無法關閉舊版登入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以追蹤移轉程序嗎？ </p> </td> 
   <td colname="col2"> <p>移轉工具內含的儀表板，可以顯示有多少使用者已順利移轉，以及其中有多少使用者的舊版登入功能已停用。 </p> <p> 理想情況下，當所有使用者均已完成移轉且停用舊版登入功能後，您的登入公司便會順利移轉至 Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉期間我需要執行使用者和許可權管理。 我可以使用何種工具來執行此工作？ </p> </td> 
   <td colname="col2"> <p>移轉開始後，您將可使用 Adobe Admin Console 建立及管理新使用者和產品設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>當我使用工具移轉使用者時，他們會有什麼體驗？ </p> </td> 
   <td colname="col2"> <p>訪客將會收到一封歡迎電子郵件，寄至其Analytics使用者記錄中的電子郵件ID，通知他們透過Experience Cloud存取Analytics的新方式。 如果他們沒有現有的Adobe ID，則系統會提示他們建立一個，之後他們便可以使用其Adobe ID存取解決方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>除了使用移轉工具之外，我可以使用 API 來移轉使用者嗎？ </p> </td> 
   <td colname="col2"> <p>否。 您必須使用移轉工具，以確保現有的所有使用者均移轉至 Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪些 Analytics 使用者管理功能在 Adobe Admin Console 中無法使用？ </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">資產轉移 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">使用者到期 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">使用者記錄 </li> 
    </ul> <p>這些在Analytics使用者管理中仍可供使用。 </p> <p>如需詳細資訊，請參閱 <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Adobe Admin Console 中不支援的 Analytics 功能</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我們在 Adobe Admin Console 中建立了數個設定，並將它們對應至 Analytics 權限群組。 移轉開始後，這些設定會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>Analytics 權限群組會像您的其他群組一樣，在 Adobe Admin Console 中重新建立為產品設定檔。 這表示您會在 Admin Console 中看到兩個基本上具有重複權限的產品設定檔。 您可以將重複的產品設定檔從 Adobe Admin Console 中刪除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉使用者後的下個步驟是什麼？ </p> </td> 
   <td colname="col2"> <p>在您移轉了特定使用者或一組使用者之後，下一步就是停用他們的 <span class="filepath">my.omniture.com</span> 舊版登入。 若要這麼做，您可以在移轉工具中選取使用者，然後按一下顯示在螢幕上方的「停用舊版登入」關聯選項。 請注意，只有在您選取已順利移轉至 Adobe Admin Console 的特定使用者或一組使用者時，畫面上才會顯示這個選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移轉結束日期起會發生什麼事？ </p> </td> 
   <td colname="col2"> <p>移轉結束日期後（自移轉開始起的60天），系統會將您登入公司內的所有使用者，重新導向，使用他們的Adobe ID，透過Experience Cloud登入頁面登入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我無法在移轉結束日期前移轉所有使用者。 未移轉的使用者是否會失去 Analytics 的存取權？ </p> </td> 
   <td colname="col2"> <p>在移轉結束日期前仍未移轉的使用者，將會經由系統重新導向至 Experience Cloud 登入頁面 (experiencecloud.adobe.com)，且將無法存取 Analytics。 但是您仍可繼續存取移轉工具，以便找到並移轉這些使用者，藉此還原其存取權。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 移轉後須知（常見問題集） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題/問題 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>從 Adobe Admin Console 中刪除使用者 </p> </td> 
   <td colname="col2"> <p> 在 Analytics 中，已刪除的使用者會被設定為「<span class="term">已過期</span>」，但該帳戶仍然存在。 保留帳戶可讓轉移資產（例如區段、計算量度、排程報表、專案等）得以進行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳戶有效期 </p> </td> 
   <td colname="col2"> <p> 您可以在「管理工具」的Analytics中手動設定帳戶到期日。 到期日過後，使用者將無法存取Analytics，但是可以存取其實際的Experience Cloud使用者帳戶（例如Adobe ID、Enterprise ID、Federated ID等） 不會過期。 他們仍可登入Experience Cloud，只是無法點按進入Analytics。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Admin Console 中不支援的 Analytics 功能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>請詳閱以下您在移轉過程中可能發生的問題。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題/問題 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>登入身份 </p> </td> 
   <td colname="col2"> <p> 移轉至 Adobe Admin Console 的管理員，將無法繼續使用「登入身分」功能存取已移轉至 Adobe Admin Console 的非管理員使用者帳戶。 此功能已淘汰。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者到期日和資產轉移 </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console 不支援使用者期限或資產傳送功能。 管理員會將Analytics中的管理工具底下的Analytics使用者和Assets區段用於這兩個功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次存取（上次登入） </p> </td> 
   <td colname="col2"> <p> 關於使用者上次登入日期與時間的詳細資料將透過「Analytics 使用者與資產」連結提供，而不是 Adobe Admin Console。 Analytics 中的上次登入日期專指使用者實際從 Experience Cloud 存取 Analytics 時的登入日期，而不會反映出使用者登入 Experience Cloud 的日期/時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者管理 API <a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">Adobe 支援的身分識別類型</a> </p> </td> 
   <td colname="col2"> <p> 移轉至Adobe Admin Console的管理員應設定Adobe Developer上所提供的使用者管理API ，以程式化存取Adobe Admin Console中的使用者帳戶。 </p> <p>當您啟用移轉功能時，Analytics許可權API將會關閉。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網站服務憑證 </p> </td> 
   <td colname="col2"> <p> 使用者的網站服務憑證 (及其共用機密) 將無法在 Adobe Admin Console 中使用，您可以從「Analytics 使用者與資產」區段點選特定使用者來加以存取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>單一登入 </p> </td> 
   <td colname="col2"> <p> 當您完成移轉時，Analytics單一登入設定將會移除。 移轉期間，它們將保持活動狀態。 使用 Analytics 單一登入的客戶應升級至 <a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">Adobe Federated ID</a>。 </p> <p>Analytics建議您先以Adobe ID移轉使用者，以輕鬆建立Experience Cloud帳戶，然後將這些帳戶轉換為Federated單一登入使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>正在下載許可權群組 </p> </td> 
   <td colname="col2"> <p> Analytics管理工具或Adobe Admin Console將不再支援下載許可權群組資訊。 客戶應使用adobe.io使用者管理API來大量取得許可權群組資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳戶建立日期 </p> </td> 
   <td colname="col2"> <p>Analytics管理工具或Adobe Admin Console不再支援帳戶建立日期資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>大量電子郵件 </p> </td> 
   <td colname="col2"> <p>Analytics 管理員工具或 Adobe Admin Console 均不再支援給使用者的大量電子郵件。 客戶可以從 Adobe Admin Console 大量匯出使用者的電子郵件地址，並使用想要的電子郵件用戶端來寄送電子郵件。 </p> </td> 
  </tr> 
 </tbody> 
</table>
