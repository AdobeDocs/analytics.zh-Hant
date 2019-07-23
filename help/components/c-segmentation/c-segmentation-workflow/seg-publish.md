---
description: 可讓您在觀眾程式庫、Target和Audience Manager中使用區段進行行銷活動。
seo-description: 可讓您在觀眾程式庫、Target和Audience Manager中使用區段進行行銷活動。
seo-title: 將區段發佈至Experience Cloud
solution: Analytics
title: 將區段發佈至Experience Cloud
topic: 區段
uuid: e5ce20c-ce43-423b-a29 f-ba66 e9 e24 d27
translation-type: tm+mt
source-git-commit: d362813f497734f3d09def59ad842406ef4bf5aa

---


# 將區段發佈至Experience Cloud

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. 最近更新大幅最佳化發佈工作流程。以前，發佈可使用的區段大約需要48小時。現在處理程序可能需要小時，但視其他流量和區段大小而定，處理速度可能會更快。(不過，我們目前沒有方法可在區段推出時通知您，因此您必須手動檢查。)我們也將可填寫區段的最大數量提升到75(從20個)。您可以在「元件&gt;區段」中檢視已發佈區段。


## 必備條件

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). 否則您無法將它發佈至Experience Cloud。
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Creation] and the [!UICONTROL Segment Publishing] permissions to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## 考量事項

* **報表套裝限制**：每個報表套裝最多可發佈75個區段。實施此限制。如果已發佈75個區段，則無法發佈任何其他區段，直到您取消發佈足夠區段以低於75區段臨界值為止。
* **會員資格限制**：共用給Analytics [!DNL Experience Cloud] 的觀眾不能超過千萬個唯一成員。
* **資料隱私**：不會根據訪客的驗證狀態篩選觀眾。如果訪客可在未驗證和已驗證狀態下瀏覽您的網站，當訪客未驗證時發生的動作仍會使系統將訪客納入受眾。Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).
* 您可以在 Analytics 中編輯或刪除發佈的區隔。如果該區隔正在使用中，系統會在您編輯該區隔時發出警告訊息。您無法刪除 Adobe [!DNL Target] 正在使用的已發佈區段。

## 區段發佈時間軸

| 可用項目 | 當它推出 | 可用項目 |
|---|---|---|
| 中繼資料(區段標題和定義) | 發佈後立即發佈 | [!DNL Audience Manager][!UICONTROL Experience Cloud觀眾程式庫]、 [!DNL Target] |
| 具備會籍的可用區段 | 發佈後的~小時 | Visitor Profile Viewer in [!DNL Audience Manager] |
| 特徵與成員族群 | 24小時內 | [!DNL Audience Manager] |

## Publish segments in [!UICONTROL Segment Builder]

1. Navigate to [!UICONTROL Analytics &gt; Workspace &gt; Components &gt; Segments] &gt; +
1. Create a segment in the [!UICONTROL Segment Builder].
1. 為區段提供標題和說明-您無法將它儲存。
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)].

![](assets/publish-ec.png)

| 元素 | 說明 |
|---|---|
| Publish this segment to the Experience Cloud (for *report suite*) | 啓用此選項時，會與Experience Cloud instantaneously共用區段標題和定義(例如，通常用於廣告平台的殼層觀眾)，而區段成員資格則會每小時評估並共用。<br> 例如，當觀眾與Target中的活動相關聯時，Analytics會開始傳送ID給符合Experience Cloud和Target對象資格的訪客。At that point, the audience name and corresponding data begins displaying on the Experience Cloud Audiences page. </br> |
| 建立對象視窗 | 您選取的時間範圍可用來建立滾動日曆的對象。例如，「最近30天」(預設)包含在今天日期前30天內符合對象資格的訪客(而非建立區段時的原始日期)。 |
| 在對象庫中建立 | 您建立和發佈的區段可以提供，而不會延遲Experience Cloud觀眾程式庫中的延遲。它們不會依賴Analytics更新。這些區段不會計入超過75個已發佈區段的限制。 |
| x75已發佈 | 顯示您已發佈至Experience Cloud的區段數。按一下連結，查看已發佈區段及其相關報表套裝和擁有者的清單。 |
| 儲存 | 儲存此區段。 |

## 解除發佈區段

To unpublish a segment, just **unclick** the checkbox that you used to publish it.

## View segment publishing status in the [!UICONTROL Segment Manager]

1. Navigate to [!UICONTROL Analytics &gt; Components &gt; Segments].
1. Notice the new [!UICONTROL Published] column. 是/否是指區段是否已發佈至Experience Cloud。

![](assets/publish-status.png)

## Retrieve the [!DNL Audience Manager] UUID and use Visitor Profile Viewer

擷取目前與瀏覽器關聯的AAM UUID有個方法：

* Adobe Experience Cloud Debugger
* 瀏覽器中的原生開發人員工具(例如Chrome Developer Tools)

下列螢幕抓圖會顯示如何擷取瀏覽器上的AAM UUID，並在Audience Manager訪客資料檢視器中使用它來驗證特徵和區段成員資格。

### 方法1：使用Adobe Experience Cloud Debugger

1. Download and install [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in the Chrome Web Store.
1. 載入頁面時啓動除錯程式。
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
(`50814298273775797762943354787774730612` in the example below)

![](assets/debugger.jpg)

### 方法2：使用Chrome Developer Tools(或其他瀏覽器開發人員工具)

1. 載入頁面之前啓動Chrome Developer Tools
1. 載入頁面並檢查「應用程式&gt; Cookie」。The AAM UUID should be set in the 3rd-party
Demdex cookie ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) in the example below). The field demdex is the AAM UUID set
on the browser (`50814298273775797762943354787774730612` in the example below)

## View the segment traits in [!DNL Audience Manager]

在AAM中，當Analytics與Experience Cloud共用區段時，會以串流方式評估特定區段的訪客清單。

1. In [!DNL Audience Manager], go to [!UICONTROL Audience Data &gt; Traits &gt; Analytics Traits]. 您將會看到每個Analytics報表套裝中對應至您Experience Cloud組織的資料夾。這些資料夾(適用於特性、區段和資料來源)會在設定或布建「描述檔和對象/人員」核心服務時建立。
1. Select the folder for the report suite in which you previously created the segment you wanted to share with [!DNL Audience Manager]. 您將看到您建立的區段/對象。When you share a segment, 2 things happen in [!DNL Audience Manager]:
* 特徵會建立，首先不含資料。約。8 hours after the segment gets published in [!DNL Analytics], the list of ECIDs gets onboarded and shared with [!DNL Audience Manager] and other Experience Cloud solutions.

![](assets/aam-traits.png)

* 隨即建立一個特徵區段。它會使用與您已發佈區段之報表套裝相關聯的資料來源。

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. 在 Analytics 或 Audience Manager 中建立的區隔皆適用於 Target 中的活動。例如，您可以根據 Analytics 中建立的 Analytics 轉換度量和受眾區隔來建立行銷活動。], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
