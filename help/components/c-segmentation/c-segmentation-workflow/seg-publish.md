---
description: 可讓您在「對象庫」、「目標」和「對象管理員」中，將區段用於行銷活動。
seo-description: 可讓您在「對象庫」、「目標」和「對象管理員」中，將區段用於行銷活動。
seo-title: 發佈區段至 Experience Cloud
solution: Analytics
title: 發佈區段至 Experience Cloud
topic: 區段
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: cd2d9f90c548d3bb32a57faa47b185dc25db1d5a

---


# 發佈區段至 Experience Cloud

>[!IMPORTANT]
>
>尚未針對所有客戶推出本頁所述有關區段發佈和使用者介面的延遲改進。 這裡說明目前的生產 [環境](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html)。

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], [!DNL Advertising Cloud], and [!DNL Campaign]. 最近的更新已大幅最佳化發佈工作流程。 以前，發佈可用區段大約需要48小時。

現在，處理最多需要8小時，但視其他流量和區段大小而定，處理速度可能更快。 （不過，我們目前無法通知您區段何時可用，因此您必須手動檢查。）我們也將可發佈區段的最大數量從20個增加到75個。 您可以在「元件&gt;區段」中檢視已發佈的區段。

>[!NOTE]
>
>Adobe Campaign（Classic和Standard）的運作方式不同，因為它會在8小時延遲的同時，產生額外的24小時延遲。


