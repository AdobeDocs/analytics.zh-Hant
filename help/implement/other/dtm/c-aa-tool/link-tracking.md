---
description: 部署 Analytics 時，動態標籤管理中用於連結追蹤的欄位說明。
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 連結追蹤
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# 連結追蹤

部署 Analytics 時，動態標籤管理中用於連結追蹤的欄位說明。

**[!UICONTROL *`Property`*]**> **[!UICONCONTROL![](assets/settings_gear.png)

編輯工具]** > **[!UICONTROL 連結追蹤]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 元素 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 啟用 ClickMap </td>
   <td colname="col2"> <p>決定是否蒐集訪客點按對映資料。 </p> <p>請參閱[trackInlinestats](../../../vars/config-vars/trackinlinestats.md)。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 追蹤下載連結 </td>
   <td colname="col2"> <p>追蹤網站上的檔案下載連結。 </p> <p>請參閱[trackDownloadLinks](../../../vars/config-vars/trackdownloadlinks.md)。</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 下載副檔名 </td> 
   <td colname="col2"> <p>若網站包含供人下載檔案的連結，且檔案具有任何已列出的副檔名，則這些連結的 URL 將會出現在報表中。 </p>請參閱[linkDownloadFileTypes](../../../vars/config-vars/linkdownloadfiletypes.md)。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 追蹤對外連結 </td>
   <td colname="col2"> <p>判斷點按的任何連結是否為退出連結。 </p> <p>請參閱[trackExternalLinks](../../../vars/config-vars/trackexternallinks.md)。 </p> <p><b>單一頁面應用程式考量事項: </b>由於部分 SPA 網站的編碼方式，對 SPA 網站上頁面的內部連結，看起來可能像是對外連結。 </p> <p>您可以使用下列其中一個方法來追蹤來自 SPA 網站的對外連結: </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>如果您不想要從 SPA 追蹤任何對外連結，請插入項目至<span class="wintitle">永不追蹤</span>區段。 </p> <p>例如，<span class="filepath">https://testsite.com/spa/#</span> </p> <p>會忽略對此主機的所有 # 連結。會追蹤連線至其他主機的所有輸出連結，例如 <span class="filepath"></span>https://www.google.com。 </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>如果在 SPA 上有您想要追蹤的一些連結，請使用<span class="wintitle">永遠追蹤</span>區段。 </p> <p>例如，如果您有 <span class="filepath">spa/#/about</span> 頁面，即可以在<span class="wintitle">永遠追蹤</span>區段放入「關於」。 </p> <p>「關於」頁面是所追蹤的唯一對外連結。不會追蹤頁面上的任何其他連結 (例如，<span class="filepath"></span>https://www.google.com)。 </p> </li>
    </ul> <p>請注意，這兩個選項互斥。 </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> 保留 URL 參數 </td>
   <td colname="col2"> <p>保留查詢字串。 </p> <p>請參閱[linkLeaveQueryString](../../../vars/config-vars/linkleavequerystring.md)。 </p> </td>
  </tr>
 </tbody>
</table>
