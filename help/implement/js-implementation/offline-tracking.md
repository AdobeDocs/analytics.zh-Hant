---
description: 下列變數和函數可讓您在應用程式離線時儲存測量呼叫。
keywords: Analytics Implementation
title: 離線追蹤
topic: Developer and implementation
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 離線追蹤

下列變數和函數可讓您在應用程式離線時儲存測量呼叫。

> [!NOTE]若要啟用離線追蹤，您的報表套裝必須已啟用時間戳記。如果報表套裝已啟用時間戳記，您的 `trackOffline` 組態屬性&#x200B;*必須*&#x200B;為 true。如果報表套裝未啟用時間戳記，您的 `trackOffline` 設定屬性&#x200B;*必須*&#x200B;為 false。如果此項目未正確設定，將會遺失資料。如果您不確定報表套裝是否啟用時間戳記， [contact Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

啟用後，離線 AppMeasurement 會以下列方式運作:

* 應用程式會傳送伺服器呼叫，但資料傳輸會失敗。
* AppMeasurement 會生成目前點按的時間戳記。
* AppMeasurement 會緩衝處理點按資料，然後將緩衝點按資料備份至永久性儲存體以免資料丟失。

後續每次點擊時，或在 `offlineThrottleDelay` 定義的間隔時間中，AppMeasurement 會試圖傳送緩衝點擊資料；保持原始的點擊順序。如果資料傳輸失敗，將會繼續緩衝點擊資料 (會在裝置離線時持續進行)。

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 屬性或方法 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>預設值: false </p> <p>啟用或停用測量程式庫的離線追蹤。 </p> <p> <b>範例:</b> </p> 
    <code class="syntax c">
      s.trackOffline=true; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>預設: 無限制 </p> <p>儲存在佇列中的離線點擊數量上限。 </p> <p> <b>範例:</b> </p> 
    <code class="syntax c">
      s.offlineHitLimit=100; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>預設值: 0 </p> <p>指定當 AppMeasurement 偵測到作用中的網路連線時，傳送緩衝點擊資料的延遲時間 (單位為毫秒)。指定此值可減輕因傳送多筆點擊資料而對應用程式造成的效能影響。 </p> <p>例如，如果 offlineThrottleDelay=1000 且系統花了 300 毫秒傳送點擊資料，則 AppMeasurement 會等候 700 毫秒再傳送下一筆緩衝點擊資料。 </p> 
    <code class="syntax c">
      s.offlineThrottleDelay=1000; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> 手動設定測量物件的上線或離線狀態。程式庫會自動偵測裝置為離線或上線，因此只有在您要將測量強制離線時，才需要這些方法。<code> forceOnline </code> 只用於在手動離線後，恢復為上線狀態。 </p> <p>當測量為離線時: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> 如果 <code> trackOffline </code> 為 true: 會儲存點擊資料，直到測量上線為止。 </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> 如果 <code> trackOffline </code> 為 false: 會捨棄點擊資料。 </li> 
    </ul> <p> <b>範例:</b> </p> 
    

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
