---
description: HTTP 要求和回應標題可用來收集 AppMeasurement 未收集的資料。本節將說明資料收集期間所使用的標題。
keywords: Analytics Implementation
title: 資料彙集 HTTP 標題
topic: Developer and implementation
uuid: 3325e13c-b300-46e4-a592-3a83ed59718b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料彙集 HTTP 標題

HTTP 要求和回應標題可用來收集 AppMeasurement 未收集的資料。本節將說明資料收集期間所使用的標題。

## HTTP 要求標題 {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>標題</b> </td> 
   <td> <b>使用狀況</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>讀取先前由我們的資料收集伺服器建立的 Cookie。 </p> <p> 自 2014 年起，Adobe 伺服器將捨棄除了 Adobe 設定的 Cookie 以外，所有伴隨伺服器呼叫的 Cookie。如需 Adobe Cookie 的完整清單，請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/">Experience Cloud 中使用的 Cookie</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> 用於瀏覽器、作業系統和行動裝置偵測。 </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> 作為 User-Agent 的替代項目，使某些瀏覽器 (如 OperaMini) 的瀏覽器、作業系統和行動裝置偵測能正確執行。 </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> 作為 User-Agent 的替代項目，使某些瀏覽器 (如 OperaMini) 的瀏覽器、作業系統和行動裝置偵測能正確執行。 </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> 作為 User-Agent 的替代項目，使某些瀏覽器 (如 OperaMini) 的瀏覽器、作業系統和行動裝置偵測能正確執行。 </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> 作為 User-Agent 的替代項目，使某些瀏覽器 (如 OperaMini) 的瀏覽器、作業系統和行動裝置偵測能正確執行。 </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> 作為 User-Agent 的替代項目，使某些瀏覽器 (如 OperaMini) 的瀏覽器、作業系統和行動裝置偵測能正確執行。 </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> 作為用來識別作業系統的替代項目。 </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> 作為用戶端螢幕解析度的替代來源。 </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> 作為用戶端螢幕顏色深度的替代來源。 </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> 偵測在預先提取網頁的過程中提出了資料收集要求。 </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> 偵測在瀏覽器顯示網頁預覽時提出了資料收集要求。 </td> 
  </tr> 
  <tr> 
   <td> 接受 </td> 
   <td> 用以識別瀏覽器所支援的影像格式，以便我們瞭解是否需要傳回 GIF 或 WBMP 影像。 </td> 
  </tr> 
  <tr> 
   <td> 反向連結 </td> 
   <td> 在資料收集要求未傳入至查詢字串，或與查詢字串中的值不同時，作為用來取得關於該要求發自哪個頁面 URL 之資訊的備援功能。 </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> 用來尋找提出資料收集要求之用戶端的正確 IP 位址。此 IP 位址可用來產生地理區域、行動電信業者和其他報表。 </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]使用動態變數的實施可選擇讀取前述以外其他 HTTP 要求標題。

## HTTP 回應標題 {#section_A9C7035198C84037A21A8033CC408F0E}

| **標題** | **使用狀況** |
|---|---|
| Access-Control-Allow-Origin | 用以支援將樣式資料收集要求分享給我們的伺服器的跨原始來源資源。 |
| 過期 | 瀏覽器快取控制。 |
| Last-Modified | 瀏覽器快取控制。 |
| Cache-Control | 瀏覽器快取控制。 |
| Pragma | 瀏覽器快取控制。 |
| ETag | 瀏覽器快取控制。 |
| Vary | 瀏覽器快取控制。 |
| P3P | 提供資料收集要求的預設或自訂 P3P 原則。 |
| 狀態 | 包含無內容要求的「成功」或「失敗」狀態。只有在要求指定不應傳回內容時，才會使用。 |
| 原因 | 包含無內容要求之失敗狀態的原因。只有在要求指定不應傳回內容時，才會使用。 |
| 位置 | 用以將提出資料收集要求的用戶端重新導向至不同的 URL。我們用來偵測訪客 ID Cookie 設定能力的 Cookie 交握，即為一例。 |
| Content-Type | 指定傳回至用戶端的內容類型 (GIF、文字、Javascript 等)。 |
| Content-Length | 指定傳回至用戶端的內容大小。 |

> [!NOTE]在回應中可設定其他 HTTP 標題，以進行內部狀態監控。其中有部分標題可傳回至瀏覽器，但瀏覽器不一定需加以接收。
