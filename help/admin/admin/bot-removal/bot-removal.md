---
title: 在 Adobe Analytics 移除機器人
description: 如何在Adobe Analytics中移除機器人
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 52%

---

# 在 Adobe Analytics 移除機器人

在 Adobe Analytics 中，您有多個選項可移除報表中的機器人流量：

## 使用機器人規則

前往&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 機器人規則」]**，即可設定標準與自訂的機器人篩選方式：

| 規則類型 | 說明 |
|--- |--- |
| 標準 IAB 機器人規則 | 選取&#x200B;**[!UICONTROL 「啟用 IAB 機器人篩選規則」]**，系統會使用 [IAB](https://www.iab.com/) (國際廣告局) 的「國際編目程式與機器人清單」來移除機器人流量。多數客戶至少都會選取此選項。 |
| 自訂機器人規則 | 您可以根據使用者代理、IP位址或IP範圍來定義和新增自訂機器人規則。 |

如需詳細資訊，請參閱[機器人規則概觀](/help/admin/admin/bot-removal/bot-rules.md)。

## 使用[!UICONTROL websiteBot]外掛程式來識別機器人

[!UICONTROL websiteBot]外掛程式可讓您動態識別案頭訪客是否為機器人。 您可以使用這些資料來提高所有報告類型的正確性，這可讓您以更好的方式測量合理的網站流量。

此外掛程式會執行兩項檢查：

* 首先，它會使用navigator.UserAgent變數來判斷裝置是桌上型或行動裝置。 若是行動裝置則不列入考慮。
* 若是桌上型電腦，此外掛程式會新增一個滑鼠移動事件監聽程式。

如需詳細資訊，請參閱[Adobe Analytics實作指南](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html)。

## 使用 Adobe 工具組合

此外，由於機器人會快速變形，Adobe 為此提供數種其他強大功能，只要定期適當地組合使用，有助於加強清除這些危及資料品質的來源。這些功能包括：Experience Cloud ID 服務、分段、Data Warehouse、客戶屬性和虛擬報表套裝。以下是如何使用這些工具的概述。

### 步驟 1：將訪客的 Experience Cloud ID 傳遞至新宣告的 ID

若要開始，請在[People核心服務](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)中建立新宣告ID。 將訪客的Experience CloudID傳遞至此新宣告的ID，這項操作透過[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)即可快速輕鬆完成。 將已宣告 ID 命名為「ECID」。

![](assets/bot-cust-attr-setup.png)

以下為透過「資料元素」擷取此 ID 的方式。請務必將您的Experience CloudOrgID正確填入「資料元素」中。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

設定此資料元素後，請依照[這些指示](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)，將宣告的ID傳遞至Experience Launch的ECID工具中。AdobeLaunch

### 步驟 2：使用分段來識別機器人

您已將訪客的 ECID 傳到宣告的 ID 中了，接下來您可以使用 [Analysis Workspace 的分段功能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)來識別疑似機器人的訪客。機器人經常會有下列行為：單次存取造訪、異常使用者代理、未知的裝置/瀏覽器資訊、無反向連結、新訪客、異常登陸頁面等。借助工作區下鑽和分段功能的力量，即可識別逃過 IAB 篩選及報表套裝機器人規則的機器人。舉例來說，您可以參考以下螢幕擷圖使用區段：

![](assets/bot-filter-seg1.png)

### 步驟 3：透過「Data Warehouse」匯出所有區段中的 [!DNL Experience Cloud IDs]

您已使用區段識別機器人後，下一步就是使用Data Warehouse擷取與此區段相關聯的所有Experience CloudID。 此螢幕擷取顯示您應如何設定[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)請求：

![](assets/bot-dwh-3.png)

請記得以「Experience Cloud訪客ID」作為維度，並套用「機器人」區段。

### 步驟 4：將此清單傳回 Adobe 作為客戶屬性

Data Warehouse報表抵達後，您就有必須從歷史資料中篩選的ECID清單。 複製這些 ECID 並貼到空白的 .CSV 檔案，檔案中只需包含「ECID」和「機器人標幟」兩欄。

* **ECID**:請確定此欄標題與您為上述新宣告ID所指定的名稱相符。
* **機器人標幟**:將「機器人標幟」新增為「客戶屬性」結構維度。

將這份 .CSV 檔案匯入為「客戶屬性」，然後依照這篇[部落格文章](https://theblog.adobe.com/link-digital-behavior-customers)所述，使報表套裝訂閱「客戶屬性」。

![](assets/bot-csv-4.png)

### 步驟 5：建立可運用新「客戶屬性」的區段

處理完您的資料集並整合至Analysis Workspace後，請建立另一個區段，區段會運用新的「機器人標幟」客戶屬性維度和[!UICONTROL Exclude]容器：

![](assets/bot-filter-seg2.png)

### 步驟 6：將此區段設為虛擬報表套裝篩選條件

最後，建立[虛擬報表套裝](/help/components/vrs/vrs-about.md) ，使用此區段來篩選已識別的機器人：

![](assets/bot-vrs.png)

這個新分段的虛擬報表套裝現在會產生更乾淨的資料集，並移除已識別的機器人。

### 步驟 7：定期重複步驟 2、3 和 4

至少每月提醒您識別和篩選新機器人，或許在定期排程分析之前。
