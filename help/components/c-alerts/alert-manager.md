---
description: 管理警報。
title: 警報管理器概觀
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 86580b3c149c0feb1d70d9ba197cf0810e472586
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# 警報管理器

您可以在警報管理器中管理現有警報。您可以對警報執行各種管理任務，例如標記、重新命名、刪除等。

警報管理器的結構與 [區段管理員](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-hant)及[計算量度管理員](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=zh-hant)非常相似。

![](assets/alert-manager.png)

## 建立警報

若要從警報管理器建立警報：

1. 請選取「**[!UICONTROL 元件]** > **[!UICONTROL 警報]**」，以存取 Adobe Analytics 中的警報管理器。

   ![](assets/alert-manager.png)

1. 請選取「[!UICONTROL **新增**]」(或者，如果您沒有任何現有警報，則選取「[!UICONTROL **建立新警報**]」)。

1. 請選取與您要建立之警報的相對應警報類型：

   * [!UICONTROL **分析資料警報**]：警報會在資料出現異常事件時通知您。

     如果選取此選項，請繼續「[建立警報](/help/components/c-alerts/alert-builder.md)」，以了解更多有關建立警報的詳細資訊。

   * [!UICONTROL **伺服器呼叫使用量警報**]：此警報用於通知您伺服器呼叫耗用量和諾使用量資料存在超額風險或發生超額情況。

     如果選取此選項，請繼續「[伺服器呼叫使用量警報](/help/admin/admin/c-server-call-usage/scu-alerts.md)」。

     >[!NOTE]
     >
     >您必須是 Analytics 管理員或具有伺服器呼叫使用權限的使用者，才能存取伺服器呼叫使用量。

## 管理現有警報

您可以對現有警報執行各種動作，例如標記、重新命名、刪除等等。

若要警報管理器中管理現有警報：

1. 請選取「**[!UICONTROL 元件]** > **[!UICONTROL 警報]**」，以存取 Adobe Analytics 中的警報管理器。

   ![](assets/alert-manager.png)

1. 請選取一個或多個您要管理的警報。

   ![](assets/alert-manager-tasks.png)

1. 在動作列中，選取下列任一選項：

   | 動作 | 函數 |
   |---------|----------|
   | [!UICONTROL **標記**] | 將標記套用至警報。這可協助您組織警報以方便使用。 |
   | [!UICONTROL **刪除**] | 刪除此警報。 |
   | [!UICONTROL **重新命名**] | 重新命名此警報。 |
   | [!UICONTROL **核准**] | 將警報標記為已核准。 |
   | [!UICONTROL **複製**] | 建立警報副本 (重複)。 |
   | [!UICONTROL **停用**] | 停用目前啟用的警報。 |
   | [!UICONTROL **啟用**] | 啟用目前停用的警報。 |
   | [!UICONTROL **續約**] | 續約警報的到期日。這將延長警報到期日，無論其原始到期日為何，將從您選取此選項之日起延長 1 年。 |
   | [!UICONTROL **匯出為 CSV**] | 將警報匯出為 .CSV 檔案。 |

## 編輯警報

若要編輯現有警報：

1. 請選取「**[!UICONTROL 元件]** > **[!UICONTROL 警報]**」，以存取 Adobe Analytics 中的警報管理器。

   ![](assets/alert-manager.png)

1. 在「[!UICONTROL **標題和說明**]」欄中選取警報名稱。

1. 視需要編輯警報。

   下列是編輯警報時您可以執行的一些動作：

   * 新增警報至其他報告套裝
   * 新增或修改說明
   * 修改時間詳細程度
   * 修改收件者
   * 修改到期日
   * 修改量度和篩選器

1. 請選取「[!UICONTROL **儲存**]」。

## 設定資料欄

您可以透過設定顯示的欄位來設定警報管理器中每個警報顯示的資訊。

若要設定警報管理器中的可見欄：

1. 在 Adobe Analytics 中，選取「**[!UICONTROL 元件]**」索引標籤，然後選取「**[!UICONTROL 警報]**」。

1. 在警報管理器中，選取「**自訂欄**」圖示 ![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您想要在警報管理器中顯示的欄。

   可使用下列欄：

   | 欄標題 | 說明 |
   |---|---|
   | 標題和說明 | 在警報產生器中提供這些值。若要編輯標題和說明，請選取標題連結以開啟警報產生器。 |
   | 我的最愛 | 在每個警報旁會顯示星形圖示，讓您將警報標記為我的最愛。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | 類型 | 顯示警報為分析資料警報還是伺服器呼叫使用量警報。 |
   | 已啟用 | 顯示目前警報是啟用或停用。 |
   | 報告套裝 | 指出上次儲存警報的報告套裝。 |
   | 所有者 | 指出警報的擁有者。如果您不是管理員，您只能查看自己所擁有或已與您共用的量度。 |
   | 標記 | 顯示由您或與您共用警報之人員套用至警報的標記。 |
   | 到期日 | 顯示警報設定到期的日期和時間。 |
   | 日期已修改 | 指出上次修改警報的日期。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