## 必備條件

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). 否則，您無法將它發佈至Experience Cloud。
* 請確定您正在對應至Experience cloud組織的 [報表套裝中工作](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。
* 請確定您的組織正在使用Experience Cloud ID。
* 在您發佈區段之前，您的管理員必須先將「 [!UICONTROL 區段發佈] 」權限指派給 [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)Admin Console中的產品設定檔，然後將您新增至產品設定檔。


## 考量事項

* **報表套裝限制**:每個報表套裝最多可發佈75個區段。 此限制會強制執行。 如果您已發佈75個區段，則必須解除發佈足夠的區段，才能發佈至低於75個區段臨界值的區段。
* **會籍限制**:從Analytics共用給 [!DNL Experience Cloud] 的觀眾不能超過2000萬個獨特成員。
* **資料隱私**:不會根據訪客的驗證狀態來篩選對象。 如果訪客可在未驗證和已驗證狀態下瀏覽您的網站，當訪客未驗證時發生的動作仍會使系統將訪客納入受眾。檢視 [Adobe Experience cloud隱私權](https://www.adobe.com/privacy/experience-cloud.html) ，以瞭解受眾分享的完整隱私權影響。
* 有關和中的區 **段之間差異的[!DNL Adobe Analytics]討[!DNL Audience Manager]**&#x200B;論，請 [到此處](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)。

## 區段發佈時間軸

| 可用功能 | 可用時 | 可用位置 |
|---|---|---|
| 中繼資料（區段標題和定義） | 發佈後立即生效 | [!DNL Audience Manager], [!UICONTROL Experience cloud觀眾程式庫], [!DNL Target] |
| 具有會籍的可用區段 | 發佈後約8小時 | 訪客資料檢視器(位於 [!DNL Audience Manager] |
| 特性與會籍人口 | 24-48小時內 | [!DNL Audience Manager] |

## 在區段產生器中 [!UICONTROL 發佈區段]

1. 導覽至「 **[!UICONTROL 分析&gt;工作區&gt;元件&gt;區段]&gt; +」**
1. 在區段產生器中建 [!UICONTROL 立區段]。
1. 提供區段的標題和說明——否則您無法儲存。
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>在Analytics中檢視區段預覽時，請務必使用「具有Experience Cloud ID的訪客」，而不是比較Adobe Analytics數字與Audience Manager數字時的「獨特訪客」區段預覽總計：
>
>![](assets/seg-vis-ecid.png)

| 元素 | 說明 |
|---|---|
| **[!UICONTROL 將此區段發佈至 Experience Cloud (適用於&#x200B;*<report suite>*)]** | 啟用此選項時，區段標題和定義（即廣告平台中常用的殼層對象）會立即與Experience cloud共用，而區段會籍會每4小時評估一次並共用一次。 <br> 例如，當該對象與中的活 [!DNL Target]動相關聯時， [!DNL Analytics] 就會開始傳送符合該Experience cloud及對象資格的訪客的ID [!DNL Target] 。 At that point, the audience name and corresponding data begins displaying on the Experience Cloud Audiences page. </br> |
| **[!UICONTROL 建立對象視窗]** | 您選取的時間範圍會用來建立以滾動日曆為基礎的觀眾。 例如，「最近30天」（預設值）包含自今天日期（非建立區段的原始日期）起最近30天內符合觀眾資格的訪客。 |
| **[!UICONTROL 在對象庫中建立]** | 您建立和發佈的區段可在Experience cloud觀眾程式庫中提供，而無延遲。 它們不依賴Analytics更新。 這些區段不會計入您75個發佈區段的限制。 |
| **[!UICONTROL 第x頁（共75頁）已發佈]** | 顯示您已發佈至Experience cloud的區段數。 按一下連結，以檢視已發佈區段及其關聯報表套裝和擁有者的清單。 |
| **[!UICONTROL 儲存]** | 儲存此區段。 |

## 取消發佈或刪除區段

若要刪除已發佈至 Experience Cloud 的區段，必須先將其取消發佈。若要取消發佈區段，只需&#x200B;**取消勾選**&#x200B;您用來發佈該區段的核取方塊即可。

>[!NOTE]
>
>您&#x200B;**無法**&#x200B;取消發佈下列任何 Adobe 解決方案目前正在使用的區段：[!DNL Analytics] (在 [!DNL Audience Analytics] 中)、[!DNL Campaign]、[!DNL Advertising Cloud] (適用於 [!DNL Core Service] 和 [!DNL Audience Manager] 客戶) 以及所有其他外部合作夥伴 (適用於 [!DNL Audience Manager] 客戶)。您&#x200B;**可以**&#x200B;取消發佈 [!DNL Target] 正在使用的區段。

## 在「區段管理員」中檢視區段發 [!UICONTROL 布狀態]

1. 導覽至「 [!UICONTROL 分析&gt;元件&gt;區段」]。
1. 請注意新的「 [!UICONTROL 發佈] 」欄。 是／否指區段是否已發佈至Experience Cloud。

![](assets/publish-status.png)

## 檢索 [!DNL Audience Manager] UUID

擷取目前與瀏覽器相關聯的AAM UUID有兩種方式：

* Adobe Experience Cloud Debugger
* 瀏覽器中的原生開發人員工具（例如Chrome Developer Tools）

下列螢幕擷取畫面顯示如何在瀏覽器上擷取AAM UUID，並在Audience Manager訪客資料檢視器中使用它來驗證特徵和區段會籍。

**方法1:使用Adobe Experience cloud除錯程式**

1. 在Chrome Web Store下 [載並安裝Adobe Experience Cloud](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) Debugger。
1. 載入頁面時啟動除錯程式。
1. 捲動至Audience Manager區段，並在目前瀏覽器頁面上尋找AAM UUID集(在`50814298273775797762943354787774730612` 以下範例中)

![](assets/debugger.jpg)

**方法2:使用Chrome Developer Tools（或其他瀏覽器開發人員工具）**

1. 載入頁面之前，先啟動Chrome開發人員工具
1. 載入頁面並勾選「應用程式&gt; Cookie」。 AAM UUID應設定在第三方Demdex Cookie([以下範例中為adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) )中。 欄位demdex是AAM UUID，會選取瀏覽器(`50814298273775797762943354787774730612` 在以下範例中)。

![Chrome Developer Tool](assets/ggogle-uuid.png)

## 使用Audience Manager訪客 [!UICONTROL 資料檢視器]

在載入訪客描述檔檢視器時，預設會使用瀏 [!UICONTROL 覽器上的AAM] UUID。 如果驗證其他使用者的特徵實現，請在UUID欄位中輸入UUID，然後按一下「重新 [!UICONTROL 整理]」。 如需詳細 [資訊，請參閱訪客資料檢視器](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) 。

![](assets/aam-vpv.png)

## 檢視區段特徵於 [!DNL Audience Manager]

在AAM中，當Analytics與Experience cloud共用區段時，會以串流方式評估特定區段的ECID訪客清單。

1. 在中 [!DNL Audience Manager]，請至「觀 [!UICONTROL 眾資料&gt;特徵&gt;分析特徵」]。 您將會看到每個Analytics報表套裝的資料夾，該資料夾已對應至您的Experience cloud組織。 當設定檔和觀眾／人員核心服務啟動或布建時，就會建立這些資料夾（特徵、區段和資料來源）。
1. 選取您先前建立要共用之區段的報表套裝資料夾 [!DNL Audience Manager]。 您將看到您建立的區段／對象。 當您共用區段時，會發生下列兩個事 [!DNL Audience Manager]項：
* 首先建立特徵，但不含任何資料。 約 在區段發佈8小時後， [!DNL Analytics]ECID清單就會登入並與其他Experience cloud解決方 [!DNL Audience Manager] 案共用。

![](assets/aam-traits.png)

* 建立單一特徵區段。 它使用與您發佈區段之報表套裝關聯的資料來源。

## 檢視區段於 [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. 在 Analytics 或 Audience Manager 中建立的區隔皆適用於 Target 中的活動。例如，您可以根據 Analytics 中建立的 Analytics 轉換度量和受眾區隔來建立行銷活動。]，按一下「 [!UICONTROL 觀眾」]。
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

