---
title: 轉換舊版Report Builder活頁簿
description: 瞭解如何轉換舊版以Report Builder為基礎的活頁簿，以使用新的Report Builder。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: d7832dc56eb680f57a6875cf32e29fd5a8858098
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# 轉換舊版Report Builder活頁簿

在改用新的Report Builder功能時，您可以快速轉換目前以Report Builder為基礎的舊版活頁簿（舊版活頁簿），以使用新的Report Builder [資料區塊](create-a-data-block.md)功能。

>[!IMPORTANT]
>
>在轉換舊版活頁簿之前，請先複製每個活頁簿並重新命名一個版本。 這可確保您隨時擁有原始舊版活頁簿的副本（需要時）。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [轉換活頁簿](https://video.tv.adobe.com/v/3446193?captions=chi_hant&quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


>[!NOTE]
>
>若要轉換舊版活頁簿，您必須先設定[新的Report Builder](/help/analyze/report-builder/report-builder-setup.md)。


## 開啟舊版活頁簿

若要開啟舊版活頁簿，您可以：

* 直接從您的本機電腦或網路開啟舊版活頁簿。 在Excel中開啟舊版活頁簿時：

   1. 從Excel帶狀圖列選取![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**。
   1. 選取&#x200B;**[!UICONTROL 登入]**&#x200B;並登入Report Builder。
   1. 然後[轉換舊版活頁簿](#convert-a-workbook)。

* 從&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;的[排程](report-builder-hub.md)索引標籤開啟已排程的舊版活頁簿。 若要這麼做：

   1. 開啟Excel，然後從Excel功能區列選取![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**。

   1. 選取&#x200B;**[!UICONTROL 登入]**&#x200B;並登入Report Builder。

   1. 在&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;中選取[排程](report-builder-hub.md)。
   1. 選取&#x200B;**[!UICONTROL 舊版]**&#x200B;標籤。 索引標籤會列出舊版以Report Builder為基礎的排程活頁簿。

      ![舊版工作台](assets/upgrade-legacy-schedule.png)

   1. 從清單中選取![SelectBox](/help/assets/icons/SelectBox.svg)您要轉換的排程活頁簿，然後選取![下載](/help/assets/icons/Download.svg)。 活頁簿會下載並在Excel的新視窗中開啟。 您現在可以[轉換舊版Report Builder活頁簿](#convert-a--workbook)。


## 轉換舊版活頁簿

若要轉換舊版活頁簿：

1. 開啟舊版活頁簿後，新的Report Builder會偵測此活頁簿是否包含[舊版Report Builder](/help/analyze/legacy-report-builder/home.md)請求。

   ![升級活頁簿提示](assets/upgrade-workbook.png){zoomable="yes"}

1. 如果找到一或多個舊版要求，請在&#x200B;**[!UICONTROL 升級活頁簿]**&#x200B;對話方塊中按一下&#x200B;**[!UICONTROL 升級]**&#x200B;以升級活頁簿。

   >[!NOTE]
   >
   >您必須個別升級每個請求。 不支援大量升級。


1. 若您升級，會出現&#x200B;**[!UICONTROL 警告]**&#x200B;對話方塊，提醒您變更活頁簿。 此外也鼓勵您在繼續之前，先建立舊版活頁簿的備份。

   ![升級警告](assets/upgrade-warning.png){zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續升級。

   如果升級成功，便會顯示&#x200B;**[!UICONTROL 活頁簿升級已完成]**&#x200B;通知。

   ![升級完成](assets/upgrade-complete.png)

   * 選取&#x200B;**[!UICONTROL 關閉]**&#x200B;以關閉通知，並繼續使用活頁簿處理新Report Builder的更新要求。

   * 選取「下載升級報告」**&#x200B;**&#x200B;以下載並開啟顯示升級結果的新Excel活頁簿。 如需範例，請參閱下文。

     ![Excel Report Builder升級報告活頁簿](assets/upgrade-report.png)

您現在可以[管理資料區塊](/help/analyze/report-builder/manage-reportbuilder.md)。


## 排程轉換的舊版活頁簿

您可以選擇使用您從Report Builder中心的&#x200B;**[!UICONTROL 排程]**&#x200B;索引標籤下載並開啟的舊版活頁簿的排程詳細資料。 此選項不適用於具有您從本機電腦或網路開啟之排程詳細資料的舊版活頁簿。

1. 排程活頁簿。 若要使用舊版排程來排程轉換的舊版活頁簿：

   * 從Report Builder中心選取&#x200B;**[!UICONTROL 傳送活頁簿]**，或
   * 從Report Builder中&#x200B;**[!UICONTROL 排程]**&#x200B;索引標籤可用的&#x200B;**[!UICONTROL 活頁簿]**&#x200B;索引標籤中選取&#x200B;**[!UICONTROL 排程活頁簿]**。

1. 系統提供您使用舊版活頁簿的排程詳細資料，作為預設排程設定。

   ![移轉舊版活頁簿排程](assets/upgrade-legacy-schedule-convert.png)

   * 選取&#x200B;**[!UICONTROL 使用]**&#x200B;以使用舊版排程詳細資料。 排程詳細資料已預先填入[傳送活頁簿](schedule-reportbuilder.md#schedule-a-workbook)介面。
   * 選取&#x200B;**[!UICONTROL 不要使用]**&#x200B;以不使用舊版排程詳細資料。
   * 選取「**[!UICONTROL 取消]**」進行取消。

   選取&#x200B;**[!UICONTROL 從未來使用中移除舊版中繼資料]**，以便未來不再為此活頁簿使用舊版排程詳細資料。


## 不支援舊版Report Builder功能 {#unsupported}

新的Report Builder已不再提供某些舊版Report Builder功能

* 即時請求。

* 路徑/流失報告。

* 排程報表的FTP選項。

* 訪客量度。下列量度已轉換為&#x200B;*不重複訪客*，即使報表結果可能不是完全相符： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`和`visitorsyearly`。 此轉換也適用於`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。
