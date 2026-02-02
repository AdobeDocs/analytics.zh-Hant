---
title: 使用Report Builder排程活頁簿
description: 瞭解如何使用Report Builder中的排程功能。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 8b6d8a4efec59b693a69984880d8f374ae0cfabc
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 26%

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

若要排程活頁簿：

1. 在Report Builder中心選取「**[!UICONTROL 排程]**」以建立排程，讓您將活頁簿Excel檔案(.xlsx)自動散發給個人或群組。

   ![選取[排程]按鈕以建立排程。](./assets/schedule.png){zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 排程活頁簿]**&#x200B;或![新增](/help/assets/icons/Add.svg)以建立新的排程活頁簿。

   ![排程活頁簿視窗。](./assets/schedule-workbook.png){zoomable="yes"}

   排程窗格會顯示活頁簿的一些預先定義資訊，例如活頁簿名稱和上次修改活頁簿的日期。

### 檔案

在&#x200B;**[!UICONTROL 檔案]**&#x200B;區段中，您提供檔案型別、名稱和密碼的詳細資訊，以保護檔案。

![排程窗格。](./assets/schedule-pane.png){zoomable="yes"}

1. 使用![TableSelect](/help/assets/icons/TableSelect.svg)選取目前的活頁簿（如果尚未選取）。

1. （選擇性）輸入&#x200B;**[!UICONTROL 檔案名稱]**。

   活頁簿檔案名稱預設為活頁簿的名稱，但您可以視需要變更檔案名稱。

1. 選取&#x200B;**[!UICONTROL 檔案型別]**。

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   當您選取&#x200B;**[!UICONTROL CSV]**&#x200B;時，請注意，排程活頁簿會以zip附件的形式傳送。 有些企業電子郵件管理部門可能會封鎖包含壓縮附件的電子郵件。 您會看到相應的警告。

1. (選用) 選取&#x200B;**[!UICONTROL 「將時間戳記附加到檔案名稱」]**。

   您可以在檔案名稱附加時間戳記，以識別活頁簿的更新日期。時間戳記有助於檢視在特定日期傳送的活頁簿版本。 選取後，您可在以下兩者之間選擇：

   * **[!UICONTROL ISO日期格式]**，這會導致`YYYY-MM-DD`附加至檔案名稱。
   * **[!UICONTROL ISO日期格式+時間戳記]**，結果會將`YYYY-MM-DD_HH-MM-SS`附加至檔案名稱。

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. 在&#x200B;**[!UICONTROL 密碼保護活頁簿]**&#x200B;中輸入密碼。 有效的密碼至少需要8個字元、一個數字和一個特殊字元。 選取![VisibilityOff](/help/assets/icons/VisibilityOff.svg)以顯示密碼，選取![Visibility](/help/assets/icons/Visibility.svg)隱藏密碼（預設）。


### 電子郵件

在&#x200B;**[!UICONTROL 電子郵件]**&#x200B;區段中，您提供電子郵件的收件者、主旨和說明。

![排程電子郵件設定](assets/schedule-email.png){zoomable="yes"}

1. 輸入&#x200B;**收件者**。您可以輸入組織中可辨識的人員名稱。 或者，您可以輸入組織外人員的電子郵件地址。

1. 輸入電子郵件的&#x200B;**主旨**&#x200B;以及收件者的說明。主旨預設為活頁簿檔案名稱，但您可以視需要修改主旨。您可以在說明區段中新增詳細資料。

1. 您可以選擇在&#x200B;**[!UICONTROL 描述]**&#x200B;文字區域中輸入描述。


### 排程

在&#x200B;**[!UICONTROL 排程]**&#x200B;區段中，您可以定義排程，以將活頁簿的電子郵件傳送給收件者。

![排程定義](assets/schedule-enable.png){zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 顯示排程選項]**&#x200B;以定義排程。

1. 輸入從&#x200B;**[!UICONTROL 開始的]**&#x200B;開始日期。 或者，選取![行事曆](/help/assets/icons/Calendar.svg)以從行事曆中挑選開始日期。

1. 在&#x200B;**[!UICONTROL 結束日期]**&#x200B;中輸入結束日期。 或者，選取![行事曆](/help/assets/icons/Calendar.svg)以從行事曆中挑選結束日期。

1. 選取&#x200B;**[!UICONTROL 頻率]**。 視選取的頻率而定，您會有其他選項。 請參閱下表。

   | 頻率 | 選項 |
   |---|---|
   | **[!UICONTROL 每小時傳送]** | 輸入&#x200B;**[!UICONTROL 每小時傳送一次的值]**。 |
   | **[!UICONTROL 每日傳送]** | 選取&#x200B;**[!UICONTROL 每日頻率]**： **[!UICONTROL 每天傳送]**、**[!UICONTROL 每個工作日傳送]**&#x200B;或&#x200B;**[!UICONTROL 自訂頻率]**。<br/>如果您選取&#x200B;**[!UICONTROL 自訂頻率]**，請輸入&#x200B;**[!UICONTROL 每隔]**&#x200B;天傳送的值。 |
   | **[!UICONTROL 每週傳送]** | 輸入&#x200B;**[!UICONTROL 每週]**&#x200B;傳送的值。 並選取一週的&#x200B;**[!UICONTROL 天]**。 |
   | **[!UICONTROL 按一週的某天每月傳送]** | 選取&#x200B;**[!UICONTROL 星期]**&#x200B;和&#x200B;**[!UICONTROL 星期]**。 |
   | **[!UICONTROL 每月依月份日期傳送]** | 從&#x200B;**[!UICONTROL 於本月]**&#x200B;的當天傳送中選取一個值。 |
   | **[!UICONTROL 每年依月份日期]**&#x200B;傳送 | 選取&#x200B;**[!UICONTROL 一週中的某天]**，選取一個月中的&#x200B;**[!UICONTROL 周]**，然後選取一年中的&#x200B;**[!UICONTROL 每月]**。 |
   | **[!UICONTROL 依特定日期每年傳送]** | 選取&#x200B;**[!UICONTROL 月份]**，並從&#x200B;**[!UICONTROL 於當月的這個日期傳送]**&#x200B;中選取值。 |

