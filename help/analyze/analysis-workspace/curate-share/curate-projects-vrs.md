---
title: VRS 與專案組織
description: 瞭解如何組織虛擬報表套裝元件和專案
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# VRS 與專案組織

基本上，組織專案或虛擬報表套裝 (VRS) 時，您會篩選掉元件，使對象只看見您希望他們使用的專案/VRS 元件 (維度、量度、區段及日期範圍)。

>[!NOTE]
>
>產品描述檔是控制使用者可檢視之元件的主要機制。 They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). 組織為次要的篩選器。

我們最近改善了組織體驗。下列為&#x200B;**[!UICONTROL 「全部顯示」]**按鈕所顯示內容的概述，以及不同組織體驗和權限層級中可用的已組織元件:

| 組織類型 | 管理員 | 非管理員專案擁有者 | 非管理員 |
|---|---|---|---|
| 已組織的 VRS | 所有未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 元件 |
| 已組織的專案 | 所有未經組織的專案元件 | 所有未經組織的專案元件 | 此角色擁有或已與其共享之未經組織的專案元件 |
| 已組織 VRS 中的已組織專案 | 所有未經組織的元件 (如下所示) **[!UICONTROL Non-Curated Project Components]**and**[!UICONTROL  Non-Curated VRS Components]** | 此角色擁有或已與其共用之所有未經組織的專案元件和未經組織的 VRS 元件 | 此角色擁有或已與其共享之未經組織的 VRS 與專案元件 |

>[!IMPORTANT]
>
>VRS組織一律在專案組織之前套用。 這表示即使您策劃的專案包含某些元件，當策劃的VRS不包含這些元件時，也會將其篩選掉。
