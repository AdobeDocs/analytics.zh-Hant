---
description: 「尋找方法」頁面可識別不同的尋找方法報告如何接收網站上轉換成功事件的評價。例如，如果某個訪客透過搜尋引擎進入您的網站並進行購買，則由「尋找方法」指定搜尋引擎接收反向連結評價的方式。
title: 尋找方法
feature: Admin Tools
role: Admin
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 97%

---

# 尋找方法

「尋找方法」頁面可識別不同的尋找方法報告如何接收網站上轉換成功事件的評價。例如，如果某個訪客透過搜尋引擎進入您的網站並進行購買，則由「尋找方法」指定搜尋引擎接收反向連結評價的方式。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 尋找方法]**

## 尋找方法說明 {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 您要修改的尋找方法 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置 </td> 
   <td colname="col2"> 指定如何套用反向連結的評分。支援的配置選項包括： <p> <span class="uicontrol">最近 (最後一個)：</span>將所有評分給予最後一個反向連結 (預設)。 </p> <p> <span class="uicontrol">原始值：</span>首個反向連結獲得全部評價。 </p> <p> <span class="uicontrol">線性：</span>所有反向連結獲得相同評價。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 過期時間 </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol">瀏覽：</span>在指定的閒置時段後；通常約為 30 分鐘。 </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol">頁面檢視：</span>開啟您網站上的任何頁面之時。 </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol">分鐘：</span>閒置 1 分鐘之後。 </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol">購買：</span>購買的時候。 </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol">產品檢視：</span>訪客檢視產品網頁時。 </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol">購物車開啟：</span>訪客開啟新的線上購物車時。 </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol">購物車結帳：</span>訪客使用線上購物車結帳時。 </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol">購物車新增：</span>訪客新增產品至線上購物車時。 </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol">購物車移除：</span>訪客從線上購物車移除產品時。 </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol">購物車開啟：</span>訪客檢視線上購物車的內容時。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
> 所有「尋找方法」將在瀏覽結束時過期。如果您選擇在不同的事件 (例如，購物車結帳) 發生後過期，在瀏覽期間發生「購物車結帳」時，「尋找方法」會過期。如果「購物車結帳」未在瀏覽期間發生，則「尋找方法」仍在瀏覽結束時過期。
