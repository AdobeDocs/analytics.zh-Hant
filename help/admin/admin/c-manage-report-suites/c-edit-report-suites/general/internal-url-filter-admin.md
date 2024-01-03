---
description: 內部 URL 篩選器可識別您認為是屬於網站內部的反向連結。這可協助流量來源報表填入資料並協助篩選內部流量。
title: 內部 URL 篩選器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# 內部 URL 篩選器

內部URL篩選器可讓您識別您視為網站內部的反向連結。 這可協助流量來源報表填入資料並協助篩選內部流量。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 內部URL篩選器]**

反向連結或反向連結頁面通常是訪客進入您網站的頁面。若要避免造成資料偏差，您可以篩選掉內部反向連結。依賴內部URL篩選器的Dimension包括 [反向連結](/help/components/dimensions/referrer.md)， [反向連結網域](/help/components/dimensions/referring-domain.md)， [行銷管道](/help/components/dimensions/marketing-channel.md)和其他流量來源維度。

[行銷管道處理規則](../marketing-channels/c-rules.md) 提供&quot;[!UICONTROL 符合內部URL篩選器]」作為可能的規則條件。

>[!IMPORTANT]
>
>某些報表套裝有一個句點(`.`)預設設定。 當此篩選器存在時，所有流量都會分類為內部。 移除此篩選器並取代為一個或多個所需的內部網域後，反向連結報表才能運作。

* 檢視下的所有現有篩選器 **[!UICONTROL 目前的篩選器]** 區段。
* 使用「 」下的文字方塊新增篩選器 **[!UICONTROL 新增篩選器]** 區段，然後按一下 **[!UICONTROL 新增]**.

篩選器的操作方式 **包含** 邏輯與完整URL。 Adobe建議省略通訊協定(`https://`)和子網域建立篩選器時，除非需要將來自不同子網域的流量作為外部流量。
