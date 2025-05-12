---
description: 在 Adobe Analytics 中建立資料收集的基本容器
title: 建立報告套裝
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 8c0e88a22928d79599ab0a0ad3efc8159712d739
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 98%

---

# 建立報告套裝

報告套裝是 Adobe Analytics 用來提取報告的獨立資料單位。組織可以有許多報告套裝，每個報告套裝都包含不同的資料集。雖然過去使用者較重視個別產生報告，但如今使用單一報告套裝已變得更具優勢了。[虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant#virtual-report-suites)和報告時間處理的引進讓管理員能夠建立自己的資料子集，進而靈活地取得全域和網站特有資料。

本文的適用對象為系統層級管理員或 Adobe Analytics 管理員，目的在方便這些人員準備資料收集。

## 先決條件

[Adobe Analytics 優先管理員指南](/help/admin/admin-console/first-admin-guide.md)：確保系統層級管理員已透過 Experience Cloud Admin Console 授與您 Adobe Analytics 的存取權限。

## 建立報告套裝 {#create-report-suite}

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報告套裝]**。
1. 按一下&#x200B;**[!UICONTROL 新增報表套裝]**。
1. 選取預先定義的範本或現有的報告套裝，以當成[範本](/help/admin/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)使用。

   >[!NOTE]
   >
   >只能複製設定，不能複製資料。如果由客戶服務複製設定，您需要提供客戶服務針對有關風險之免責聲明的書面確認。請參閱「[並非從來源報告套裝複製的設定](/help/admin/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)」，了解詳細資訊。

1. 填寫[「新報告套裝」](/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)中所述的欄位。
1. 按一下&#x200B;**[!UICONTROL 「建立報告套裝」]**。

報告套裝 ID 的長度上限為 40 個位元組。 報告套裝易記名稱的長度上限為 255 個位元組。

## 疑難排解

**登入 Experience Cloud 後，Analytics 圖示會變灰。**

這表示您的帳戶尚未取得 Analytics 的正確權限。請與您組織的系統層級管理員合作，確保您所屬的設定檔具備存取 Adobe Analytics 的足夠權限。

## 後續步驟

[建立 Adobe Analytics 標記屬性](/help/implement/launch/create-analytics-property.md)：建立用來管理您的 Analytics 實作的區域。
