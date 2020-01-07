---
description: 關於自動配置 Adobe Analytics 部署的常見問題。自動配置方法可為您管理 AppMeasurement 代碼。
keywords: Dynamic Tag Management;plugins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Adobe Analytics 工具常見問題集
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics 工具常見問題集

關於自動配置 Adobe Analytics 部署的常見問題。自動配置方法可為您管理 [!DNL AppMeasurement] 程式碼。

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 透過 DTM 實作 Adobe Analytics 時，應該將外掛程式放在何處? </p> </td> 
   <td colname="col2"> <p> 如果使用 DTM 來手動託管 <code> s_code</code>，則可在與託管 <code> s_code</code> 相同的編輯器中新增外掛程式，正如同在一般的 Adobe Analytics 實作中一樣。 </p> <p>不過，您也可以選擇將外掛程式放入工具設定之<span class="term">自訂頁面程式碼</span>區段的編輯器中。這兩個實作方法的作用應該是相同的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果在新版本工具中進行配置變更，可以先在測試環境中進行測試再發佈到生產環境嗎? </p> </td> 
   <td colname="col2"> <p>是。 </p> <p>所有變更均可在測試環境中加以測試，如同您一般會在部署至生產環境之前所進行一般。如果因為您注意到測試中的問題而選擇不要發佈，生產代碼將會如發行新整合之前般繼續運作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我從手動配置 (現有工具的預設設定) 切換為自動配置，目前的設定會不會受到影響? </p> </td> 
   <td colname="col2"> <p>不可以。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我從手動程式庫管理切換為由 Adobe 管理，目前的設定或代碼會不會受到影響? </p> </td> 
   <td colname="col2"> <p>您指定的任何使用者代碼會由基礎 <span class="keyword">AppMeasurement</span> 程式庫加以覆寫。您必須將此代碼移至工具配置結尾的新<span class="wintitle">自訂頁面程式碼</span>區段，讓代碼可繼續執行。此方法可讓 <span class="keyword">AppMeasurement</span> 程式庫與使用者的自訂代碼分開進行管理 (和升級)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>發行新整合時，是否會保留 <span class="keyword">Adobe Analytics</span> 工具的修訂歷史記錄? </p> </td> 
   <td colname="col2"> <p>是。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如需設定資訊，請參閱[新增 Adobe Analytics 工具](/help/implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md)。

## 潛在的陷阱 {#section_201BF9E0EB7D4BC2B72A617543C2030B}

如果您目前使用 [!DNL Adobe Analytics]，整合可能會造成資料收集問題的機會很低。如果您在發行之後將您的程式庫發佈到生產環境，才會引發這些問題。(生產代碼會維持不變直到發佈發生。)

若要避免這些問題，請確保:

* 已在工具中正確輸入報表套裝 ID。
* 工具中的報表套裝 ID 符合 [!DNL AppMeasurement] 代碼中的 ID。
* 貨幣代碼、字元集、追蹤伺服器和 SSL 追蹤伺服器配置欄位均以支援的值正確設定。
* 自訂程式碼是在 [!DNL Library Management] 中定義。

