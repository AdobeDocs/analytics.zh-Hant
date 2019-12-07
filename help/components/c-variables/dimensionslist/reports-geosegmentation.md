---
description: 顯示訪客位置的相關資料。地域劃分報告包括國家、地區、城市、美國州和美國 DMA (數位行銷區域)。已為所有客戶啟用地域劃分報表。
title: 地域劃分
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 地域劃分

顯示訪客位置的相關資料。地域劃分報告包括國家、地區、城市、美國州和美國 DMA (數位行銷區域)。已為所有客戶啟用地域劃分報表。

「Reports &amp; Analytics」中其他地方可用的所有量度會自動納入國家、地區、城市、美國州和 DMA 報告: 轉換和造訪型量度，外加計算量度。有關詳細資訊，請參閱本 Adobe [部落格](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/)文章。

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 國家 </td> 
   <td colname="col2"> <p> 最大的地理分區。除了大多數報告均可用的標準「排名」和「趨勢」視圖外，它還提供一種「地圖」視圖，該視圖會依據不同國家對網站總流量的不同貢獻，為其設定不同的色彩。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地區 </td> 
   <td colname="col2"> <p> 小於國家、大於城市的地理區域。在某些國家，地區是指一個州、省或府/州。在其他區域，則是指構成國、部門或都會區。在所示每個地區的右側，括弧中顯示有地區所在的國家。 </p> <p>在表格詳細資料中，按一下「執行用於此地區的城市報告」(放大鏡) 執行報告，可顯示選定地區中的城市與該地區的其他城市的比較情況。 </p> <p>請參閱<a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  >地域劃分地區和郵遞區號的使用狀況 (依國家區分)</a>，以瞭解哪些國家/地區使用地區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> <p> 最小的地理分區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美國州 </td> 
   <td colname="col2"> <p> 以熱圖顯示美國各州的訪客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美國 DMA </td> 
   <td colname="col2"> <p> (數位行銷區域) 整個美國的廣播與電視媒體市場分區。您可以篩選報告，只顯示特定州的行銷區域。該資料由達成夥伴關係的 Adobe 和 Nielsen Media Research 公司共同提供。 </p> <p>注意: 美國 DMA 報告中「未指定的」項目代表無法與特定 DMA 相關聯的訪客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 報告精確性 </td> 
   <td colname="col2"> <p>Digital Envoy 是一家提供 IP 情資與驗證解決方案的頂級公司，Adobe 與他們合作，推出了「地域劃分」這項可根據使用者的 IP 位址測量地理位置的功能。雖然以個別資料集為準的精確性可能會浮動，但一般而言，Digital Envoy 在國家層級能夠提供 99% 以上的精確性、地區層級可達 97% 以上的精確性，城市層級則可達 90% 以上。 </p> <p>注意: 這些數字假設未啟用移除 IP 位址最後八位元的 [設定] (/help/admin/admin/general-acct-settings-admin.md)。 </p> <p>IP 位址會對應至郵遞區號，每個城市都依「當地政府」為該城市制定的郵遞區號來定義。例如，柏林郊區不包含在柏林的定義中，而如果 IP 位址可精確對應至每個城鎮的郵遞區號，就會分別列出這些城鎮。 </p> <p>有些因素可能會對 的地域劃分資料造成影響，包括: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">代表公司 Proxy 的 IP 位址。這些 Proxy 可能看似是通過使用者公司網路的流量，然而實際上是不同位置 (若使用者在遠端工作)。 </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">行動 IP 位址。行動 IP 定位會根據位置與網路而在不同層級運作。許多電信業者會透過集中化或地區性 POP 取回 IP 流量。 </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">屬於衛星 ISP 使用者的 IP 位址。要識別這些使用者的確切位置並不容易，因為他們通常看似來自上行位置。 </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">軍事與政府 IP。此類 IP 通常屬於在全球各地旅行、而透過其居住地 (而非駐在基地或辦公室) 進入的工作人員。 </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">我們的地域劃分/IP 資料是由第三方廠商提供，並會根據 ISP 和其他網路來源所提供的資訊定期更新。由於 IP 查閱經常在世界各地進行買賣，因此本質上相當易變。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

