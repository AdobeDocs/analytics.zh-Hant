---
description: 說明若想啟用 Activity Map 連結收集和用戶下載，Analytics 管理員需要完成的步驟。
title: 啟用 Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 23%

---


# 啟用和啟用Activity Map

說明若想啟用 Activity Map 連結收集和用戶下載，Analytics 管理員需要完成的步驟。

## 步驟 1.啟動Activity Map {#update_code}

Activity Map模組是AppMeasurement.js、Adobe Experience Platform標籤和Web SDK (alloy.js)的一部分。 除非您更新至，否則無法收集Activity Map資料 **Web SDK 2.15.0版** 或更高，或 **Adobe Analytics標籤擴充功能1.90版** 或更高，或 **AppMeasurement 1.6版** 或更高。

+++Web SDK (Adobe Experience Platform標籤擴充功能)

1. 在Adobe Experience Platform標籤中，導覽至您要實作Analytics的屬性。 在 [!UICONTROL 擴充功能] -> [!UICONTROL Adobe Experience Platform Web SDK]，選取 **[!UICONTROL 啟用點選資料收集]** 如下方醒目提示之處。
1. 使用變更建置程式庫。
1. 將程式庫發佈到生產環境。

![](assets/web_sdk.png)

**驗證**

使用開發人員控制檯網路標籤與呼叫互動：

1. 在網站上載入開發Launch指令碼。
1. 按一下元素時，在「網路」標籤中搜尋「/ee」

   ![](assets/validation1.png)

Adobe Experience Platform Debugger：

1. 下載並安裝 [Adobe Experience Platform debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. 前往 [!UICONTROL 記錄檔] > [!UICONTROL Edge] > [!UICONTROL 連線到邊緣].

   ![](assets/validation2.jpg)

**常見問題集**

* **Network索引標籤中未觸發interact呼叫。**
收集呼叫中的點選資料收集，我們需要使用「/ee」或「collect？」進行篩選。

* **收集呼叫沒有裝載顯示。**
收集呼叫的設計方式是讓追蹤不會影響到其他網站的導覽，因此檔案解除安裝功能適用於收集呼叫。 這不會影響您的資料收集，但如果您需要在頁面上驗證，請將target = &quot;_blank&quot;新增至個別元素。 然後連結會在新標籤中開啟。

* **如何忽略PII的集合？**
在&lt;&lt;on before link中新增個別條件，然後按一下「傳送回撥>」，並傳回false以忽略這些值。 [了解更多](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant)

  程式碼範例：

  ![](assets/sample-code.png)

+++

+++手動Web SDK實施

另請參閱 [追蹤連結](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=zh-Hant) Activity Map有關如何實作連結追蹤，以及如何透過擷取 `region` HTML元素的URL值。

>[!NOTE]
>
>啟用Web SDK的連結追蹤目前會在客戶從某一頁面導覽至下一頁面時，傳送連結事件。 這與AppMeasurement的運作方式不同，並可能導致傳送至Adobe的額外計費點選。

+++

+++Analytics擴充功能(Adobe Experience Platform標籤)

在Adobe Experience Platform標籤中，導覽至您要實作Analytics的屬性。 在 [!UICONTROL 安裝擴充功能] 對話方塊，選取 **[!UICONTROL 使用Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. 下載最新Javascript程式庫以進行AppMeasurement。
前往 **[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 代碼管理器]**.
1. 透過以下方式實作 [這些指示](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=zh-Hant).

+++

## 步驟 2. 啟用 Activity Map 報表 {#enable}

您必須在報表套裝層級啟用Activity Map報表。

1. 登入 Adobe Analytics，並依序導覽至&#x200B;**[!UICONTROL 「Analytics]** > ****&#x200B;管理員 > **[!UICONTROL 報表套裝]** > 選取報表套裝 > **[!UICONTROL 編輯設定]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 報表」]**。

1. Activity Map 會將連結資料收集至 Activity Map 報表中。您必須先按一下&#x200B;**[!UICONTROL 「啟用 Activity Map 報表」]**&#x200B;啟動變數，才能真正啟動。

   此步驟會新增收集資料所需的所有 Analytics 維度。

   ![](assets/enable.png)

1. 大約一小時後，查看[「Activity Map 頁面報表」](/help/analyze/activity-map/activitymap-reporting-analytics.md)，當中就會顯示用戶有點按連結的所有頁面。

## 步驟 3.將使用者新增至 [!UICONTROL Activity Map存取] 產品設定檔 {#add_users}

1. 按一下&#x200B;**[!UICONTROL 「新增用戶至群組」]**。

   這會將您帶到中的產品設定檔頁面 [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. 如果您尚未建立 [!UICONTROL Activity Map存取] 產品設定檔，請立即執行。 此設定檔所需的許可權專案為 [!UICONTROL Analytics工具] > [!UICONTROL Activity Map] 和 [!UICONTROL Analytics工具] > [!UICONTROL 區段發佈].

1. 將使用者新增至該產品設定檔。 這可讓您的使用者從下載Activity Map  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL Activitymap]** .

