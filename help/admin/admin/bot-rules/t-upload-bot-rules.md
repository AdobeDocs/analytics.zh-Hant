---
description: 若要大量上傳機器人規則，您可上傳用於定義規則的 CSV 檔。
seo-description: 若要大量上傳機器人規則，您可上傳用於定義規則的 CSV 檔。
seo-title: 上傳機器人規則
solution: Analytics
subtopic: 機器人規則
title: 上傳機器人規則
topic: 管理工具
uuid: bd70c199-5817-437e-980d-6d8f95d82f2c
translation-type: tm+mt
source-git-commit: 93d6c7698216b3064f5417dbcfb33184efc2c132

---


# 上傳機器人規則

若要大量上傳機器人規則，您可上傳用於定義規則的 CSV 檔。

建立 CSV 檔案，依下列順序加入以下各欄:

<table id="table_770891EF9E4A49F695977BB6446736B5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 機器人名稱</code> </p> </td> 
   <td colname="col2"> <p> <code>IP 開頭</code> </p> </td> 
   <td colname="col3"> <p> <code>IP 結尾</code> </p> </td> 
   <td colname="col4"> <p> <code> 代理符合規則 (包含或開頭為)</code> </p> </td> 
   <td colname="col5"> <p> <code> 代理包含 (100 字元上限)</code> </p> </td> 
   <td colname="col6"> <p> <code> 代理排除 (255 字元上限)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以定義 3 種機器人規則:

* 使用者代理包含或開頭為
* 單一 IP 位址或萬用字元符合
* IP 範圍符合

匯入檔案中每一列都只能包含下列其中一種機器人定義:

* **使用者代理包含或開頭為**: 提供單一使用者代理字串，與「代理包含」欄比對。在「代理符合規則」欄位中加入&#x200B;*「包含」*&#x200B;或&#x200B;*「開頭為」*，指定符合類型。An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. 字串比對不分大小寫。「IP 開頭」和「IP 結尾」欄都必須為空。

* **單一IP位址或萬用字元符合**：若要比對單一IP位址( `10.10.10.1`)或萬用字元IP位址( `10.10.*.*`)，請在「IP開頭」和「IP結尾」欄中放置相同的值。「符合規則」、「代理包含」和「代理排除」必須為空。

* **IP 範圍符合**: 使用「IP 開頭」和「IP 結尾」欄，定義 IP 位址的範圍。Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. 「符合規則」、「代理包含」和「代理排除」必須為空。

## 多個規則結合 OR

若要結合 OR 和一組規則來比對機器人 (例如，使用者代理或 IP 位址)，請在機器人名稱欄位中提供您要組合使用之所有規則的完整名稱。不支援 AND 比對。

## 以上傳檔案覆寫所有規則

選取&#x200B;**[!UICONTROL 「覆寫現有規則」]核取方塊，刪除所有現有規則並以上傳檔案中定義的規則加以取代。**

## 匯出規則

**[!UICONTROL 「匯出已上載機器人檔案」]按鈕可將 UI 中定義的所有規則匯出維 CSV 格式。**