### 傳送

若要傳送活頁簿：

* 如果您尚未使用&#x200B;**[!UICONTROL 顯示排程選項]**&#x200B;定義排程，請選取&#x200B;**[!UICONTROL 立即傳送]**，以立即透過電子郵件傳送活頁簿。
* 如果您已使用&#x200B;**[!UICONTROL 顯示排程選項]**&#x200B;定義排程，請選取&#x200B;**[!UICONTROL 依排程傳送]**，以使用您定義的排程透過電子郵件傳送活頁簿。

在這兩種情況下，您都會在Report Builder中心底部看到確認快顯通知。

若要取消傳送活頁簿，請選取&#x200B;**[!UICONTROL 取消]**。

## 管理安排的活頁簿

如需有關管理已排程活頁簿的資訊，請參閱[管理已排程活頁簿](/help/analyze/report-builder/manage-reportbuilder.md)。




<!--

## Schedule a workbook

Use the Schedule button in the Report Builder hub to quickly create a schedule so that you can automatically distribute a workbook Excel file (.xlsx) to an individual or a group.

1. Click the Schedule button in the Report Builder hub.

    ![Click the Schedule button to create a schedule.](./assets/schedule-button.png){width="55%"}

1. Click Schedule Workbook or the plus button in the upper-left to create a new scheduled workbook.

    ![The Schedule workbooks window.](./assets/schedule-workbook.png){width="55%"}

    The scheduling pane displays some pre-defined information about the workbook such as the workbook name and the last date that the workbook was modified.

    ![The scheduling pane.](./assets/schedule-pane.png){width="55%"}

1. (Optional) Enter a file name.

    The workbook file name defaults to the name of the workbook but you can change this if you want. If you\'re sending the same workbook to multiple audiences and you want to name it something a little bit more friendly for a certain audience, you can change the name.

1. (Optional) Select **Append time-stamp to file name**.

    You can append a timestamp to the file name to identify the date the workbook was updated. This is helpful to quickly see which version of a workbook was sent on a specific date. The **Filename preview** shows how the workbook file name will appear in the email when the workbook is distributed. The time-stamp format is YYYY-MM-DD.

1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){width="55%"}

1. Enter **Recipients**. You can enter the name of a person that is recognized in your organization, or you can enter an email address of a person inside or outside of your organization.

1. Enter the **Subject** of the email and a description for your recipients. The subject defaults to the workbook file name but you can modify the subject if needed. You can add details in the description section.

    ![Enter a subject in the Subject field.](./assets/recipients-subject.png){width="55%"}

1. Set up the scheduling options to set the date and time that you want the workbook emailed to your recipients.

    Choose the start and end date and time frames. This can be today's date or a date in the future.

    Choose the **Frequency** from the drop-down menu. You can set the frequency to be hourly, daily, weekly, monthly, or yearly on a specific day. For example, you can set up a schedule to send the workbook on the first Sunday night of the month so that your recipients will have the email in their inbox first thing on Monday morning.

    ![Select the frequency to schedule your report.](./assets/frequency.png){width="55%"}

1. After you set the schedule, click **Send on schedule**.

    ![Click Send on schedule.](./assets/send-on-schedule.png){width="55%"}

    You see a confirmation toast at the bottom of the Report Builder hub and the scheduled workbook is listed under the Workbooks tab.

    ![Confirmation toast](./assets/confirmation-toast.png){width="55%"}

## Schedule a converted workbook {#converted}

1. Schedule a [converted](/help/analyze/report-builder/convert-workbooks.md) legacy workbook.

   A pop up appears, asking if you want to use the scheduling metada from the legacy workbook to create a new scheduled task. 

1. If you select **[!UICONTROL Use]**, Report Builder automatically fills in the legacy scheduling information. 

1. Ensure that this information is correct and schedule. 

1. If you want to send the workbook on a different schedule, schedule a completely fresh scheduled task. 


## Send the workbook one-time only

You can also send out the workbook only once.

1. Un-check **Show scheduling options** 

    ![Click Un-check Show scheduling options to send out a workbook one time.](./assets/send-now.png){width="40%"}

1. Click **Send Now**.

## Manage scheduled workbooks

For information about managing workbooks that are already scheduled, see [Manage scheduled workbooks](/help/analyze/report-builder/manage-schedules-reportbuilder.md).

-->