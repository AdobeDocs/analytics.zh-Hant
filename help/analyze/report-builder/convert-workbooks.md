---
title: 如何將您的舊版Report Builder活頁簿轉換為資料區塊
description: 說明如何將您的舊式請求轉換為資料區塊
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: cf1b64479690cf5bdfdc8d9ba08879d0e0886611
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# 將舊版Report Builder活頁簿轉換為資料區塊

在採用新Report Builder技術時，您可以快速將目前的舊版活頁簿轉換為Javascript活頁簿。

>[!IMPORTANT]
>
>複製每個活頁簿並重新命名一個版本，然後再進行轉換。 如此一來，您仍可擁有原始活頁簿的復本（需要時）。

>[!VIDEO](https://video.tv.adobe.com/v/3434957/?quality=12&learn=on)

1. 依照](/help/analyze/report-builder/report-builder-setup.md)的指示進行[設定新Report Builder。

1. 開啟Excel，然後按一下右上方的Adobe Report Builder圖示。

1. 按一下「**[!UICONTROL 登入]**」並登入Report Builder。

1. Report Builder增益集偵測到此活頁簿是否包含[舊版Report Builder](/help/analyze/legacy-report-builder/home.md)要求。

   ![升級活頁簿提示](assets/upgrade_workbook.png)

1. 如果找到一或多個舊版要求，請按一下[升級] ****&#x200B;以升級活頁簿。

   >[!NOTE]
   >
   >您必須個別升級每個請求。 不支援大量升級。


1. 升級時，系統會顯示警告訊息，提醒您變更活頁簿。 此外也鼓勵您在繼續之前，先建立舊版活頁簿的備份。

   ![升級警告](assets/upgrade_warning.png)

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續升級。

   如果升級成功，會顯示下列完成通知：

   ![升級完成](assets/upgrade_complete.png)

1. （選擇性）按一下&#x200B;**[!UICONTROL 下載升級報告]**。 此報表包含每個已升級資料區塊的狀態。

您現在可以[管理資料區塊](/help/analyze/report-builder/manage-reportbuilder.md)。


## 新Report Builder中不支援舊版Report Builder功能 {#unsupported}

將舊版Report Builder的功能與新Report Builder增益集比較時，有些舊版功能已無法使用：

- 即時請求

- 路徑/流失報告

- 排程報表的FTP選項

- 訪客量度。 下列量度將全部轉換為「不重複訪客」，即使報表結果可能不是完全相符： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`以及`visitorsyearly`。 這也適用於`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。

## 排程轉換的活頁簿 {#schedule}

請參閱排程文章中的[排程轉換的活頁簿](/help/analyze/report-builder/schedule-reportbuilder.md)。