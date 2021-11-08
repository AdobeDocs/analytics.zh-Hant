---
description: 智慧型警報系統可更精細地控制警報，並整合異常偵測與警報系統。
title: 智慧型警報
uuid: ac8c9710-d245-46e9-b906-32d3bb0013c0
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 38fb7ec39495b2b8cde4955bd1b3c1d3487632c3
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 88%

---

# 智慧型警報

智慧型警報系統可更精細地控制警報，並整合異常偵測與警報系統。

以下是影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## 概觀 {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>智慧型警報僅供 Adobe [!DNL Analytics] Prime 與 Adobe [!DNL Analytics] Ultimate 的客戶使用。

智慧型警報可讓您

* 根據異常 (90％、95％、99%、99.75% 或 99.9% 臨界值；％ 變化；以上/以下) 建立警報。
* 預覽警報觸發的頻率.
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結。
* 建立在單一警報中擷取多個量度的「堆疊」警報。

警報系統的元件包括：警報產生器、警報管理器、警報預覽和更好的內容感知存取，以建立警報。 舊的警報系統使用者介面不再可用，但我們會移轉警報。部分舊式警報功能 [不再可用](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html?lang=zh-Hant).

取得「警報產生器」有四種方式：

* 在 Analysis Workspace 中使用下列快速鍵：

   `ctrl (or cmd) + shift + a`
* 直接前往「警報產生器」：「**[!UICONTROL Workspace]** > **[!UICONTROL 元件]** > **[!UICONTROL 新增警報]**」。
* 選取一或多個自由表格行項目、以滑鼠右鍵按一下並選取&#x200B;**[!UICONTROL 「從選取範圍建立警報」]**。如此會開啟「警報產生器」並從表格套用的適當量度和篩選器預先填入產生器。接著您可以視需要編輯警報。

   ![](assets/create-alert-from-selection.png)

* 在 [!UICONTROL Reports &amp; Analytics] 報表中，前往&#x200B;**[!UICONTROL 「更多]** > **[!UICONTROL 新增警報」]**。如此會開啟新的「警報產生器」，並從報表套用的適當量度和篩選器預先填入產生器。接著您可以視需要編輯警報。

   ![](assets/add-alert.png)

## 常見問答：系統如何計算及觸發警報 {#section_1F3B1DAF21784306953B49AAD4C3DCAB}

% 臨界值代表標準差。例如，95% = 2 標準差與 99% = 3 標準差。 依您選擇的時間詳細程度而定，[不同模式](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)會用於計算各資料點距離基準有多遠 (多少標準差)。若您設定較低的臨界值 (例如 90%)，您收到異常警報的次數就會比設定較高臨界值 (99%) 時多。我們特別導入 99.75% 與 99.99% 以用於每小時詳細程度的臨界值，因此不會觸發那麼多的異常警報。

<table id="table_B3AA85E1DE3543DCA34966A52E3CE4AB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>問：警報的異常偵測能多早判斷出資料異常？</b> </p> </td> 
   <td colname="col2"> <p>培訓期間會依選擇的詳細程度而有所不同。請參閱<a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md">異常偵測</a>所使用的統計技術，以取得詳細資訊。摘要如下： </p> 
    <ul id="ul_4F8C2A41F06C498DBF5E7AE5DE803773"> 
     <li id="li_E246091A3F1E484C8444AF4052FCA784">每月 = 15 個月 + 去年的相同範圍 </li> 
     <li id="li_CC014FB38AE1492B9647E990C29BFB3C">每週 = 15 週 + 去年的相同範圍 </li> 
     <li id="li_2517EE2097534324BE9C1B54CD181A62">每天 = 35 天 + 去年的相同範圍 </li> 
     <li id="li_710BC8B009354542AA4962A59A646099">每小時 = 336 小時 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：如果我只希望在行為狀況突然減少或增加時收到警報，是否適合使用異常功能？還是我需要使用絕對值？</b> </p> </td> 
   <td colname="col2"> <p>使用絕對值仍會觸發突然減少或增加的警報。您無法獨立隔離突然減少或增加的警報。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：我是否能將警報設定為只在一天中的特定時段觸發 (例如只在營業時間觸發，不在非營業時間觸發)？</b> </p> </td> 
   <td colname="col2"> <p>目前沒辦法。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：我能否取得包含虛線的「預期值」表格 (或某種顯示相關數值的輸出資料)？</b> </p> </td> 
   <td colname="col2"> <p>使用 Workspace 時不行。但您可以使用 Report Builder 做到這點 (請觀看此影片：<a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html?lang=zh-Hant"  >Report Builder 中的異常偵測</a>)。 </p> <p>請留意，Report Builder 使用的是較簡單的異常偵測方式。此方式是使用固定 30 天培訓期，固定 95％ 間隔。 </p> </td> 
  </tr> 
 </tbody> 
</table>
