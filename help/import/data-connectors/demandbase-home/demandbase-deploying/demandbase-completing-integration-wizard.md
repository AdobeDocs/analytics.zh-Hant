---
description: 若要啓用整合，您必須在「資料連接器」介面中完成設定精靈。
seo-description: 若要啓用整合，您必須在「資料連接器」介面中完成設定精靈。
seo-title: 完成Adobe整合精靈
title: 完成Adobe整合精靈
uuid: 75260b92-a6 f5-44b6-b3 ea-d5945 fdd1歐洲
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

若要啓用整合，您必須在「資料連接器」介面中完成設定精靈。

1. 導覽至Adobe Marketing Cloud中的「資料連接器」(先前稱為Genesis)區域。
1. 啓動Demandbase2.0整合精靈。
1. 選擇所需的報表套裝，並提供整合的名稱。
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
   <td colname="col2"> 主要聯絡人的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 說明 </td> 
   <td colname="col2"> (可選)此整合設定的說明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API金鑰 </td> 
   <td colname="col2"> 您可以向Demandbase代表取得此項資訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自訂Demandbase Dimension# N </td> 
   <td colname="col2"> 這些是可選維度的ID。如需詳細資訊，請參閱Demandbase自訂維度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 傳送至Adobe Target </td> 
   <td colname="col2">如果「true」，Demandbase維度也會使用隱藏mbox傳送至Adobe Target。 <p>注意：您必須在網頁上實施已設定mbox. js檔案，才能收集維度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 設定下列變數映射項目：

   | 項目 | 說明 |
   |---|---|
   | Demandbase Dimensions | 從報表套裝中選擇可用的eVar變數。 |
   | Demandbase自訂維度(選用) | 從報表套裝中選擇可用的eVar變數。 |

1. 設定自訂維度的名稱(如果適用)。

   1. 如果您選擇在步驟中包含自訂維度並在步驟中映射選用的eVar，則必須為這些維度提供好記名稱。例如，如果您選擇輸入「stock_ atiker」作為自訂維度1，則應將包含「Dimension1」的方塊變更為「Stock Timer」。
   1. **請勿** 修改標準維度的名稱(即Demandbase SID、Company Name、Industry等)。

1. 核取方塊，即可自動為您建立Demandbase整合控制面板(建議)。
1. 檢閱所有組態項目，然後按一下 **[!UICONTROL 「立即啓動]**」。

