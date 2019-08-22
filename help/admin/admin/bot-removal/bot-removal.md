---
title: 在Adobe Analytics中移除機器人
seo-title: 在Adobe Analytics中移除機器人
description: 在Adobe Analytics中移除機器人程式的個方法
seo-description: 在Adobe Analytics中移除機器人程式的個方法
translation-type: tm+mt
source-git-commit: 3b363c6d457dbeaef443aa059d2f7de3cdccbbb2

---


# 在Adobe Analytics中移除機器人

在Adobe Analytics中，您有個主要選項可從報表中移除機器人流量：

1. Adobe Analytics中的預設機器人篩選方法是 [建立以IAB機器人清單為基礎的機器人規則](/help/admin/admin/bot-removal/bot-rules.md) 。此清單會每月更新，並從許多來源編譯其清單，包括CDN和主要網際網路屬性。它包含數以千計的已知機器人，包括所有我的最愛：Google、Bing、Mozilla等此清單涵蓋機器人篩選的絕大多數使用案例和需求。

1. 使用 [s. hitOffer實施外掛程式，](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)借由每分鐘傳送幾十次或數百次點擊，移除行為像機器人的訪客。

1. 此外，由於機器人程式進展很快，Adobe提供了幾項其他強大功能，在正常情況下並定期地結合後，有助於移除這些資料品質的敵人。這些功能包括：Experience Cloud ID服務、分段、資料倉庫、客戶屬性和虛擬報表套裝。以下概述如何運用這些工具：

## 步驟1：將訪客的Experience Cloud ID傳遞至新宣告的ID

首先，您將想要在 [「對象」核心服務中建立新的宣告ID](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)。您需要將訪客的Experience Cloud ID傳遞至此新的宣告ID，以便使用 [Adobe Experience Platform Launch快速輕鬆地完成](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html)。讓我們對宣告的ID使用「ECID」名稱。

畫面抓圖

以下是如何透過資料元素擷取此ID的畫面畫面。請確實將您的Adobe MCorG ID填入「資料元素」中。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

在設定此資料元素後，請依照 [下列指示](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) 將宣告的ID傳遞至Launch中的ECID工具。

## 步驟2：使用區段來識別機器人

現在，您將訪客的ECID傳遞至宣告的ID，現在是時候使用分析工作區中的分段來識別表現類似機器人的訪客。機器人通常由其行為定義：單次存取瀏覽、異常使用者代理、未知裝置/瀏覽器資訊、反向連結、新訪客、異常登陸頁面等。使用工作區劃分和區段的功能來識別已鎖定的IAB篩選和您的報表套裝機器人規則的機器人程式。例如，以下是您可使用之區段的螢幕擷取：

![](assets/bot-filter-seg1.png)

## 步驟3：透過資料倉庫從區段匯出所有ECID

現在，您已使用區段識別機器人，下個步驟是利用資料倉庫擷取與此區段關聯的所有Experience Cloud ID。這就是您應如何設定 [「資料倉儲](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) 」報表的方式：

![](assets/bot-dwh-3.png)

請記得使用Experience Cloud訪客ID作為維度，並套用「機器人」區段。

## 步驟4：將此清單送回Adobe作為客戶屬性

在資料倉庫報表送達後，您將擁有需要從歷史資料篩選的ECID清單。將這些ECID複製並貼至空白的. CSV檔案，只含兩欄、ECID和機器人標記：

![](assets/bot-csv-4.png)

確定第一欄標題符合您提供給上述新宣告ID的名稱。使用此. CSV檔案作為您的客戶屬性匯入檔案，然後將您的報表套裝訂閱至客戶屬性，如 [此部落格貼文](https://theblog.adobe.com/link-digital-behavior-customers)所述。

## 步驟5：建立運用新客戶屬性的區段

在處理資料集並整合至分析工作區後，請建立另一個區段，運用新的「機器人標幟」客戶屬性維度：

