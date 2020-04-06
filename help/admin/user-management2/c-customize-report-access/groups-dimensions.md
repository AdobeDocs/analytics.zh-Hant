---
description: 在粒度層級自訂使用者存取，包括 eVar、流量報表、解決方案報表和路徑報表。
keywords: groups;permissions
subtopic: Users and groups
title: 自訂維度權限
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 自訂維度權限

>[!IMPORTANT]使用者和產品管理功能即將移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。輪到您移轉使用者時，Adobe 會通知您。After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

在粒度層級自訂使用者存取，包括 eVar、流量報表、解決方案報表和路徑報表。

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT] 目前部分維度無法提供權限。這些維度包括：行動書籤長度、行動裝置號碼、行動 DRM、行動資訊服務、行動 Java VM、行動郵件裝飾、行動網路通訊協定、行動作業系統、行動「對講機」。
>
>這些維度適用於所有使用者，不論其他權限為何。

此頁面上的設定與頁面上選取的報表套裝相 [!UICONTROL Define User Groups] 關。

![](assets/permissions-dimensions.png)

瞭解權限的「維度」類別的下列資訊。

* eVar 1-250會個別授權。
* 所有流量報表都是維度。
* 視訊和行動報表以及其他 Analytics 解決方案報表 (Experience Manager、Advertising Cloud、Social 等) 均屬維度。
* 如果使用者擁有父維度的存取權，則可使用路徑報表。
* 自訂群組中的所有目前維度和量度都會自動移轉至新類別。 如果現有群組已啟用量度，預設會為其提供所有新取得權限的維度（eVar和內容感知）和量度。
* Classifications Importer (即原 SAINT) 權限：存取類別是由存取類別基準的[變數](https://marketing.adobe.com/resources/help/zh_TW/reference/c_classifications.html)所決定。

如需詳細資訊，請參 [閱權限變更的常見問題](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html)。

**自訂維度**

下列項目是您可以存取的維度。

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVar </a> </p> </td> 
   <td colname="col2"> <p>eVar 1-250會個別授權。 eVar是自訂轉換變數，您可用來在自訂報表中劃分轉換成功度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/sc/implement/props_eVars.html"> Prop </a> </p> </td> 
   <td colname="col2"> <p>Prop 為自訂流量變數。 </p> <p>請參閱 Analytics 實作中的<a href="https://marketing.adobe.com/resources/help/zh_TW/sc/implement/props_eVars.html">流量 Prop 和轉換 eVar</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/sc/implement/hierN.html"> 階層 </a> </p> </td> 
   <td colname="col2"> <p> 階層 (hierN) 變數會決定某個頁面在您的網站階層或頁面結構中的所在位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> 與「清單屬性」功能類似，清單變數允許在相同的影像要求中使用多個值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準 </p> </td> 
   <td colname="col2"> <p>指Analytics中的標準（現成可用）維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/analytics/activitymap/"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map 報告維度：Activity Map 頁面；Activity Map 連結；Activity Map 地區；各地區的 Activity Map 連結；Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/mobile/"> 行動 </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>這項合作夥伴整合已不再進行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_TW/sc/appmeasurement/hbvideo/nielsen-partnership.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>這項合作夥伴整合已不再進行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 社交 </p> </td> 
   <td colname="col2"> <p>未使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>
