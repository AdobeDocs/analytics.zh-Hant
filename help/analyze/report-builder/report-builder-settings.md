---
title: 配置Report Builder的設定
description: 瞭解如何設定Report Builder的設定。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 28%

---

# Report Builder 設定


使用&#x200B;**設定**&#x200B;窗格配置應用程式層級的設定，例如，UI 顯示的語言或是否在離線模式中運作。這些設定會即刻套用，而且所有未來工作階段都適用相同設定，直到變更為止。

若要變更 Report Builder 設定

1. 選取&#x200B;**設定**&#x200B;圖示。

1. 變更[啟用離線模式](#off-line-mode)、[選取語言](#language)或[啟用疑難排解](#troubleshooting)。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

   顯示[取消並套用]按鈕的![Report Builder日期範圍窗格。](./assets/report-builder-settings.png){zoomable="yes"}

## 離線模式

當您在離線模式中建立和編輯資料區塊時，不會擷取資料。 相反地，會使用模擬資料，因此您可以快速工作，而不需要等候請求執行。 當您重新上線時，請選取![重新整理](/help/assets/icons/Refresh.svg) **[!UICONTROL 重新整理資料區塊]**&#x200B;或![檔案重新整理](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 重新整理所有資料區塊]**，以使用實際資料重新整理資料區塊。

如欲啟用離線模式

1. 選取![設定](/help/assets/icons/Setting.svg)。

1. 開啟&#x200B;**[!UICONTROL 啟用離線模式]**。

1. 在&#x200B;**[!UICONTROL 將量度資料]**&#x200B;顯示為欄位中輸入正整數。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。


## 語言

您可以選擇Report Builder介面的語言。 所有支援的Customer Journey Analytics語言都可供使用。

若要選取Report Builder介面中使用的語言：

1. 從&#x200B;**[!UICONTROL 語言]**&#x200B;下拉式功能表中選取語言。

1. 選取&#x200B;**套用。**

## 疑難排解

**[!UICONTROL 疑難排解記錄]**&#x200B;設定會將所有使用者端/伺服器資料記錄到本機檔案。 使用此選項來協助解決支援申請單。

若要啟用疑難排解記錄，請檢查&#x200B;**[!UICONTROL 將Report Builder請求記錄到本機檔案]**。

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->