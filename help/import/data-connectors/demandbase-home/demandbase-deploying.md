---
description: 部署此整合是一個簡單的程式，需要執行下列動作。
seo-description: 部署此整合是一個簡單的程式，需要執行下列動作。
seo-title: 部署整合
title: 部署整合
uuid: 9c116ca8-4dbf-44eb-a832-574527ee88b7
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# 部署整合{#deploying-the-integration}

部署此整合是一個簡單的程式，需要執行下列動作。

## 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

若要啟動整合，您必須在「資料連接器」介面中完成設定精靈。

1. 導覽至Adobe Experience cloud中的「資料連接器」（先前稱為Genesis）區域。
1. 啟動Demandbase 2.0整合精靈。
1. 選擇所要的報表套裝，並提供整合的名稱。
1. 設定下列項目：

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 電子郵件地址 </td> 
   <td colname="col2"> 主要聯繫人的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 說明 </td> 
   <td colname="col2"> （可選）此整合設定的說明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API金鑰 </td> 
   <td colname="col2"> 您可以從Demandbase代表取得此資訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自訂需求庫維度#N </td> 
   <td colname="col2"> 這些是8個可選維度的ID。 如需詳細資訊，請參閱Demandbase自訂維度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 傳送至Adobe Target </td> 
   <td colname="col2">如果為"true",Demandbase維度也會使用隱藏的mbox傳送至Adobe Target。 <p>注意： 必須在網頁上實作已設定的mbox.js檔案，才能收集維度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 設定下列變數對應項目：

   | 項目 | 說明 |
   |---|---|
   | Demandbase維 | 從報表套裝中選擇可用的eVar變數。 |
   | Demandbase自訂維度（選用） | 從報表套裝中選擇可用的eVar變數。 |

1. 設定自訂維度的名稱（如果適用）。

   1. 如果您選擇在步驟4中加入自訂維度，並在步驟5中對應選用的eVar，則必須為這些維度提供好記的名稱。 例如，如果您選擇輸入"stock_ticker"作為「自訂維度1」，則應將包含"Dimension 1"的方塊變更為"Stock Ticker"。
   1. 不 **要修改** 標準8維的名稱（即Demandbase SID、公司名稱、行業等）。

1. 核取方塊，讓Demandbase整合儀表板自動為您建立（建議）。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。

## 部署整合程式碼{#deploying-the-integration-code}

完成整合精靈後，您必須將整合程式碼部署至Adobe Analytics部署程式碼(s_code)。

>[!NOTE]
>
>如果您使用Adobe tagManager或動態標籤管理來部署Adobe Analytics，則可使用其中一種工具輕鬆新增整合程式碼。

1. 前往「支 **[!UICONTROL 援]** 」標籤，從整合的「資 `integration code v2_0_1` 源」區下載並儲存資源。

1. 如果適用，請對程式碼進行任何必要的修改。 如需詳細資訊，請參閱修改整合代碼（在本頁）。
1. 如果您的Adobe Analytics部署程式碼中尚未包含整合模組，請加入它。
1. 使用下列其中一種方法部署程式碼：

   * 使用Adobe TagManager或動態標籤管理來新增代碼。
   * 或者，將程式碼傳送至負責更新Adobe Analytics部署程式碼的組織資源。

>[!IMPORTANT]
>
>請務必先在開發／測試環境中測試此整合的部署，然後再將它部署至生產環境。

## 修改整合代碼{#modifying-the-integration-code}

在大多數情況下，您不需要對「資料連接器」精靈產生的整合程式碼進行任何修改。

不過，如果您確實需要進行調整，以下會說明部分程式碼設定。

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
   <td colname="col2">Adobe Analytics影像要求在觸發至Analytics收集伺服器之前，等待Demandbase資料的毫秒數上限。 <p>注意： 此設定適用於所有可能透過「整合模組」執行的整合。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_key </td> 
   <td colname="col2"> 您的Demandbase API金鑰。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_apiURL </td> 
   <td colname="col2"> Demandbase API的URL範本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_delim </td> 
   <td colname="col2"> 分隔字元，用於在將Demandbase維度值傳送至Adobe Analytics時分隔這些值。 變更此設定可能會導致預設分類規則無法正確運作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_setTnt </td> 
   <td colname="col2">如果為true，則整合程式碼會嘗試使用隱藏的mbox，將Demandbase維度以描述檔參數的形式傳送至Adobe Target。 <p>注意： 這要求頁面上存在mbox.js代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_tntVarPrefix </td> 
   <td colname="col2"> 此字串會先於每個Demandbase維度名稱，再傳送至Adobe Target。 例如，如果此設定的值為"db_"，則維度"industry"會以"db_industry"的形式傳送至Adobe Target。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_dimensionsArray </td> 
   <td colname="col2"> 傳送至Adobe Analytics的標準Demandbase維度。 建議您不要修改此設定。 "max_size"屬性是維度在截斷之前允許的字元數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_dimensionsArrayCustom </td> 
   <td colname="col2"> 傳送至Adobe Analytics的自訂Demandbase維度。 "max_size"屬性是維度在截斷之前允許的字元數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_cName </td> 
   <td colname="col2"> 用於保留Demandbase API通訊狀態的作業Cookie名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_contextName </td> 
   <td colname="col2"> 用來傳送標準維度至Adobe Analytics的contextData變數名稱。 建議您不要修改此設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db。_contextNameCustom </td> 
   <td colname="col2"> 用來將自訂維度傳送至Adobe Analytics的contextData變數名稱。 建議您不要修改此設定。 </td> 
  </tr> 
 </tbody> 
