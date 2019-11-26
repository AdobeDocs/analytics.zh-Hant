---
description: 可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。
solution: Analytics
title: 安全管理員
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 229ce50a24bd7b86e3859775bb4fbeba1c6a5668

---


# 安全管理員

可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。

**[!UICONTROL Analytics]** &gt;管 **[!UICONTROL 理]** &gt;公 **[!UICONTROL 司設定]** &gt;安 **[!UICONTROL 全性]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 需要增強式密碼 </span> </td> 
   <td colname="col2">強制使用者建立遵守下列規則的安全密碼: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">長度不得少於 8 個字元。 </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">首位和末位字元之間至少包含一個符號或數字字元。 </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">至少包含一個英文字母。 </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">字典中找不到或包含字典中多個單詞 (英文)。 </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">不能包含登入使用者名稱中的 3 個連續字元。 </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">必須與前 10 個密碼不同。 </li> 
    </ul> <p>注意: 此功能將對日後的新密碼強制執行。但不會檢查現有密碼，或強制使用者變更現有密碼。因此，請考慮啟用密碼過期，強制使用者變更其密碼並遵循增強式密碼規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 密碼過期</span> </td> 
   <td colname="col2"> 強制使用者定期變更其使用者帳戶密碼。您可指定密碼隔多久過期，以及強制密碼立即過期。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 強制 IP 登入限制</span> </td> 
   <td colname="col2"> <p>(此功能無法與Experience cloud登入搭配使用。 請注意，自2020年10月起，此功能將不再提供。)限制存取特定 IP 位址或 IP 位址範圍的報告。 </p> <p>「IP 位址篩選」清單可以新增高達 100 個項目，每個項目可以是特定的位址或一個位址範圍。 </p> <p> 「IP 位址篩選」清單中至少必須要有一個項目，<span class="wintitle">「強制 IP 登入限制」</span>才會開始執行。 </p> <p> <span class="uicontrol"> 接受的IP位址</span>:若要指定IP位址範圍，請以方括弧括住範圍(例如 <code>
       192.168.10.[20-240]
     </code>)。 You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>失敗的登入會予以記錄，並可從<a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232">使用與存取記錄檔</a>中檢視。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 執行電子郵件網域限制</span> </td> 
   <td colname="col2"> <p>對 Analytics 要傳送書籤、可下載之報告及警報的電子郵件地址和網域進行篩選。 </p> <p>電子郵件篩選清單支援高達 100 個項目，每個項目都可以是電子郵件地址或整個電子郵件網域。 </p> <p>若計劃報告具有未核准的電子郵件目的地，Analytics 會傳送一份電子郵件通知此問題，並附上取消報告計劃的連結。 </p> <p> <span class="wintitle">「接受的電子郵件網域篩選」</span>清單中至少必須要有一個項目，<span class="wintitle">「執行電子郵件網域限制」</span>才會開始執行。 </p> <p> <span class="uicontrol"> 接受的電子郵件地址和網域</span>:若要指定IP位址範圍，請以方括弧括住範圍(例如 <code>
       192.168.10.[20-240]
     </code>)。 You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 密碼恢復通知</span> </td> 
   <td colname="col2"> <p>當使用者嘗試重設使用者帳戶密碼時，通知指定的管理員。 </p> <p> <span class="uicontrol">現存管理員</span>: 顯示所有管理員。您可以按住 Ctrl 鍵並按一下，及按住 Shift 鍵並按一下，選取多個管理員。 </p> <p> <span class="uicontrol">電子郵件成員</span>: 顯示目前定義的電子郵件群組。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 強制IP登入限制的 [!UICONTROL 生命週期結束]

「強 **[!UICONTROL 制IP登入限制]** 」功能是即將推出的舊版Analytics功能，可讓您將認為安全的特定IP位址列入白名單，以允許成功登入並存取您的Adobe Analytics環境。 在許多情況下，此功能可用來將公司IP位址設為使用者唯一可登入的安全IP位址。 因此，若要使用Adobe Analytics，使用者必須在公司辦公室或透過VPN登入網路。

### 我們為什麼要考慮終身？

Experience cloud登入移轉和／或Experience cloud登入在某些情況下會中斷此功能。 使用「客戶屬性」或「觀眾程式庫」的 **[!UICONTROL 客戶]** ，常 **[!UICONTROL 常會突破]**。

此外，如果您擁有多個Experience cloud解決方案，則可以透過使用其他解決方案之一登入Experience cloud來規避此需求，因為Analytics本身以外並不存在或不支援此功能。 使用者也可以透過IP欺騙來解決這個問題。

最後，Adobe透過單一登入和同盟ID提供功能正常且更優越的替代解決方案。 此功能可讓您更精確地控制使用者的登入體驗並提供安全性。

### 移除此功能對您有何影響？

對於任何已設定「 **[!UICONTROL 強制IP登入限制]** 」的客戶，此功能將於2020年10月移除。 屆時，任何仍有的IP登入限制將不再執行。 如果您仍需依IP位址限制登入，則應檢閱並實作建議的單一登入與同盟ID解決方案（以下更多資訊與資源）。

此外， **[!UICONTROL Analytics UI中的「]****[!UICONTROLA]** dmin &gt;公司設定&gt;安全性管理員」（如下所示）將會移除「強制IP登入限制管理員」。

![](assets/sec-manager2.png)

### 您還有哪些選擇？

如上所述，此Analytics功能將結束生命週期。 為了給您實作SSO和Federated ID的時間，我們已將EOL日期延遲至2020年10月。

SSO和Federated ID都是比我們目前提供的IP登入限制功能更優越的解決方案，可為您提供更多的控制、安全性和功能。

有關如何設定SSO/Federated ID的資訊，我們提供下列說明檔案。 我們建議您仔細閱讀並與IT部門合作，以實作這些內容：

* [單一登入與Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [管理控制台——身分設定檔案](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [管理控制台——身分設定教學課程（影片）](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [設定同盟ID教學課程（影片）](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [單一登入——常見問題](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Adobe支援的身分類型](https://helpx.adobe.com/enterprise/using/identity.html)

如果您想要繼續表達對IP登入限制的支援，並要求由Experience cloud提供，您可在我們的論壇頁面上投票支 [持此功能](https://forums.adobe.com/ideas/11648)。 如需有關SSO/Federated ID和EXC的其他問題或資訊，請聯絡Ryan Monger(monger@adobe.com)。
