---
description: 說明三步驟部署程序。
title: 部署整合
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: ht
source-git-commit: a3aa8feb937e2a1f40c498aa4e143de21cf26b86

---


# 部署整合{#deploying-the-integration}

說明三步驟部署程序。

部署這項整合是一項簡單的程序，需要執行下列動作：

## 完成整合精靈{#completing-the-integration-wizard}

使用整合精靈的步驟。

若要啟用整合，您必須在 Data Connectors 介面中完成 Lyris 整合精靈。

1. 導覽至 Adobe Experience Cloud 中的 Data Connectors (前身為 Genesis) 區域。

   ![](assets/data_connectors.png)

1. 在&#x200B;**[!UICONTROL 新增整合]**&#x200B;下方的 Lyris HQ 底下，按一下&#x200B;**[!UICONTROL 「啟用」]**。

   ![](assets/add_integration.png)

1. 在&#x200B;**[!UICONTROL 一般設定]**&#x200B;下方，選擇所需的報表套裝，並替整合提供名稱。
1. 在&#x200B;**[!UICONTROL 自訂值]**&#x200B;下方填寫與 Lyris 帳戶相關的所有資訊。

   ![](assets/general_settings.png)

1. 從下拉式功能表中選擇適當的保留 eVar 和事件。

   ![](assets/variable_mapping.png)

1. 除了 3 個自動化合作夥伴區段外，您也可以在&#x200B;**[!UICONTROL 您的區段]**&#x200B;底下選擇自己的區段。
1. 此整合可能需要將數個資料點下載至您的 Lyris 帳戶。您可以在&#x200B;**[!UICONTROL 存取要求]**&#x200B;底下選擇授予此項的存取權。
1. 在&#x200B;**[!UICONTROL 資料收集]**&#x200B;下方，您可以選擇使用自動化或手動解決方案 (JavaScript 外掛程式)，從登陸頁面 URL 收集查詢字串參數。如果您選擇使用自動化解決方案，請為訊息 ID 和收件者 ID 輸入查詢字串參數。如需 JavaScript 外掛程式，請聯絡您的 Adobe 顧問。

   ![](assets/data_collection.png)

1. 您可以選擇自動產生 Lyris 控制面板和書籤。

   ![](assets/dashboard_generation.png)

1. 檢閱整合摘要，然後按一下&#x200B;**[!UICONTROL 「啟用」]**。

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

> [!NOTE] 資料交換需要幾天的時間才能開始。啟用整合後，請務必與 Lyris 聯絡。

1. 在 Data Connectors 中導覽至您的 Lyris 整合。在&#x200B;**[!UICONTROL 「支援]**&#x200B;標籤 > **[!UICONTROL 整合活動記錄」]**&#x200B;下方，應該會看到&#x200B;**[!UICONTROL 量度資料匯入成功]**&#x200B;和/或&#x200B;**[!UICONTROL 分類資料匯入成功]**&#x200B;這類事件：

   ![](assets/integration_info.png)

1. 現在，可使用適當的量度檢視您的 Lyris 訊息報表。在 Adobe Experience Cloud 中，選取&#x200B;**[!UICONTROL 「Reports &amp; Analytics」]**。
1. 選取正確的報表套裝。
1. 在&#x200B;**[!UICONTROL 自訂轉換]**&#x200B;下方，選取&#x200B;**[!UICONTROL 「訊息 ID 報表」]**，再選擇&#x200B;**[!UICONTROL 「訊息 ID/訊息名稱」]**。

## 查詢字串參數外掛程式代碼{#query-string-param-plug-in-code}

顯示要與 Adobe Analytics 搭配使用的 Lyris 外掛程式代碼。

> [!NOTE] 請務必先在 Adobe Analytics 的「管理工具」中保留必要的 eVar，然後再使用下列程式碼。知道已保留哪些 eVar 後，請以相關的 eVar 取代 eVarN。例如 eVar10。

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
