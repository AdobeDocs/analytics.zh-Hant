---
description: 在Adobe Analytics部署Kampyle資料連接器。
title: 部署整合
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
exl-id: ac8e1f30-cefe-448a-bec6-cda58ee51025
source-git-commit: 4078d0be92c8ccd639e408e7372a5636938cad00
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 45%

---

# 部署整合{#deploying-the-integration}

部署此整合的簡單程式包括完成Adobe整合精靈、部署外掛程式碼(JavaScript)以及驗證整合。

## 完成 Adobe 整合精靈{#complete-the-adobe-integration-wizard}

若要啟動整合，請完成「資料連接器」介面中的設定精靈。

1. 登入 [!DNL Adobe Experience Cloud].
1. 按一下「**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 資料連接器]**」。
1. 啟動 Kampyle 整合精靈。
1. 選取所需的報表套裝，並提供整合的名稱。
1. 設定下列項目：
   1. **[!UICONTROL 電子郵件地址]**:主要聯繫人的電子郵件地址。
   1. **[!UICONTROL 說明]** （可選）:此整合設定的說明。
   1. **[!UICONTROL Kampyle Key]**:在Kampyle應用程式中，在 **[!UICONTROL Feedback Form]** >  **[!UICONTROL Feedback Form Customization（意見表>意見表自訂）下尋找此]**&#x200B;索引鍵。
   1. **[!UICONTROL 追蹤伺服器]**:您用來追蹤Adobe Analytics資料的追蹤伺服器值。
   1. **[!UICONTROL 追蹤伺服器安全]**:如果您的追蹤伺服器對於安全/https流量不同，請在此處提供該設定。
1. 設定下列&#x200B;**[!UICONTROL 變數對應]**&#x200B;項目：
   1. **[!UICONTROL Kampyle Feedback ID]**:從報表套裝中選取可用的eVar變數
   1. **[!UICONTROL 回饋等級]**:從報表套裝中選取可用的成功事件（鍵入「計數器」）。
   1. **[!UICONTROL 意見項目]**:從報表套裝中選取可用的成功事件（鍵入「計數器」）。
   1. **[!UICONTROL 評等意見]**:從報表套裝中選取可用的成功事件（鍵入「計數器」）。
1. 核取方塊以自動建立 Kampyle 整合控制面板 (建議)。
1. 檢閱所有設定項目，然後按一下&#x200B;**[!UICONTROL 「立即啟用」]**。

## 部署整合設定物件{#deploy-the-integration-configuration-object}

完成整合精靈後，將整合設定物件部署至您的Web屬性。 在許多情況下，部署整合設定物件最簡單的方式，就是將物件加入您的 Adobe Analytics 部署程式碼中。

>[!NOTE]
>
>如果您使用Adobe Experience Platform Launch，可透過該工具輕鬆新增整合設定物件。

1. 導覽至整合的&#x200B;**[!UICONTROL 「資源]** > **[!UICONTROL 支援」]**&#x200B;標籤。
1. 下載並儲存 **[!UICONTROL Kampyle 整合程式碼 (JS)]** 資源。程式碼看起來類似：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用下列其中一種方法部署代碼：

   * 用Adobe Experience Platform Launch。
   * 將程式碼傳送至維護您Adobe Analytics部署的組織資源。

## 驗證整合{#verify-the-integration}

驗證整合是否透過完成兩項檢查成功傳輸資料。

### 整合活動記錄 {#section-0472df9180db4f218db5f6040cab07af}

導覽至&#x200B;**[!UICONTROL 「支援]** > **[!UICONTROL 整合活動記錄」]**，檢視 Adobe Experience Cloud 中的 Kampyle 整合設定。在&#x200B;**[!UICONTROL 「資料輸入」]**&#x200B;標籤下方，應該會看到指出分類資料已成功匯入的項目。

>[!NOTE]
>
>成功部署後24小時內通常會出現記錄項目。

![整合活動記錄](assets/integration_activity_log.png)

### Adobe 報表資料 {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

導覽至適當功能表結構內的 Kampyle 報表，使用 Adobe Analytics 檢視 Kampyle 意見報表。

>[!NOTE]
>
> 假設整合式意見表單正在主動接收提交內容，報表資料應會在部署成功後 24 到 48 小時內顯示。

![Adobe報告資料](assets/adobe_reporting_data.png)