</table>

## 包括整合模組{#including-the-integrate-module}

整合程式碼要求Integrate module必須存在於您的Adobe Analytics部署中。

如果您尚未將整合模組納入部署，請根據您的實作類型完成下列步驟。

### 針對AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. 將您從「 **[!UICONTROL Analytics]** &gt;管理&gt;代碼管理器」下載的AppMeasurement **[!UICONTROL zip檔案解壓縮]******。

1. 開啟名為的檔案 [!DNL AppMeasurement_Module_Integrate.js]。
1. 將此檔案的內容複製並貼上到主檔案 [!DNL AppMeasurement.js] 中。

   >[!NOTE]
   >
   >將它貼上到檔案中DO NOT ALTER ANYTHING BELOW THIS LINE COMMENT之前。

### 舊版程式碼（H程式碼） {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 從「資料連接器」UI的「資源」區域（在「支援」標籤下）下載「整合模組」。

   ![](assets/h_code.png)

1. 將該檔案的內容複製並貼至您的檔 [!DNL s_code] 案。

   >[!NOTE]
   >
   >將它貼上到檔案中DO NOT ALTER ANYTHING BELOW THIS LINE COMMENT之前。

## 驗證整合{#verifying-the-integration}

檢查即時追蹤和報告，以驗證整合是否成功擷取資料。

### 即時追蹤 {#section-9c20e8ff6b404ae09387ee07d675c9e2}

使用DigitalPulse除錯工具驗證Demandbase維度資料是否正傳送至Adobe Analytics。 刪除Cookie後，在已部署整合程式碼的網站上重新載入頁面。 假設您目前的IP對應至Demandbase所識別的組織，您應該會看到類似下列的結果。

**Reports &amp; Analytics（舊稱SiteCatalyst）包含兩個Demandbase上下文資料變數：**

![](assets/debugger1.png)

**Target Mbox包含Demandbase描述檔參數：**

只有在頁面上實施Target，且您已針對Adobe Target設定此整合時，您才會看到這個項目——請參閱Adobe整合精靈中的步驟4。

![](assets/debugger2.png)

### 報告 {#section-1792fe75dc3249d0ad063dfd87a89162}

使用使用Adobe整合精靈（步驟7）自動為您建立的儀表板，在Adobe Analytics中檢視您的Demandbase報表。

或者，您也可以導覽至Adobe Analytics功能表結構內的Demandbase報表——請參閱下方的螢幕擷取畫面。

>[!NOTE]
>
>在成功部署後的24-48小時內應會顯示此資料。

![](assets/reporting1.png)

![](assets/reporting2.png)

### 常問的問題 {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**"n/[a]"是什麼意思？**

Demandbase Data Connector會設定此預設值，以指出屬性何時為「不可用」。 有兩種常見的方案設定預設值：

* Demandbase會偵測訪客來自不屬於公司的IP位址。
* 會使用「帳戶監視」屬性（以"watch_list"開頭），但公司不在您的「帳戶監視」清單中。

**為什麼「`[n/a]`」對於特定屬性的顯示頻率較高？**

Demandbase會分類所有IP位址，並提供audience_segment屬性，即使訪客不來自公司IP亦然。 當觀眾傳回「Residential」、「Wireless」和「Hospitality」等值時，其他屬性可能無法使用。

有時，訪客的對象是「SMB」，但其他屬性將顯示「`[n/a]`」。 這表示Demandbase能夠將訪客分類為小型企業，但無法使用完整的公司個人檔案。 這通常發生在最小的公司，當多個小型企業使用相同的服務提供商或IP地址塊時。

### 開發人員考量事項 {#section-d33fff55bc4b4db99f82dee418ef1bc2}

如果您需要調整實作中的預設值，請更新行：

```
_db._nonOrgMatchLabel = "[n/a]";
```
