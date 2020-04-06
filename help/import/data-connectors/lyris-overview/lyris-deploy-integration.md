---
description: 說明三步驟部署程序。
title: 部署整合
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 部署整合{#deploying-the-integration}

說明三步驟部署程序。

部署這項整合是一項簡單的程序，需要執行下列動作：

## 完成整合精靈{#completing-the-integration-wizard}

使用整合精靈的步驟。

若要啟用整合，您必須在 Data Connectors 介面中完成 Lyris 整合精靈。

1. 導覽至 Adobe Experience Cloud 中的 Data Connectors (前身為 Genesis) 區域。

   ![](assets/data_connectors.png)

1. 在「 **[!UICONTROL Add Integration]** Lyris HQ」下，按一下 **[!UICONTROL Activate]**。

   ![](assets/add_integration.png)

1. Under **[!UICONTROL General Settings]**, choose the desired Report Suite and provide a name for the integration.
1. Fill in all your Lyris account-related information under **[!UICONTROL Custom Values]**.

   ![](assets/general_settings.png)

1. 從下拉式功能表中選擇適當的保留 eVar 和事件。

   ![](assets/variable_mapping.png)

1. You may choose your own segments under **[!UICONTROL Your Segments]** - apart from the 3 automated Partner segments.
1. 此整合可能需要將數個資料點下載至您的 Lyris 帳戶。You may choose to give access for this under **[!UICONTROL Access Request]**.
1. Under **[!UICONTROL Data Collection]**, you can choose to have an automated or a manual solution (JavaScript Plug-in) to collect query string parameters from the landing page URL. 如果您選擇使用自動化解決方案，請為訊息 ID 和收件者 ID 輸入查詢字串參數。如需 JavaScript 外掛程式，請聯絡您的 Adobe 顧問。

   ![](assets/data_collection.png)

1. 您可以選擇自動產生 Lyris 控制面板和書籤。

   ![](assets/dashboard_generation.png)

1. Review the integration summary and click **[!UICONTROL Activate]**.

## Lyris EmailLabs 中的設定{#configuration-within-the-lyris-emaillabs}

以下步驟說明完成精靈後需在 Lyris 中進行哪些設定。

1. 完成整合精靈後，您必須與 Lyris Professional 團隊合作，完成與 Lyris HQ 帳戶的整合並進行測試。
1. 新增 URL 查詢字串參數：確認 URL 附加字串已正確輸入至使用者介面的「組織」設定區域中。此字串應包含促銷活動層級 ID (hq_m) 和收件者層級 ID (hq_v)。

   字串 ID 的範例如下：

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >如果您套用 Lyris 的原生分析工具，*點按追蹤*&#x200B;會標記所有新增的必要變數。

## 驗證整合{#verifying-the-integration}

驗證 Lyris/Adobe Analytics 整合是否成功的步驟。

完成所有部署步驟後，可以驗證整合是否能成功傳輸資料。

>[!NOTE] 資料交換需要幾天的時間才能開始。啟用整合後，請務必與 Lyris 聯絡。

1. 在 Data Connectors 中導覽至您的 Lyris 整合。在標籤 **[!UICONTROL Support]** >下 **[!UICONTROL Integration Activity Log]**，您應該會看到事件， **[!UICONTROL Metric data imported successfully]** 例如和／或 **[!UICONTROL Classification data imported successfully]**:

   ![](assets/integration_info.png)

1. 現在，可使用適當的量度檢視您的 Lyris 訊息報表。In the Adobe Experience Cloud, select **[!UICONTROL Reports & Analytics]**.
1. 選取正確的報表套裝。
1. 在下 **[!UICONTROL Custom Conversions]**&#x200B;面，選擇 **[!UICONTROL Message ID Reports]** 並選擇 **[!UICONTROL Message ID/Message Name]**。

## 查詢字串參數外掛程式代碼{#query-string-param-plug-in-code}

顯示要與 Adobe Analytics 搭配使用的 Lyris 外掛程式代碼。

>[!NOTE] 請務必先在 Adobe Analytics 的「管理工具」中保留必要的 eVar，然後再使用下列程式碼。知道已保留哪些 eVar 後，請以相關的 eVar 取代 eVarN。例如 eVar10。

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```
