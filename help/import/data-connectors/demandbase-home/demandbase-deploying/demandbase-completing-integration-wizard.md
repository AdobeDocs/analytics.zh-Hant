---
description: 若要啟動整合，您必須在「資料連接器」介面中完成設定精靈。
seo-description: 若要啟動整合，您必須在「資料連接器」介面中完成設定精靈。
seo-title: 完成Adobe整合精靈
title: 完成Adobe整合精靈
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

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

