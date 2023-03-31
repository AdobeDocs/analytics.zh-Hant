---
description: 內部 URL 篩選器可識別您認為是屬於網站內部的反向連結。這可協助流量來源報表填入資料並協助篩選內部流量。
title: 內部 URL 篩選器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---


# 內部URL篩選器

內部URL篩選器可讓您識別您視為網站內部的反向連結。 這可協助流量來源報表填入資料並協助篩選內部流量。

反向連結或反向連結頁面通常是訪客進入您網站的頁面。若要避免造成資料偏差，您可以篩選掉內部反向連結。報告會從以下報告中排除已篩選的反向連結：[反向連結](/help/components/dimensions/referrer.md)維度、[反向連結網域](/help/components/dimensions/referring-domain.md)維度，以及其他流量來源維度。

## 檢視現有的內部URL篩選器

>[!NOTE]
>
>有些報表套裝具有句點(.)的內部URL篩選器 預設設定。 當此篩選器存在時，所有流量都會分類為內部。 反向連結報表要到期間(.) 篩選器。

若要檢查為報表套裝設定的內部URL篩選器： <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. 選擇 **[!UICONTROL 管理]** > **[!UICONTROL 報表套裝]** 存取「報表套裝管理器」。

1. 選取您要檢查哪些內部URL篩選器已設定的報表套裝，然後選取 **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 內部URL篩選器]**.

   所有現有篩選器都列在 [!UICONTROL **目前的篩選器**] 區段。

## 新增內部URL篩選器至報表套裝

1. 選擇 **[!UICONTROL 管理]** > **[!UICONTROL 報表套裝]** 存取「報表套裝管理器」。

1. 選取您要新增內部URL篩選器的報表套裝，然後選取 **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 內部URL篩選器]**.

1. 在提供的欄位中新增篩選區段，開始輸入您要篩選之頁面的URL，然後選取 [!UICONTROL **新增**].

   您新增的URL現在會顯示在 [!UICONTROL **目前的篩選器**] 區段。
