---
description: 顯示訪客位置的相關資料。 地域劃分報表包括國家、地區、城市、美國州和美國DMA（數位行銷區域）。 「地域劃分」報表可供所有客戶使用。
title: 地域劃分
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 地域劃分

顯示訪客位置的相關資料。 地域劃分報表包括國家、地區、城市、美國州和美國DMA（數位行銷區域）。 「地域劃分」報表可供所有客戶使用。

「Reports &amp; Analytics」中其他地方可用的所有量度會自動納入國家、地區、城市、美國州和 DMA 報告：轉換和造訪型量度，外加計算量度。For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報表 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 國家 </td> 
   <td colname="col2"> <p> 最大的地理分區。 除了大多數報告均可用的標準「排名」和「趨勢」視圖外，它還提供一種「地圖」視圖，該視圖會依據不同國家對網站總流量的不同貢獻，為其設定不同的色彩。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地區 </td> 
   <td colname="col2"> <p> 比國家小但比城市大的地理區域。 在某些國家，地區是州、省或州。 在其他地區，則是組成國家、部門或都市地區。 在顯示的每個區域的右側，括弧中還顯示區域的國家。 </p> <p>在表格詳細資料中，按一下「執行此地區的城市報表」（放大鏡），以執行報表，顯示選定地區中的城市與該地區其他城市相比的表現。 </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> <p> 最小的地理分區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美國州 </td> 
   <td colname="col2"> <p> 顯示美國各州訪客的熱圖。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. DMA </td> 
   <td colname="col2"> <p> （數位行銷區）美國廣播和電視媒體市場分區。 您可以篩選報表，只顯示特定狀態內的行銷區域。 此資料是透過Adobe與Nielsen Media Research, Inc.的合作關係提供。 </p> <p>注意：美國 DMA 報告中「未指定的」項目代表無法與特定 DMA 相關聯的訪客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 報表準確度 </td> 
   <td colname="col2"> <p>Adobe已與IP智慧與驗證解決方案的領先供應商Digital Envoy合作，提供地域劃分(GeoSegmentation)，這是根據使用者的IP位址進行地理測量的功能。 雖然個別資料集的準確度可能不同，但Digital Envoy通常在國家／地區層級提供超過99%的正確度、在地區層級提供超過97%的正確度，在城市層級提供超過90%的正確度。 </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>IP 位址會對應至郵遞區號，每個城市都依「當地政府」為該城市制定的郵遞區號來定義。例如，柏林郊區不包含在柏林的定義中，而如果 IP 位址可精確對應至每個城鎮的郵遞區號，就會分別列出這些城鎮。 </p> <p>有些因素可能會對 的地域劃分資料造成影響，包括： </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">代表公司Proxy的IP位址。 這些流量可能會顯示為透過使用者公司網路的流量，如果使用者正在遠端工作，實際上可能是不同的位置。 </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">行動IP位址。 行動IP定位的運作層級視位置和網路而定。 許多電信業者會透過集中式或地區性的POP來回傳IP流量。 </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">屬於衛星ISP使用者的IP位址。 識別這些使用者的特定位置很困難，因為他們通常似乎來自上行鏈路的位置。 </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">軍事和政府IP。 這通常是指在全球各地旅行，並通過其家鄉進入的人員，而不是他們目前駐在的基地或辦公室。 </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">我們的地域劃分/IP資料由第三方廠商提供，並會根據ISP和其他網路來源提供的資訊定期更新。 IP查詢本身就不穩定，因為它們經常在世界各地買賣。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

