---
description: 內部URL篩選器可識別您視為網站內部的反向連結。 它們有助於流量來源報表填入資料，並有助於篩選內部流量。
title: 內部 URL 篩選器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---


# 內部 URL 篩選器

內部URL篩選器可讓您識別您視為網站內部的反向連結。 它們有助於流量來源報表填入資料，並有助於篩選內部流量。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報告套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 內部URL篩選器]**

反向連結或反向連結頁面通常是訪客進入您網站的頁面。 若要避免資料產生偏差，您可以篩選掉內部反向連結。 依賴內部URL篩選器的維度包含[反向連結](/help/components/dimensions/referrer.md)、[反向連結網域](/help/components/dimensions/referring-domain.md)、[行銷管道](/help/components/dimensions/marketing-channel.md)以及其他流量來源維度。

[行銷管道處理規則](../marketing-channels/mc-proc-rules.md)會提供[!UICONTROL 符合內部URL篩選器]（儘可能符合規則條件）。

>[!IMPORTANT]
>
>某些報表套裝預設會設定句點(`.`)的內部URL篩選器。 當此篩選器存在時，所有流量都會分類為內部。 移除此篩選器並取代為一個或多個所需的內部網域後，反向連結報表才能運作。

* 檢視&#x200B;**[!UICONTROL 目前篩選器]**&#x200B;區段下的所有現有篩選器。
* 使用&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;區段下的文字方塊新增篩選器，然後按一下&#x200B;**[!UICONTROL 新增]**。

篩選器會針對完整URL使用&#x200B;**contains**&#x200B;邏輯來運作。 Adobe建議在建立篩選器時省略通訊協定(`https://`)和子網域，除非需要將來自不同子網域的流量當作外部流量。
