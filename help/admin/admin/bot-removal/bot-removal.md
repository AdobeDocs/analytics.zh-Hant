---
title: Adobe Analytics中的機器人移除
seo-title: Adobe Analytics中的機器人移除
description: Adobe Analytics中移除機器人的3種方式
seo-description: Adobe Analytics中移除機器人的3種方式
translation-type: tm+mt
source-git-commit: ef17712b4a8a4a5c13dde9be9fdf2281eeb40091

---


# Adobe Analytics中的機器人移除

在Adobe Analytics中，您有多個選項可從報表中移除機器人流量：

## 使用機器人規則

標準和機器人篩選方法都受 **[!UICONTROL Analytics]** **[!UICONTROL Admin]** Report Suites **[!UICONTROL &gt; Settings]** &gt; General Custom Bot規則 ************&gt; Edit General Comsum Bot Rules: Admin Report Suites支援

| 規則類型 | 說明 |
|--- |--- |
| 標準IAB機器人規則 | 選 **[!UICONTROL 取「啟用IAB機器人篩選規則]** 」會使用 [IAB](https://www.iab.com/) （國際廣告局）的「國際蜘蛛程式與機器人清單」來移除機器人流量。 大多數客戶至少要選擇此選項。 |
| 自訂機器人規則 | 您可以根據使用者代理、IP位址或IP範圍來定義和新增自訂機器人規則。 |

如需詳細資訊，請參 [閱機器人規則概觀](/help/admin/admin/bot-removal/bot-rules.md)。

## 使用 `hitGovernor` 實施外掛程式

使用 [s.hitGovernor實作外掛程式](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)，可移除行為類似機器人的訪客，這表示這些訪客每分鐘傳送數十或數百次點擊。

## 結合使用Adobe工具

此外，由於機器人程式正在快速變形，Adobe提供其他數種強大功能，當適當且定期地結合後，可協助清除這些資料品質的敵人。 這些功能包括：Experience Cloud ID服務、區段、資料倉庫、客戶屬性和虛擬報表套裝。 以下是如何運用這些工具的概觀。

### 步驟1:將訪客的Experience Cloud ID傳遞至新宣告的ID

若要開始，您會想要在「人員核心服務」中建立新 [的宣告ID](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)。 您需要將訪客的Experience Cloud ID傳遞至此新宣告的ID中，這可以透過 [Adobe Experience Platform Launch快速輕鬆地完成](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html)。 讓我們為宣告的ID使用名稱「ECID」。

![](assets/bot-cust-attr-setup.png)

以下是如何透過「資料元素」擷取此ID的方式。 請務必將您的Experience cloud組織ID正確填入「資料元素」。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

設定此資料元素後，請依照 [下列指示](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) ，將宣告的ID傳入Launch的ECID工具中。

### 步驟2:使用區段來識別機器人

現在您已將訪客的ECID傳入宣告的ID中，您可以在分析工作區中使 [用區段來識別像是機器人的訪客](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) 。 機器人通常由其行為定義：單次存取、異常使用者代理、未知的裝置／瀏覽器資訊、無反向連結、新訪客、異常著陸頁面等。 使用工作區下鑽和分段功能，識別逃避IAB篩選的機器人程式和您的報表套裝機器人規則。 例如，以下是您可使用之區段的螢幕擷取：

![](assets/bot-filter-seg1.png)

### 步驟3:透過資 [!DNL Experience Cloud IDs] 料倉庫從區段匯出所有

現在您已使用區段識別機器人，下一步就是利用資料倉庫擷取與此區段關聯的所有Experience Cloud ID。 以下是您如何設定資料倉 [庫請求](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

請記得使用Experience cloud訪客ID做為維度並套用「機器人」區段。

### 步驟4:將此清單傳回Adobe作為客戶屬性

資料倉庫報表到達後，您就會有需要從歷史資料篩選的ECID清單。 將這些ECID複製並貼入空白的。CSV檔案，只有兩欄：ECID和機器人標幟。

* **ECID**:請確定此欄標題符合您為上述新宣告的ID所提供的名稱。
* **機器人標幟**:將其添加為「客戶屬性」結構維。

使用此。CSV檔案做為「客戶屬性」匯入檔案，然後依照此部落格文章中所述，將您的報表套裝訂閱至「客戶 [屬性」](https://theblog.adobe.com/link-digital-behavior-customers)。

![](assets/bot-csv-4.png)

### 步驟5:建立可運用新「客戶屬性」的區段

在您的資料集已處理並整合至分析工作區後，請建立另一個區段，以運用新的「機器人標幟」客戶屬性維度和排除容 [!UICONTROL 器] :

![](assets/bot-filter-seg2.png)

### 步驟6:使用此區段作為虛擬報表套裝篩選

最後，您應建立虛擬報 [表套裝](/help/components/vrs/vrs-about.md) ，利用此區段來篩選已識別的機器人：

![](assets/bot-vrs.png)

此新分段的虛擬報表套裝現在會產生一組明顯更簡潔的資料，並完全移除已識別的機器人。

### 步驟7:定期重複步驟2、3和4

至少每月設定提醒，以識別和篩選新的機器人程式，可能是在定期排程分析之前。
