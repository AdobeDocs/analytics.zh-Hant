---
description: 瞭解不同的儲存選項，包括自動儲存、另存新檔、另存為範本，以及開啟舊版。
title: 儲存專案
feature: Workspace Basics
role: Business Practitioner, Administrator
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
translation-type: tm+mt
source-git-commit: cfeb681805108c9d9422d88b6d7146d0eb186204
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 54%

---

# 儲存專案

若要儲存您對專案所做的變更，請前往 Analysis Workspace 的&#x200B;**[!UICONTROL 「專案」]**&#x200B;功能表。工作區也會在某些情況下自動儲存專案。

## 儲存專案選項 {#Save}

您可以在&#x200B;**[!UICONTROL 「專案」]**&#x200B;功能表底下執行不同的儲存操作，取決於您日後要如何存取分析。

| 動作 | 說明 |
|---|---| 
| **[!UICONTROL 儲存]** | 儲存專案的變更項目。如果專案已共用，專案的收件者也會看到變更項目。當您第一次儲存專案時，系統會提示您為專案提供名稱、（選用）說明和新增（選用）標籤。 |
| **[!UICONTROL 一併儲存附註]** | 在您的專案儲存之前，請新增專案中變更的附註。 備注與項目版本一起儲存，可供[!UICONTROL Project] > [!UICONTROL 開啟舊版]下的所有編輯器使用。 |
| **[!UICONTROL 另存新檔]** | 建立專案的複本。原始專案不受影響。 |
| **[!UICONTROL 另存為範本]** | 將專案儲存為[自訂範本](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)，您的組織可在&#x200B;**[!UICONTROL 「專案 > 新增」]**&#x200B;下使用 |

![](assets/save-project.png)

## 自動儲存 {#Autosave}

現有專案 (即之前至少已儲存一次的專案) 每兩分鐘會自動儲存至您的本機電腦一次。從未儲存過的新專案目前不會自動儲存。

有些情況可能會導致您遠離未儲存的專案變更項目，進而產生不同的可用操作。

### 開啟另一個 Analysis Workspace 專案

Adobe 提供在離開頁面前儲存的選項。離開現有專案後，自動儲存的本機副本即會刪除。

![](assets/existing-save.png)

### 離開或關閉索引標籤

瀏覽器會警告未儲存的變更將遺失。您可以選擇離開或取消。

![](assets/browser-image.png)

### 瀏覽器當機或工作階段逾時

對於&#x200B;**現有**&#x200B;項目，返回工作區後，您將看到&#x200B;**項目恢復**&#x200B;模式。 選取「是」會從自動儲存的本機復本中還原專案。 若選擇「否」，則會刪除自動儲存的本機副本，並開啟上次使用者儲存的專案版本。

![](assets/project-recovery.png)

若為從未儲存的&#x200B;**新**&#x200B;專案，未儲存的變更無法復原。

## 開啟先前版本 {#previous-version}

>[!NOTE]
>
>先前的專案版本目前為有限版本。

要開啟項目的舊版：

1. 前往&#x200B;**[!UICONTROL Project]** > **[!UICONTROL 開啟舊版]**

   ![](assets/previous-versions.png)

1. 檢視舊版可用的清單。
   [!UICONTROL 除了「注] 釋」外，還顯示「時間戳記」  和「編輯器」(Editor)  在「編輯器」(  Saved)時添加了它們。沒有備注的版本會儲存90天；含備注的版本會儲存1年。
1. 選擇舊版，然後按一下&#x200B;**[!UICONTROL Load]**。
然後載入舊版並附上通知。 在您按一下**[!UICONTROL Save]**&#x200B;之前，舊版不會成為項目的當前保存版本。 如果您從載入的版本導覽，當您返回時，將會看到專案的上一個儲存版本。
