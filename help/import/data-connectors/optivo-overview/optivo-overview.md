---
description: 此整合結合了電子郵件行銷軟體整合式意見回應系統的強大功能與Adobe Analytics的行為報告功能，為您的組織建立強大的分析與最佳化機會。
seo-description: 此整合結合了電子郵件行銷軟體整合式意見回應系統的強大功能與Adobe Analytics的行為報告功能，為您的組織建立強大的分析與最佳化機會。
seo-title: Adobe Analytics的Optivo® broadmail Data Connector
title: Adobe Analytics的Optivo® broadmail Data Connector
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Adobe Analytics的Optivo® broadmail Data Connector{#optivo-broadmail-data-connector-for-adobe-analytics}

此整合結合了電子郵件行銷軟體整合式意見回應系統的強大功能與Adobe Analytics的行為報告功能，為您的組織建立強大的分析與最佳化機會。

[!DNL ~合作夥伴~] 是專業的電子郵件行銷軟體。 其主要功能是建立、傳送及評估電子報和電子郵件宣傳。 `[~Partner~]` 提供雲端服務（軟體即服務）。

此整 `[~Partner~]` 合提供自動化的再行銷和資料同步化，進而提高轉化率和收入。 此整合可讓行銷人員根據客戶的電子郵件互動和網站行為，自動同步客戶細分。 可自訂區段的自動資料交換可協助您建立目標明確的電子郵件宣傳，以提升銷售，例如購物車放棄率和購物後再行銷至交叉、向上和轉售產品。

此整合也會將成功電子郵件宣傳的指標從 `[~Partner~]` Adobe Analytics交換。 重要資料會集中顯示在您的電子郵件促銷活動概述中。

## 資料連接器實驗室計畫 {#section-51f9864851b64d96873127b9ac9c9a2b}

此計畫是Adobe協力廠商平台合作夥伴建立整合併傳遞至聯合市場的快速追蹤方法。 這些整合由我們的合作夥伴完全開發，並透過社群方法在Adobe Experience cloud上提供。 Adobe Analytics和其他解決方案的Adobe客戶可免費取得這些軟體，且由於整合的第三方性質，Adobe不提供默示擔保，因此Adobe不會依現狀提供。

如果您對目前的服務、擔保或授權有任何疑問，請聯絡您的Adobe客戶經理。

## 主要優點和功能{#key-benefits-and-features}

此整合包含下列主要優點：

* 恢復瀏覽和放棄的購物者
* 透過目標交叉銷售和向上銷售再行銷提高銷售
* 自動以區段為基礎的促銷活動
* 進行中的最佳化促銷活動
* 合作夥伴中 [!DNL ~的細分~] ，以進行目標再行銷
* 持續促銷活動量度更新
* 自動化對話觸發程式

## 動態行銷區段{#dynamic-marketing-segments}

此整合包含下列動態行銷區段：

* **** 購買設定檔：透過訪客購買模式所定位的促銷活動，增加重複訂單和平均訂單值。
* **** 產品／內容檢視行為設定檔：根據產品檢視和內容存取分析，透過行銷細分觸及潛在客戶。
* **** 購物車放棄設定檔：透過專為猶豫是否要完成購物車的訪客量身打造的微調促銷活動，協助訪客轉化為客戶。
* **** 有效的再行銷：客戶也可以根據其使用者的需求建立並排程自訂的再行銷區段。

## 啟動前{#before-you-activate}

在開始的「資料連接器」整合之前，請完成下列需求：

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** 報表套裝特定：請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所需的報表套裝。
* **** 可用和設定的Adobe Analytics變數：此整合需要自訂事件和自訂eVar。

* **** 授權代表：請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。 啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。
* **** 訊息ID:整合需要我們擷取並儲存Adobe Analytics變數(eVar)中的「訊息ID」。 您需要這些ID來識別您傳送的郵件。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。
* **** 合作夥伴：整合需要我們在Adobe Analytics變數(eVar) [!UICONTROL ~中擷取並儲存~] 「合作夥伴」。 此ID是來自合作夥伴系統的電子郵件地址的編碼或數 [!UICONTROL ~字表~] 示。 此合 [!UICONTROL ~作夥伴~] 與網站上的下游訪客行為（購物車放棄、購買等）相關聯被拉入「合作伙 [!UICONTROL ~伴~] 」系統，並可用於再行銷目的。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。
* **** 貼文點按時間：在設定程式中，此整合需要指派與點按後動作時間對應的eVar。 當收件者點選郵件中的連結後，需要將收件者動作的相 [!UICONTROL ~關資訊傳送給Partner~] 。

* **** 點按貼文產品：在設定程式中，此整合需要指派給eVar，該eVar對應於與點按貼文動作相關聯的已提供產品。 當收件者點選郵件中的連結後，需要將收件者動作的相 [!UICONTROL ~關資訊傳送給Partner~] 。

* **** 點按後動作類型：在設定程式中，此整合需要指派給與點按後動作類型對應的eVar。 當收件者點選郵件中的連結後，需要將收件者動作的相 [!UICONTROL ~關資訊傳送給Partner~] 。

* **** 隱私權規範：您應瞭解，透過啟用「收件者」或「訪客ID」追蹤，此功能可追蹤您網站訪客的個人識別資訊。 這涉及隱私權問題，需要貴組織實施適當的程式，例如向網站訪客提供通知並給予同意。

## 定價{#pricing}

請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。

啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。

### Adobe定價考量事項 {#section-1f4f46c0d969435db57d38c1c310a05a}

Adobe Analytics解決方案的現有客戶使用此「資料連接器整合」時不需額外付費。 尚未改用新Adobe Analytics產品的客戶，請聯絡Adobe客戶代表以取得詳細資訊。

### 合作夥伴定價考慮事項 {#section-f8ca71df32224412a5101efb6e356529}

此整合適用於合作伙 [!DNL ~伴客戶~] ，但需支付額外的整合費用。 請聯絡sales@optivo.com以取得詳細的價格資訊。 請聯絡合 [!DNL ~作夥伴~] ，以取得價格詳細資訊。

## Adobe Analytics變數{#adobe-analytics-variables}

此整合需要Adobe Analytics變數來追蹤量度。

在識別要與此整合搭配使用的事件和eVar後，必須在Analytics管理控制台中啟用它們(如需指示，請 [參閱報表套裝](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) )。