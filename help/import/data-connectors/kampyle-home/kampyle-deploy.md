---
description: 'null'
title: 部署整合
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署此整合的簡單程式包括完成Adobe整合精靈、部署外掛程式程式碼(javascript)，以及驗證整合。

## 完成Adobe整合精靈{#complete-the-adobe-integration-wizard}

若要啟動整合，您必須在「資料連接器」介面中完成設定精靈。

1. 登入Adobe Experience Cloud。
1. 導覽至「 **[!UICONTROL 資料連接器]** 」（先前稱為Genesis）。
1. 啟動Kampyle整合精靈。
1. 選取所要的報表套裝，並提供整合的名稱。
1. 設定下列項目：
   1. **[!UICONTROL 電子郵件地址]** -主要聯絡人的電子郵件地址。
   1. **[!UICONTROL 說明]** -（選用）此整合設定的說明。
   1. **[!UICONTROL Kampyle Key]** —— 在Kampyle應用程式中，在「意見表單 **[!UICONTROL &gt;意見表]** 單自訂」下尋找此金鑰 ****。
   1. **[!UICONTROL 追蹤伺服器]** -您用來追蹤Adobe Analytics資料的追蹤伺服器（網域）設定。
   1. **[!UICONTROL 追蹤伺服器安全]** -如果您的追蹤伺服器與安全/https流量不同，請在此處提供該設定。
1. 設定下列 **[!UICONTROL 變數映射]** 項目：
   1. **[!UICONTROL Kampyle Feedback ID]** —— 從報表套裝中選取可用的eVar變數
   1. **[!UICONTROL 回饋等級]** -從您的報表套裝中選取可用的成功事件（鍵入「計數器」）。
   1. **[!UICONTROL 回饋項目]** -從您的報表套裝中選取可用的成功事件（鍵入「計數器」）。
   1. **[!UICONTROL 含等級的意見回饋]** -從報表套裝中選取可用的成功事件（鍵入「計數器」）。
1. 核取方塊，讓Kampyle整合控制面板自動為您建立（建議）。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。

## 部署整合設定物件{#deploy-the-integration-configuration-object}

完成整合精靈後，您必須將整合設定物件部署至Web屬性。

在許多情況下，部署整合設定物件最簡單的方式就是將它加入您的Adobe Analytics部署程式碼。

> [!NOTE] 如果您使用Adobe TagManager或動態標籤管理來部署Adobe Analytics，您可以透過該工具輕鬆新增整合設定物件。

1. 導覽至整 **[!UICONTROL 合的「資]** 源 **[!UICONTROL &gt;]** 支援」標籤。
1. 下載並儲存 **[!UICONTROL Kampyle整合程式碼(JS)資源]** 。 程式碼看起來類似：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用下列其中一種方法部署程式碼：
|您 **使用Adobe tagManager或動態標籤管理。** |使用標籤管理介面來新增程式碼。 ||—|—||在 **所有其他情況下** |將程式碼傳送至負責更新Adobe Analytics部署程式碼的組織資源。  |

## 驗證整合{#verify-the-integration}

完成兩項檢查，驗證整合是否成功傳輸資料。

### 整合活動記錄 {#section-0472df9180db4f218db5f6040cab07af}

導覽至「支援&gt;整合活動記錄」，以檢視Adobe Experience cloud中 **[!UICONTROL 的Kampyle]****[!UICONTROL 整合設定]**。 在「資 **[!UICONTROL 料輸入]** 」標籤下，您應該會看到指出分類資料已成功匯入的項目。

> [!NOTE] 成功部署後24小時內應會出現記錄項目。

![](assets/integration_activity_log.png)

### Adobe Reporting Data {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

使用Adobe Analytics檢視Kampyle意見報表，方法是導覽至適當功能表結構內的Kampyle報告。

> [!NOTE] 在成功部署後24-48小時內，應會顯示報告資料，前提是整合式意見表正積極接收提交。

![](assets/adobe_reporting_data.png)

