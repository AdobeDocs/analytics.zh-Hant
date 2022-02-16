---
description: 在Adobe Analytics建立用於資料收集的基本容器
title: 建立報表套裝
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 63%

---

# 建立報表套裝

報表套裝是 Adobe Analytics 用來提取報表的獨立資料單位。組織可以有許多報表套裝，每個報表套裝都包含不同的資料集。雖然過去使用者較重視個別產生報表，但如今使用單一報表套裝已變得更具優勢了。介紹 [虛擬報告套件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) 而報告時間處理允許管理員建立您自己的資料子集，從而允許管理員靈活地獲取全局資料和特定於站點的資料。

本文旨在為系統級管理員或Adobe Analytics管理員準備資料收集。

## 先決條件

[Adobe Analytics第一份管理指南](/help/admin/admin-console/first-admin-guide.md):確保系統級管理員已通過Experience CloudAdmin Console授予您訪問Adobe Analytics的權限。

## 建立報表套裝 {#create-report-suite}

1. 按一下&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理]** > **[!UICONTROL 報表套裝」]**。
1. 按一下&#x200B;**[!UICONTROL 「新增]** > **[!UICONTROL 報表套裝」]**。
1. 若要複製報表套裝設定，請在範本清單中選取預先定義的範本，或將現有報表套裝當作[範本](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)使用。

   >[!NOTE]
   >
   >只能複製設定，不能複製資料。如果由客戶服務複製設定，您需要提供客戶服務針對有關風險之免責聲明的書面確認。請參閱[不會從來源報表套裝複製的設定值](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)以瞭解詳細資訊。

1. 填寫[「新報表套裝」](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)中所述的欄位。
1. 按一下&#x200B;**[!UICONTROL 「建立報表套裝」]**。

報表套件ID的最大長度為40位元組。 報表套件友好名稱的最大長度為255位元組。

## 疑難排解

**登入 Experience Cloud 後，Analytics 圖示會變灰。**

這表示您的帳戶尚未取得 Analytics 的正確權限。請與您組織的系統層級管理員合作，確保您所屬的設定檔具備存取 Adobe Analytics 的足夠權限。

**登入 Adobe Analytics 後，「歡迎使用 Adobe Analytics」快顯視窗和下拉式清單已經消失。**

確保已通過 [Experience Cloud](https://experience.adobe.com)，而不是通過my.omniture.com。 透過 my.omniture.com 登入的使用者無法使用報表套裝設定精靈。

## 後續步驟

[建立Adobe Analytics標籤屬性 ](/help/implement/launch/create-analytics-property.md):建立區域以管理分析實施
