---
title: 如何在Adobe Analytics中使用Report Builder排程活頁簿
description: 瞭解如何使用Report Builder中的排程功能
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 9ece9f6fcebdf308b6218aa50ab78af4f75ee8e7
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 69%

---

# 透過電子郵件共用排程活頁簿

>[!NOTE]
>
>除了排程活頁簿以透過電子郵件共用（如本節所述）之外，您還可以排程要匯出至雲端目的地的活頁簿，如[排程要匯出至雲端目的地的活頁簿](/help/analyze/report-builder/report-builder-export.md)所述。

儲存活頁簿並完成分析後，您就可以使用排程功能輕鬆與團隊中的其他人共用活頁簿。「排程」功能可讓您建立排程，自動更新活頁簿中的資料，並透過電子郵件將 Excel 活頁簿 .xlsx 檔案作為附件，在特定日期和時間傳送給您指定的客群。設定排程可讓收件者定期自動更新。您也可以使用排程功能來傳送一次活頁簿，而不排程自動更新。

您可以為單一活頁簿建立多個排程。例如，您可以每天將活頁簿傳送給您的團隊，也可以建立兩個不同的排程，每週將活頁簿傳送給主管一次。

「排程」功能也可以讓您設定活頁簿的密碼保護，以及編輯先前排程的活頁簿。


>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [排程活頁簿](https://video.tv.adobe.com/v/3413079?quality=12&learn=on){target="_blank"}以取得示範影片。

>[!ENDSHADEBOX]


## 排程活頁簿

使用Report Builder中心的「排程」按鈕快速建立排程，以便將活頁簿Excel檔案(.xlsx)自動散發給個人或群組。

1. 按一下 Report Builder 中心內的「排程」按鈕。

   ![按一下[排程]按鈕以建立排程。](./assets/schedule-button.png){width="55%"}

1. 按一下「排程活頁簿」或左上角的加號按鈕，以建立新的排程活頁簿。

   ![排程活頁簿視窗。](./assets/schedule-workbook.png){width="55%"}

   排程窗格會顯示活頁簿的一些預先定義資訊，例如活頁簿名稱和上次修改活頁簿的日期。

   ![排程窗格。](./assets/schedule-pane.png){width="55%"}

1. (選用) 輸入檔案名稱。

   活頁簿檔案名稱會預設為活頁簿的名稱，但您可以視需要變更此名稱。如果您要將相同的活頁簿傳送給多個客群，而您想要將它命名為讓特定客群更好記的名稱，就可以變更名稱。

1. (選用) 選取&#x200B;**「將時間戳記附加到檔案名稱」**。

   您可以在檔案名稱附加時間戳記，以識別活頁簿的更新日期。這有助於快速查看在特定日期傳送的活頁簿版本。**檔案名稱預覽**&#x200B;會顯示分發活頁簿時，活頁簿檔案名稱在電子郵件中的顯示方式。時間戳記格式為 YYYY-MM-DD。

1. (選用) 選取&#x200B;**「.zip壓縮」**&#x200B;來壓縮檔案並設定檔案的密碼保護。

   進行此選擇時，系統會提示您輸入密碼以開啟檔案。如果您對資料安全性有疑慮，並想以密碼保護活頁簿，這個方法就很有用。若要使用密碼保護檔案，就必須選取&#x200B;**「.zip壓縮」**。密碼必須至少為 8 個字元，並包含一個數字和一個特殊字元。

   ![在[密碼保護活頁簿]欄位中輸入密碼。](./assets/zip-compression.png){width="55%"}

1. 輸入&#x200B;**收件者**。您可以輸入組織中可識別的人員名稱，也可以輸入組織內外人員的電子郵件地址。

1. 輸入電子郵件的&#x200B;**主旨**&#x200B;以及收件者的說明。主旨預設為活頁簿檔案名稱，但您可以視需要修改主旨。您可以在說明區段中新增詳細資料。

   ![在[主旨]欄位中輸入主旨。](./assets/recipients-subject.png){width="55%"}

1. 設定排程選項，以設定您要透過電子郵件將活頁簿傳送給收件者的日期和時間。

   選擇開始和結束日期與時間範圍。這可以是今天的日期或未來的日期。

   從下拉式選單中選取&#x200B;**「頻率」**。您可以將頻率設定為特定日期的每小時、每日、每週、每月或每年。例如，您可以設定排程，在每個月的第一個星期日晚上傳送活頁簿，讓收件者在星期一早上第一時間就能在收件匣中看到該電子郵件。

   ![選取排程報告的頻率。](./assets/frequency.png){width="55%"}

1. 設定排程後，按一下&#x200B;**「依排程傳送」**。

   ![按一下[依排程傳送]。](./assets/send-on-schedule.png){width="55%"}

   您會在Report Builder中心底部看到確認快顯通知，而排程活頁簿會列在「活頁簿」索引標籤下方。

   ![確認快顯通知](./assets/confirmation-toast.png){width="55%"}

## 排程轉換的活頁簿 {#converted}

1. 排程[已轉換](/help/analyze/report-builder/convert-workbooks.md)的舊版活頁簿。

   系統會顯示一個快顯視窗，詢問您是否要使用舊版活頁簿中的排程中繼資料來建立新的排程工作。

1. 如果您選取&#x200B;**[!UICONTROL 使用]**，Report Builder會自動填入舊版排程資訊。

1. 請確定此資訊正確無誤，並排程。

1. 如果您要以不同的排程傳送活頁簿，請排程完全新的排程工作。


## 僅傳送活頁簿一次

您也可以只傳送活頁簿一次。

1. 取消勾選&#x200B;**「顯示排程選項」**

   &lbrack;按一下![取消核取[顯示排程選項]，一次傳送活頁簿。](./assets/send-now.png){width="40%"}

1. 按一下&#x200B;**「立即傳送」**。

## 管理安排的活頁簿

如需有關管理已排程活頁簿的資訊，請參閱[管理已排程活頁簿](/help/analyze/report-builder/manage-schedules-reportbuilder.md)。
