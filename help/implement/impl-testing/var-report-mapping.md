---
description: 下表顯示用來填入 Analytics 報表的變數進行對映報告時所使用的變數。
keywords: Analytics Implementation
title: 用以報表對應的變數
topic: Developer and implementation
uuid: fd81f97d-dd1a-47d5-9157-b7932fe13490
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 用以報表對應的變數

下表顯示用來填入 Analytics 報表的變數進行對映報告時所使用的變數。

以下列出每個變數，並在旁邊列出使用該變數的報表。

<table id="table_16443E46AC0E46509F8533D26EDE1BCC"> 
 <thead> 
  <tr> 
   <th class="entry"> 變數 </th> 
   <th class="entry"> 填充報表 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> s.pageName </td> 
   <td> <p>轉換報表 &gt; 路徑報表 &gt; 頁面值 </p> <p>轉換報表 &gt; 路徑報表 &gt; 登入頁面 </p> <p>轉換報表 &gt; 路徑報表 &gt; 原始登入頁面 </p> <p>流量報表 &gt; 網站流量 &gt; 頁面檢視 </p> <p>流量報表 &gt; 網站流量 &gt; 每小時獨特訪客 </p> <p>流量報表 &gt; 網站流量 &gt; 每日獨特訪客 </p> <p>流量報表 &gt; 網站流量 &gt; 每月獨特訪客 </p> <p>流量報表 &gt; 網站流量 &gt; 每年獨特訪客 </p> <p>流量報表 &gt; 訪客資料 &gt; 關鍵訪客檢視的頁面 </p> <p>流量報表 &gt; 區段 &gt; 最受歡迎頁面 </p> <p>路徑報表 &gt; 頁面 &gt; 頁面摘要 </p> <p>路徑報表 &gt; 頁面 &gt; 頁面值 </p> <p>路徑報表 &gt; 頁面 &gt; 最受歡迎頁面 </p> <p>路徑報表 &gt; 頁面 &gt; 重新載入 </p> <p>路徑報表 &gt; 頁面 &gt; 頁面點按次數 </p> <p>路徑報表 &gt; 頁面 &gt; 頁面逗留時間 </p> <p>路徑報表 &gt; 登入與退出 &gt; 登入頁面 </p> <p>路徑報表 &gt; 登入與退出 &gt; 退出頁面 </p> <p>路徑報表 &gt; 登入與退出 &gt; 退出連結 </p> <p>路徑報表 &gt; 完整路徑 &gt; 完整路徑 </p> <p>路徑報表 &gt; 完整路徑 &gt; 最長路徑 </p> <p>路徑報表 &gt; 完整路徑 &gt; 路徑長度 </p> <p>路徑報表 &gt; 完整路徑 &gt; 每次瀏覽逗留時間 </p> <p>路徑報表 &gt; 完整路徑 &gt; 單頁瀏覽 </p> <p>路徑報表 &gt; 進階分析 &gt; 上一頁 </p> <p>路徑報表 &gt; 進階分析 &gt; 下一頁 </p> <p>路徑報表 &gt; 進階分析 &gt; 上一頁面流量 </p> <p>路徑報表 &gt; 進階分析 &gt; 下一頁面流量 </p> <p>路徑報表 &gt; 進階分析 &gt; PathFinder </p> <p>路徑報表 &gt; 進階分析 &gt; 流失 </p> <p> <b>注意: </b>在前述所有的<span class="wintitle">「流量」</span>報表中 (<span class="wintitle">「最受歡迎頁面」</span>報表除外)，若未設定 <span class="wintitle">s.pageName</span> 變數，則會使用 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td> s.server </td> 
   <td> 流量報表 &gt; 區段 &gt; 最受歡迎伺服器 </td> 
  </tr> 
  <tr> 
   <td> s.pageType </td> 
   <td> 路徑報表 &gt; 頁面 &gt; 找不到頁面 </td> 
  </tr> 
  <tr> 
   <td> s.channel </td> 
   <td> <p>轉換報表 &gt; 網站路徑報表 &gt; 網站區段 </p> <p>流量報表 &gt; 區段 &gt; 最受歡迎網站區段 </p> </td> 
  </tr> 
  <tr> 
   <td> s.prop1 - s.prop20 </td> 
   <td> 流量報表 &gt; 自訂分析 &gt; 自訂分析 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.campaign </td> 
   <td> <p>轉換報表 &gt; 促銷活動 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 促銷活動 &gt; 追蹤代碼 </p> </td> 
  </tr> 
  <tr> 
   <td> s.state </td> 
   <td> 轉換報表 &gt; 訪客資料 &gt; 州 </td> 
  </tr> 
  <tr> 
   <td> s.zip </td> 
   <td> 轉換報表 &gt; 訪客資料 &gt; 郵遞區號 </td> 
  </tr> 
  <tr> 
   <td> s.events </td> 
   <td> <p>轉換報表 &gt; 購買 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 購買 &gt; 收入 </p> <p>轉換報表 &gt; 購買 &gt; 訂購 </p> <p>轉換報表 &gt; 購買 &gt; 件數 </p> <p>轉換報表 &gt; 購物車 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 購物車 &gt; 購物車 </p> <p>轉換報表 &gt; 購物車 &gt; 購物車檢視 </p> <p>轉換報表 &gt; 購物車 &gt; 購物車新增 </p> <p>轉換報表 &gt; 購物車 &gt; 購物車移除 </p> <p>轉換報表 &gt; 購物車 &gt; 結帳 </p> <p>轉換報表 &gt; 自訂事件 &gt; 自訂事件 1-20 </p> <p>轉換報表 &gt; 產品 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 產品 &gt; 交叉銷售 </p> <p>轉換報表 &gt; 產品 &gt; 類別 </p> <p>轉換報表 &gt; 促銷活動 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 客戶忠誠度 &gt; 客戶忠誠度 </p> <p>轉換報表 &gt; 銷售週期 &gt; 首次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 上次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 瀏覽次數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每日獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每月獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每年獨特客戶 </p> <p>轉換報表 &gt; 網站路徑 &gt; 頁面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.products </td> 
   <td> <p>轉換報表 &gt; 購買 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 購買 &gt; 收入 </p> <p>轉換報表 &gt; 購買 &gt; 訂購 </p> <p>轉換報表 &gt; 購買 &gt; 件數 </p> <p>轉換報表 &gt; 購物車 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 產品 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 產品 &gt; 交叉銷售 </p> <p>轉換報表 &gt; 產品 &gt; 類別 </p> <p>轉換報表 &gt; 促銷活動 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 客戶忠誠度 &gt; 客戶忠誠度 </p> <p>轉換報表 &gt; 銷售週期 &gt; 首次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 上次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 瀏覽次數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每日獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每月獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每年獨特客戶 </p> <p>轉換報表 &gt; 網站路徑 &gt; 頁面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.purchaseID </td> 
   <td> <p>轉換報表 &gt; 購買 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 購買 &gt; 收入 </p> <p>轉換報表 &gt; 購買 &gt; 訂購 </p> <p>轉換報表 &gt; 購買 &gt; 件數 </p> <p>轉換報表 &gt; 購物車 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 產品 &gt; 轉換和平均值 </p> <p>轉換報表 &gt; 產品 &gt; 交叉銷售 </p> <p>轉換報表 &gt; 客戶忠誠度 &gt; 客戶忠誠度 </p> <p>轉換報表 &gt; 銷售週期 &gt; 首次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 上次購買間隔天數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 瀏覽次數 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每日獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每月獨特客戶 </p> <p>轉換報表 &gt; 銷售週期 &gt; 每年獨特客戶 </p> <p>轉換報表 &gt; 網站路徑 &gt; 頁面值 </p> </td> 
  </tr> 
  <tr> 
   <td> s.eVar1-s.eVar20 </td> 
   <td> 轉換報表 &gt; 自訂變數 &gt; 客戶 eVar 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.linkName </td> 
   <td> 流量報表 &gt; 自訂分析 &gt; 自訂連結 </td> 
  </tr> 
  <tr> 
   <td> s.hier1 - s.hier5 </td> 
   <td> 流量報表 &gt; 階層 &gt; 階層 1-5 </td> 
  </tr> 
 </tbody> 
</table>

