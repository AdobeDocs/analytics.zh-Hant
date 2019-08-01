---
description: 完成整合精靈後，您必須將整合代碼部署至Adobe Analytics部署代碼(s_ code)。
seo-description: 完成整合精靈後，您必須將整合代碼部署至Adobe Analytics部署代碼(s_ code)。
seo-title: 部署整合代碼
title: 部署整合代碼
uuid: b3fbda0b-4ed3-4967-84ee-6c66564606e7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

完成整合精靈後，您必須將整合代碼部署至Adobe Analytics部署代碼(s_ code)。

>[!NOTE]
>
>如果您使用Adobe TagManager或動態標籤管理部署Adobe Analytics，您可以使用其中一個工具輕鬆新增整合代碼。

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration.

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. 如果Adobe Analytics部署代碼中尚未顯示「整合模組」，請加入「整合模組」。For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. 使用下列其中一種方法部署程式碼：

   * 使用Adobe TagManager或動態標籤管理來新增代碼。
   * 或者，將程式碼傳送至負責更新Adobe Analytics部署代碼的組織資源。

>[!IMPORTANT]
>
>請務必在開發/測試環境中測試此整合的部署，然後再將它部署至生產環境。

