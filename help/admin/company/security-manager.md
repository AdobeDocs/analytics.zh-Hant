---
description: 可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。
solution: Analytics
title: 安全管理員
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# 安全管理員

「安全性管理員」可讓您控制對報告資料的存取。 選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。

## 設定

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
   <td colname="col2"> <p>(此功能無法與Experience cloud登入搭配使用。 請注意，自2020年10月起，此功能將不再提供。 [更多……](/help/admin/company/login-restrictions-eol.md)限制對特定IP位址或IP位址範圍的報表存取。 </p> <p>「IP 位址篩選」清單可以新增高達 100 個項目，每個項目可以是特定的位址或一個位址範圍。 </p> <p> 「IP 位址篩選」清單中至少必須要有一個項目，<span class="wintitle">「強制 IP 登入限制」</span>才會開始執行。 </p> <p> <span class="uicontrol"> 接受的IP位址</span>:若要指定IP位址範圍，請以方括弧括住範圍(例如 <code>
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

| 元素 | 說明 |
|--- |--- |
| 需要增強式密碼 | 強制使用者建立遵守下列規則的安全密碼: <ul><li>長度不得少於 8 個字元。</li><li>第一個字元和最後一個字元之間必須至少有一個符號／數字字元。</li><li>必須至少包含一個字母字元。</li><li>字典中找不到或包含字典中多個單詞 (英文)。</li><li>不能包含登入使用者名稱中的 3 個連續字元。</li><li>必須與前 10 個密碼不同。</li></ul>**注意**:這項功能會在後續的新密碼上執行。 但不會檢查現有密碼，或強制使用者變更現有密碼。因此，請考慮啟用密碼過期，強制使用者變更其密碼並遵循增強式密碼規則。 |
| 密碼過期 | 強制使用者定期變更其使用者帳戶密碼。您可指定密碼隔多久過期，以及強制密碼立即過期。 |
| 強制 IP 登入限制 | (此功能無法與Experience cloud登入搭配使用。 請注意，自2020年10月起，此功能將不再提供。 [更多……](/help/admin/company/login-restrictions-eol.md)<br> )限制對特定IP位址或IP位址範圍的報表存取。 「IP 位址篩選」清單可以新增高達 100 個項目，每個項目可以是特定的位址或一個位址範圍。「IP 位址篩選」清單中至少必須要有一個項目，「強制 IP 登入限制」才會開始執行。Accepted IP Address: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| 執行電子郵件網域限制 | 對 Analytics 要傳送書籤、可下載之報告及警報的電子郵件地址和網域進行篩選。電子郵件篩選清單支援高達 100 個項目，每個項目都可以是電子郵件地址或整個電子郵件網域。若計劃報告具有未核准的電子郵件目的地，Analytics 會傳送一份電子郵件通知此問題，並附上取消報告計劃的連結。**[!UICONTROL 「接受的電子郵件網域篩選」]**&#x200B;清單中至少必須要有一個項目，「執行電子郵件網域限制」才會開始執行。**[!UICONTROL 接受的電子郵件地址和網域]**:若要指定IP位址範圍，請以方括弧括住範圍(例如192.168.10.[20-240])。 You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*) |
| 密碼恢復通知 | 當使用者嘗試重設使用者帳戶密碼時，通知指定的管理員。**[!UICONTROL 現存管理員]**: 顯示所有管理員。您可以按住 Ctrl 鍵並按一下，及按住 Shift 鍵並按一下，選取多個管理員。**[!UICONTROL 電子郵件成員]**: 顯示目前定義的電子郵件群組。 |
