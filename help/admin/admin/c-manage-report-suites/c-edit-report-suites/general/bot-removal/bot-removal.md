---
title: 在 Adobe Analytics 移除機器人
description: 在 Adobe Analytics 移除機器人的方式
feature: Bot Removal
role: Admin
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: de9d2039411a7f8539f8e7b4eb840f03c964f489
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 75%

---

# 在 Adobe Analytics 移除機器人

Adobe Analytics提供多個選項，用於從報表中移除機器人流量：

## 使用機器人規則

前往&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 機器人規則」]**，即可設定標準與自訂的機器人篩選方式：

| 規則類型 | 說明 |
|--- |--- |
| 標準 IAB 機器人規則 | 選取&#x200B;**[!UICONTROL 「啟用 IAB 機器人篩選規則」]**，系統會使用 [IAB](https://www.iab.com/) (國際廣告局) 的「國際編目程式與機器人清單」來移除機器人流量。多數客戶至少都會選取此選項。 |
| 自訂機器人規則 | 您可以根據使用者代理、IP 位址或 IP 範圍來定義與新增自訂機器人規則。 |

如需詳細資訊，請參閱[瞭解並設定機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)。

## 使用 Adobe 工具組合

此外，由於機器人會快速變形，Adobe 為此提供數種其他強大功能，只要定期適當地組合使用，有助於加強清除這些危及資料品質的來源。這些功能包括：Experience Cloud ID服務、細分、Data Warehouse、客戶屬性和虛擬報表套裝。  以下為工具運用方式總覽。

### 步驟 1：將訪客的 Experience Cloud ID 傳遞至新宣告的 ID

開始之前，建議您在[「人員」核心服務](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=zh-hant)中建立新宣告 ID。 您必須將訪客的 Experience Cloud ID 傳遞至這個新宣告的 ID，這項操作透過 [Adobe Experience Platform 中的標記](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=zh=Hant)即可快速輕鬆地完成。 將已宣告 ID 命名為「ECID」。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

以下為透過「資料元素」擷取此 ID 的方式。請務必在「資料元素」中正確填入您的 Experience Cloud OrgID。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

設定這個「資料元素」後，請按照[這些指示](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=zh=Hant)，使用 Adobe Experience Platform 中的標記將已宣告的 ID 傳遞到 ECID 工具中。

### 步驟 2：使用分段來識別機器人

您已將訪客的 ECID 傳到宣告的 ID 中了，接下來您可以使用 [Analysis Workspace 的分段功能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=zh-Hant)來識別疑似機器人的訪客。機器人經常會有下列行為：單次存取造訪、異常使用者代理、未知的裝置/瀏覽器資訊、無反向連結、新訪客、異常登陸頁面等。借助 Workspace 下鑽和分段功能的力量，即可識別逃過 IAB 篩選及報表套裝機器人規則的機器人。舉例來說，您可以參考以下螢幕擷圖使用區段：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### 步驟 3：透過「Data Warehouse」匯出所有區段中的 [!DNL Experience Cloud IDs]

現在您已經透過區段找出機器人了，下一步就是利用 Data Warehouse 擷取所有與此區段關聯的 Experience Cloud ID。此螢幕擷圖顯示設定 [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) 請求的方法：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

請記得將 Experience Cloud 訪客 ID 設為維度並套用「機器人」區段。

### 步驟4：將此清單傳回Adobe作為客戶屬性

收到 Data Warehouse 報表後，您就取得需要從歷史資料中篩選掉的 ECID 清單了。複製這些 ECID 並貼到空白的 .CSV 檔案，檔案中只需包含「ECID」和「機器人標幟」兩欄。

* **ECID**：此欄的標題務須符合您為上述新宣告 ID 所設的名稱。
* **機器人標幟**：新增「機器人標幟」為「客戶」屬性結構描述維度。

將這份.CSV檔案匯入為「客戶」屬性，然後依照這篇[部落格](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers)所述，使報表套裝訂閱「客戶」屬性。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### 步驟5：建立可運用新「客戶」屬性的區段

在系統處理完您的資料集並整合至 Analysis Workspace 後，請建立另一個區段，區段中採用新的「機器人標幟」客戶屬性維度和「[!UICONTROL 排除]」容器：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### 步驟6：將此區段設為虛擬報表套裝篩選條件

最後，建立[虛擬報告套裝](/help/components/vrs/vrs-about.md)，並使用此區段來篩選掉已識別的機器人：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

這個新分段的虛擬報表套裝所產生的資料集已完全移除已識別的機器人，會乾淨不少。

### 步驟 7：定期重複步驟 2、3 和 4

提醒自己至少每月識別與篩除新機器人一次，盡可能在定期排程分析之前完成。

>[!MORELIKETHIS]
>
>* [更好的機器人封鎖（第1部分）：基本知識](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-1-the-basics/ba-p/715839)
>* [更好的機器人封鎖（第2部分）：識別機器人並運用CIDR](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-2-identifying-bots-and-leveraging-cidr/ba-p/722132)
>* [更好的機器人封鎖（第3部分）：點選管理員](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-3-the-hit-governor/ba-p/727051)

