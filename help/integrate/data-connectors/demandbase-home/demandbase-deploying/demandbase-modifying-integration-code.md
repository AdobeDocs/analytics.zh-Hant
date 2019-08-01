---
description: 在大多數情況下，您不需要對「資料連接器」精靈產生的整合代碼進行任何修改。
seo-description: 在大多數情況下，您不需要對「資料連接器」精靈產生的整合代碼進行任何修改。
seo-title: 修改整合代碼
title: 修改整合代碼
uuid: 3f49a29b-ad38-4967-894a-ef7 ef4 d268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Modifying the Integration Code{#modifying-the-integration-code}

在大多數情況下，您不需要對「資料連接器」精靈產生的整合代碼進行任何修改。

不過，如果您需要進行調整，則部分程式碼設定如下所述。

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼設定 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">在前往Analytics收集伺服器之前，Adobe Analytics影像請求等待Demandbase資料的毫秒數上限。 <p>注意：此設定適用於所有可能透過Integrate模組執行的整合。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> 您的Demandbase API金鑰。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ APIUrl </td> 
   <td colname="col2"> Demandbase API的URL範本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> 用以將Demandbase維度值傳送至Adobe Analytics時的分隔字元。變更此設定可能會造成預設「分類規則」無法正常運作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ setTNT </td> 
   <td colname="col2">如果是true，則整合代碼會嘗試使用隱藏mbox將Demandbase維度傳送至Adobe Target做為描述檔參數。 <p>注意：這需要mbox. js代碼存在於頁面上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ tNTVarPrefix </td> 
   <td colname="col2"> 此字串會先前置至每個Demandbase維度名稱，再傳送至Adobe Target。例如，如果此設定有值「db_」，則維度「industry」將會傳送至Adobe Target作為「db_ industry」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ mensmensArray </td> 
   <td colname="col2"> 傳送至Adobe Analytics的標準Demandbase維度。建議您不要修改此設定。「max_ size」屬性是在發生截斷前，維度允許的字元數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ dimensionSarayCustom </td> 
   <td colname="col2"> 傳送至Adobe Analytics的自訂Demandbase維度。「max_ size」屬性是在發生截斷前，維度允許的字元數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ cName </td> 
   <td colname="col2"> 用來保持Demandbase API通訊狀態的作業Cookie名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ contextName </td> 
   <td colname="col2"> 用來將標準維度傳送至Adobe Analytics的contextData變數名稱。建議您不要修改此設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ contextNameCances </td> 
   <td colname="col2"> 用來將自訂維度傳送至Adobe Analytics的contextData變數名稱。建議您不要修改此設定。 </td> 
  </tr> 
 </tbody> 
</table>

