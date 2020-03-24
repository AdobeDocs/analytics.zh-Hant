---
description: 簡單的 3 步驟程序即可部署此整合。
title: 部署整合
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: ht
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# 部署整合{#deploying-the-integration}

簡單的 3 步驟程序即可部署此整合。

## 完成整合精靈{#completing-the-integration-wizard}

若要啟用整合，您必須在 Data Connectors 介面中完成 Selligent 整合精靈。

1. 導覽至 Adobe Experience Cloud 中的 Data Connectors 區域。

   ![](assets/selligent-data_connectors.png)

1. 在&#x200B;**[!UICONTROL 新增整合]**&#x200B;下方，將 Selligent 外掛程式拖放至 Adobe Experience Cloud 中。

   ![](assets/selligent-add_integration.png)

   隨即會開啟 Selligent Data Connector 整合。

1. **整合設定**：選擇所需的報表套裝，並在&#x200B;**[!UICONTROL 整合設定]**&#x200B;下方提供整合的名稱。

1. 在&#x200B;**[!UICONTROL 自訂值]**&#x200B;下方，填入與 Selligent 帳戶相關的所有資訊。

   ![](assets/selligent-general_settings.png)

1. **變數對應**：從下拉式功能表中選擇適當的保留 eVar 和事件：

   ![](assets/selligent-variables.png)

1. **資料設定**：除了 3 個自動化&#x200B;**[!UICONTROL 合作夥伴]**&#x200B;區段外，您也可以在&#x200B;**[!UICONTROL 您的區段]**&#x200B;底下選擇自己的區段。

1. 此整合可能需要將數個資料點下載至您的 Selligent 帳戶。您可以在&#x200B;**[!UICONTROL 存取要求]**&#x200B;底下選擇授予相同項目的存取權。
1. 在&#x200B;**[!UICONTROL 資料收集]**&#x200B;下方，選擇自動化或手動解決方案 (JavaScript 外掛程式)，用於從登陸頁面 URL 收集查詢字串參數。如果您選擇自動化解決方案，請為訊息 ID 和收件者 ID 輸入查詢字串參數，兩者分別為 MID 和 RID。如需 JavaScript 外掛程式，請聯絡您的 Adobe 顧問。
1. **報表設定**：在&#x200B;**[!UICONTROL 產生控制面板]**&#x200B;下方勾選方塊，讓 Selligent 自動為您產生控制面板。

   ![](assets/selligent-report_settings.png)

1. 檢閱整合摘要，然後按一下&#x200B;**[!UICONTROL 「啟用」]**。

## Selligent 中的設定{#configuration-within-selligent}

在 Adobe Analytics 內啟用整合後，Selligent 端就會啟用自動設定。

追蹤器已建立，可追蹤每封電子郵件。如果您想要將其限制在特定網域，請更新追蹤器設定。

強烈建議您將 URL 中 Adobe Analytics 的追蹤參數移至最前面。這將確保 Adobe 處理規則會從登陸頁面 URL 擷取參數。如下方所示勾選核取方塊，即可啟用追蹤。

![](assets/selligent-tracker.png)

## 驗證整合{#verifying-the-integration}

完成所有部署步驟後，可以驗證整合是否能成功傳輸資料。

資料交換需要幾天的時間才能開始。啟用整合後，請務必與 Selligent 聯絡。

### 整合活動記錄 {#section-927e270495db479fba9578915d9ae9c9}

在 Data Connectors 中導覽至您的 Selligent 整合。在&#x200B;**[!UICONTROL 「支援」]**&#x200B;標籤下方，應該會看到「量度資料匯入成功」和/或「分類資料匯入成功」這類事件：

![](assets/selligent-verifying.png)

### 報表資料 {#section-ebd481a162324e66bd6dc8cb4b8d2424}

使用適當的量度檢視您的 Selligent 訊息報表。

1. 前往 Adobe Experience Cloud 下方的 Report &amp; Analytics。
1. 選取正確的報表套裝。
1. 在&#x200B;**[!UICONTROL 自訂轉換]**&#x200B;下方，選取&#x200B;**[!UICONTROL 「訊息 ID 報表」]**，再選擇&#x200B;**[!UICONTROL 「訊息 ID/訊息名稱」]**。
