---
description: 管理警報。
title: 警報管理器概觀
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# 警報管理器

您可以在「警報管理員」中管理現有警報。 您可以對警示執行各種管理工作，例如標籤、重新命名、刪除等等。

警示管理員的結構相當類似於[區段管理員](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hant)和[計算量度管理員](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=zh-Hant)。

![](assets/alert-manager.png)

## 建立警報

若要從「警示管理員」建立警示，請執行下列動作：

1. 選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警報]**&#x200B;以存取Adobe Analytics中的警報管理器。

   ![](assets/alert-manager.png)

1. 選取「[!UICONTROL **新增**]」（或如果您沒有任何現有的警示，則選取「[!UICONTROL **建立新警示**]」）。

1. 選取對應至您要建立之警示的警示型別：

   * [!UICONTROL **Analytics資料警示**]：當您的資料中發生異常事件時通知您的警示。

     如果您選取此選項，請繼續[建立警示](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md)，以取得有關建立警示的詳細資訊。

   * [!UICONTROL **伺服器呼叫使用量警報**]：通知您伺服器呼叫使用量和承諾使用量資料有超額風險或發生超額的警報。

     如果您選取此選項，請繼續[伺服器呼叫使用量警報](/help/admin/admin/c-server-call-usage/scu-alerts.md)。

     >[!NOTE]
     >
     >您必須是Analytics管理員或具有伺服器呼叫使用量許可權的使用者，才能存取伺服器呼叫使用量。

## 管理現有警報

您可以對現有警報執行各種動作，例如標籤、重新命名、刪除等。

若要在「警報管理員」中管理現有警報：

1. 選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警報]**&#x200B;以存取Adobe Analytics中的警報管理器。

   ![](assets/alert-manager.png)

1. 選取一或多個您要管理的警示。

   ![](assets/alert-manager-tasks.png)

1. 在動作列中，選取下列任一選項：

   | 動作 | 函數 |
   |---------|----------|
   | [!UICONTROL **標記**] | 將標籤套用至警報。 這可協助您組織警報以方便使用。 |
   | [!UICONTROL **刪除**] | 刪除警示。 |
   | [!UICONTROL **重新命名**] | 重新命名警報。 |
   | [!UICONTROL **核准**] | 將警報標示為「已核准」。 |
   | [!UICONTROL **副本**] | 建立警示的復本（重複）。 |
   | [!UICONTROL **停用**] | 停用目前啟用的警示。 |
   | [!UICONTROL **啟用**] | 啟用目前停用的警示。 |
   | [!UICONTROL **續約**] | 更新警示到期日。 如此一來，到期日將從您選取此選項之日算起延長1年，無論原始到期日為何。 |
   | [!UICONTROL **匯出至 CSV**] | 將警報匯出至.CSV檔案。 |

## 編輯警報

若要編輯現有警示，請執行下列動作：

1. 選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 警報]**&#x200B;以存取Adobe Analytics中的警報管理器。

   ![](assets/alert-manager.png)

1. 在&#x200B;[!UICONTROL **標題和說明**]&#x200B;欄中選取警示名稱。

1. 視需要編輯警報。

   以下是編輯警報時您可以進行的部分操作：

   * 將警報新增至其他報表套裝
   * 變更擁有者
   * 更新篩選器
   * 更新到期日

1. 編輯警示，然後選取&#x200B;[!UICONTROL **儲存**]。

## 設定欄

您可以設定顯示的資料欄，以設定「警示管理員」中每個警示顯示的資訊。

若要在「警報管理員」中設定可見欄：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;標籤，然後選取&#x200B;**[!UICONTROL 警示]**。

1. 在警示管理員中，選取&#x200B;**自訂欄**&#x200B;圖示![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您要顯示在警示管理員中的欄。

   可使用下列欄:

   | 欄標題 | 說明 |
   |---|---|
   | 標題和說明 | 這些值會在警報產生器中提供。 若要編輯標題和說明，請選取標題連結以開啟警報產生器。 |
   | 我的最愛 | 在每一個警示旁邊顯示星號圖示，讓您將警示標示為我的最愛。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | 類型 | 顯示警示是Analytics資料警示還是伺服器呼叫使用量警示。 |
   | 已啟用 | 顯示警示目前是啟用還是停用。 |
   | 報表套裝 | 指出上次將警報儲存到的目標報表套裝。 |
   | 所有者 | 指出警報的擁有者。 如果您不是管理員，就只能看見自己所擁有或已共用給您的警報。 |
   | 標記 | 顯示套用至警示的標籤，這些標籤是由您自己或與您共用警示的人員所設定。 |
   | 到期日 | 顯示警示設為到期的日期和時間。 |
   | 修改日期 | 表示上次修改警示的日期。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


