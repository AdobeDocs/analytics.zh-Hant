---
description: 並非所有在「區段產生器」中建立的區段都與 Data Warehouse 相容。下表列出支援的功能。
title: Data Warehouse 區段相容性
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Data Warehouse 區段相容性

並非所有在「區段產生器」中建立的區段都與 [!DNL Data Warehouse] 相容。下表列出支援的功能。

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>排除</b> </td> 
   <td colname="col2"> 任何層級均支援 </td> 
   <td colname="col3"> 僅在特殊情況於頂層支援 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>循序區段</b> </td> 
   <td colname="col2"> 支援 </td> 
   <td colname="col3"> 不支援 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND 和 OR 可無限結合</b> </td> 
   <td colname="col2"> 支援 </td> 
   <td colname="col3"> 部分限制。請參閱下表中的*附註*。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>巢狀內嵌的容器</b> </td> 
   <td colname="col2"> 支援 </td> 
   <td colname="col3"> 部分限制 (必須減少範圍，例如訪客可包含點擊，但反向則不適用) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>維度</b> </td> 
   <td colname="col2">將維度拖放至「區段產生器」的「<span class="uicontrol">定義</span>」欄位，來瞭解其產品相容性。例如，只有 Analysis Workspace、Reports &amp; Analytics 和 Ad Hoc Analysis 支援以下維度： 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">進入伺服器 </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">進入類別 </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">進入日期 </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">所有搜尋頁面排名 </li> 
    </ul> </td> 
   <td colname="col3"> 將維度拖放至「區段產生器」的「<span class="uicontrol">定義</span>」欄位，來瞭解其產品相容性。例如，以下維度僅在「Data Warehouse」中才受支援： 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP 位址 </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">頁面 URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">訪客 ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud 訪客 ID </li> 
    </ul> <p>下列維度<b>無法</b>在 Data Warehouse 區段中使用： </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">所有搜尋頁面排名 </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">上午/下午 </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">日期 </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">星期 </li> 
     <li id="li_4008565353084611BD782B98D50C0611">一年當中的第幾天 </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">登入業務單位 </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">登入 (以登入開頭的所有維度，登入頁面除外) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">退出 (以退出開頭的所有維度，退出連結和退出頁面除外) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">階層 (以階層開頭的所有維度) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">點擊深度 </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">點擊類型 </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">小時 </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">月份 </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">找不到頁面 </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">付費搜尋 </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">季別 </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">回訪頻度 </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">單頁存取次數 </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">事件之前時間 </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">頁面逗留時間 - 分組 </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">每次瀏覽逗留時間 - 分段 </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">追蹤選擇退出原因 </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">美國各州 </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">平日/週末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>區段堆疊</b> </td> 
   <td colname="col2"> 支援 </td> 
   <td colname="col3"> 不支援 </td> 
  </tr> 
 </tbody> 
</table>

*注意：使用`AND/OR`時，Data Warehouse 不支援所有使用`exclusion`或`without`容器的情況。如果使用上述組合，Data Warehouse 只支援可重新寫入為`A AND NOT B`(或&#x200B;**包含此特徵**和&#x200B;**排除此特徵**) 的區段。*
