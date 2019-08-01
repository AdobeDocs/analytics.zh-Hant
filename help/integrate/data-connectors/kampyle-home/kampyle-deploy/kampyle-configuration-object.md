---
description: 完成整合精靈後，您必須將整合設定物件部署至您的Web屬性。
seo-description: 完成整合精靈後，您必須將整合設定物件部署至您的Web屬性。
seo-title: 部署整合設定物件
solution: Analytics
title: 部署整合設定物件
uuid: e951c864-2914-4324-9f03-5069d4f75d99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploy the Integration Configuration Object{#deploy-the-integration-configuration-object}

完成整合精靈後，您必須將整合設定物件部署至您的Web屬性。

在許多情況下，部署整合設定物件最簡單的方法是將它包含在您的Adobe Analytics部署程式碼中。

>[!NOTE]
>
>如果您使用Adobe TagManager或動態標籤管理來部署Adobe Analytics，可以透過該工具輕鬆新增整合設定物件。

1. Navigate to the **[!UICONTROL Resources]** &gt; **[!UICONTROL Support]** tab of the integration.
1. Download and save the **[!UICONTROL Kampyle Integration Code (JS)]** resource. 程式碼看起來類似於：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用下列其中一種方法部署程式碼：

       |**您可以使用Adobe TagManager或動態標籤管理。**|使用標籤管理介面來新增代碼。|
       |---|---|
       | **In all other cases** | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |
   
