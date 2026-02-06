---
title: 管理資料摘要工作
description: 瞭解如何管理資料摘要中的個別作業。 瀏覽介面、使用篩選和搜尋，以及尋找欄定義。
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 11%

---

# 管理資料摘要作業

作業是指輸出壓縮檔案的個別工作。 它們係經由摘要所建立與管理。

您可以檢視每個資料摘要、重新傳送作業或重新處理作業的工作歷史記錄。

## 檢視資料摘要的工作記錄

您可以檢視指定資料摘要的資料摘要作業清單，以及每個作業的相關資訊。

若要檢視資料摘要的工作歷史記錄：

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 在右上角選取九宮格圖示，然後選取&#x200B;[!UICONTROL **「Analytics」**]。

1. 在頂端導覽列中，前往&#x200B;[!UICONTROL **「管理」**]>[!UICONTROL **「資料摘要」**]。

   系統會顯示您有權存取之所有報表套裝的資料摘要。 或者，如果尚未設定摘要，頁面會顯示&#x200B;**[!UICONTROL 建立資料摘要]**&#x200B;按鈕。

   ![資料摘要管理員](assets/data-feed-manager.png)

1. 選取包含您要檢視之工作的資料摘要旁的核取方塊，然後選取&#x200B;[!UICONTROL **工作歷史記錄**]。

   將顯示資料摘要作業歷史記錄，其中包含可用欄中每個作業的相關資訊。

1. （選擇性）若要調整表格中的可見欄，請選取右上角的欄圖示![欄圖示](assets/customize-columns-icon.png)，然後在「自訂表格」對話方塊中，選取您要檢視的每一欄，並取消選取您要隱藏的每一欄。

   可使用下列欄：

   * **[!UICONTROL 要求期間開始]**

   * **[!UICONTROL 要求期間結束]**

   * **[!UICONTROL 已排程]**

   * **[!UICONTROL 已啟動]**

   * **[!UICONTROL 已完成]**

   * **[!UICONTROL 執行#]**

   * **[!UICONTROL 狀態]**

   * **[!UICONTROL 錯誤碼]**

   * **[!UICONTROL 錯誤訊息]**

## 重新傳送資料摘要工作

當您重新傳送資料摘要工作時，會再次傳送資料摘要檔案，且含有與檔案最初傳送時相同的資料和處理。 或者，您可以[重新處理資料摘要工作](#reprocess-data-feed-jobs)。

若要重新傳送一或多個資料摘要工作：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **管理員**] > [!UICONTROL **資料摘要**]。

1. 選取資料摘要旁的核取方塊，其中包含您要重新傳送的工作，然後選取&#x200B;[!UICONTROL **工作歷史記錄**]。

1. 選取一或多個資料摘要工作旁的核取方塊，然後選取&#x200B;**[!UICONTROL 重新傳送]**。<!-- What does the status need to be? Error, ... -->

   ![重新處理資料摘要工作](assets/data-feed-job-resend.png)

## 重新處理資料摘要工作

當您重新處理資料摘要工作時，它會重新處理資料摘要工作的來源資料，並隨重新處理的資料再次傳送。 或者，您可以[重新傳送資料摘要工作](#resend-data-feed-jobs)。

若要重新處理一或多個資料摘要工作：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **管理員**] > [!UICONTROL **資料摘要**]。

1. 選取資料摘要旁的核取方塊，其中包含您要重新處理的工作，然後選取&#x200B;[!UICONTROL **工作歷史記錄**]。

1. 選取一或多個資料摘要工作旁的核取方塊，然後選取&#x200B;**[!UICONTROL 重新處理]**。<!-- What does the status need to be? Error, ... -->

   ![重新處理資料摘要工作](assets/data-feed-job-reprocess.png)
