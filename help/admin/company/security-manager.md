---
description: 可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。
seo-description: 可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。
seo-title: 安全管理員
solution: Analytics
title: 安全管理員
topic: 管理工具
uuid: b3fbdba0-e2 f-4d67-92e3-ef05711141 d4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 安全管理員

可讓您控制報告資料的存取權。選項包括增強式密碼、密碼過期、IP 登入限制及電子郵件網域限制。

**[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理]** &gt; **[!UICONTROL 公司設定]** &gt; **[!UICONTROL 安全性」]**

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
   <td colname="col2"> <p>限制存取特定 IP 位址或 IP 位址範圍的報告。 </p> <p>「IP 位址篩選」清單可以新增高達 100 個項目，每個項目可以是特定的位址或一個位址範圍。 </p> <p> 「IP 位址篩選」清單中至少必須要有一個項目，<span class="wintitle">「強制 IP 登入限制」</span>才會開始執行。 </p> <p> <span class="uicontrol"> 接受的IP位址</span>：若要指定IP位址範圍，請將範圍括住(例如，
   <code>
    192.168.10.[20-240]
   </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
   <code>
    192.168.[10-14].*
   </code>) </p> <p>失敗的登入會予以記錄，並可從<a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local">使用與存取記錄檔</a>中檢視。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 執行電子郵件網域限制</span> </td> 
   <td colname="col2"> <p>對 Analytics 要傳送書籤、可下載之報告及警報的電子郵件地址和網域進行篩選。 </p> <p>電子郵件篩選清單支援高達 100 個項目，每個項目都可以是電子郵件地址或整個電子郵件網域。 </p> <p>若計劃報告具有未核准的電子郵件目的地，Analytics 會傳送一份電子郵件通知此問題，並附上取消報告計劃的連結。 </p> <p> <span class="wintitle">「接受的電子郵件網域篩選」</span>清單中至少必須要有一個項目，<span class="wintitle">「執行電子郵件網域限制」</span>才會開始執行。 </p> <p> <span class="uicontrol"> 接受的電子郵件地址和網域</span>：若要指定IP位址範圍，請將範圍括住(例如，
   <code>
    192.168.10.[20-240]
   </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
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

