---
description: 此整合結合了電子郵件行銷軟體整合式意見系統的強大功能及 Adobe Analytics 的行為報告功能，能為貴組織創造強大的分析和最佳化機會。
title: Adobe Analytics 的 optivo® broadmail Data Connector
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 98%

---


# Adobe Analytics 的 optivo® broadmail Data Connector{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我們將於2021年中後期推出Adobe Data Connector技術。 [更多詳情...](/help/import/data-connectors/data-connectors-eol.md)

此整合結合了電子郵件行銷軟體整合式意見系統的強大功能及 Adobe Analytics 的行為報告功能，能為貴組織創造強大的分析和最佳化機會。

[!DNL ~合作夥伴~]是專業的電子郵件行銷軟體。其主要功能是建立、傳送及評估電子報和電子郵件促銷活動。`[~Partner~]` 能以雲端服務形式提供使用 (軟體即服務)。

`[~Partner~]` 整合提供自動化的再行銷和資料同步處理功能，有助於提高轉換次數和收入。此整合可讓行銷人員根據客戶的電子郵件互動和網站行為，自動同步客戶區段。可自訂區段的自動資料交換可協助您建立目標明確的電子郵件促銷活動以提升銷售量 (例如放棄購買和購物後再行銷)，進而交叉銷售、向上銷售和再銷售產品。

此整合也會將 `[~Partner~]` 的成功電子郵件促銷活動的量度與 Adobe Analytics 交換。重要資料會集中顯示在您的電子郵件促銷活動概觀中。

## Data Connectors 實驗室計畫 {#section-51f9864851b64d96873127b9ac9c9a2b}

此計畫是 Adobe 第三方平台合作夥伴用於建立整合，並交付至聯合市場的快速追蹤方法。這些整合完全由我們的合作夥伴開發，並透過社群方法在 Adobe Experience Cloud 上提供使用。Adobe Analytics 和其他解決方案的 Adobe 客戶均可免費取得這些軟體，且會依現狀提供，由於整合的第三方性質，Adobe 不提供暗示保證。

如果您對目前的服務、保證或授權有任何疑問，請聯絡您的 Adobe 客戶經理。

## 主要優點和功能{#key-benefits-and-features}

這項整合包含下列主要優點：

* 找回瀏覽和放棄的購物者
* 透過針對式交叉銷售和向上銷售再行銷來提高銷售量
* 以區段為基礎的自動促銷活動
* 最佳化進行中的促銷活動
* 用於針對式再行銷的[!DNL ~合作夥伴~]區段
* 持續的促銷活動量度更新
* 自動化對話觸發器

## 動態行銷區段{#dynamic-marketing-segments}

這項整合提供下列動態行銷區段：

* **購買設定檔：**&#x200B;透過鎖定訪客購買模式的促銷活動，增加重複訂購和平均訂購值。
* **產品/內容檢視行為設定檔：**&#x200B;根據產品檢視和內容存取分析，透過行銷區段觸及潛在客戶。
* **購物車放棄設定檔：**&#x200B;透過專為猶豫是否要將購物車完成結帳的訪客量身打造的微調促銷活動，協助將訪客轉化為客戶。
* **有效的再行銷：**&#x200B;客戶也可以建立並排程自訂再行銷區段，以符合其使用者的需求。

## 在您啟用前{#before-you-activate}

在開始進行 Data Connectors 整合之前，請先完成下列需求：

## Adobe Analytics 需求 {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **報表套裝特定：**&#x200B;請注意，這項整合是報表套裝專用的。在啟用整合之前，請確定您已選取所需的報表套裝。
* **可用和已設定的 Adobe Analytics 變數：**&#x200B;此整合需要自訂事件和自訂 eVar。

* **授權代表：**&#x200B;請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任合作夥伴之一 (如適用) 的服務合約產生費用。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。
* **訊息 ID：**&#x200B;此整合需要我們在 Adobe Analytics 變數 (eVar) 中擷取並儲存「訊息 ID」。您需要透過這些 ID 識別您傳送的郵件。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **合作夥伴：**&#x200B;此整合需要我們在 Adobe Analytics 變數 (eVar) 中擷取並儲存[!UICONTROL ~合作夥伴~]。此 ID 是來自[!UICONTROL ~合作夥伴~]系統之電子郵件地址的編碼或數值表示法。此[!UICONTROL ~合作夥伴~]與網站上的下游訪客行為 (放棄購買、購買等) 相關聯，這些資料會被提取至[!UICONTROL ~合作夥伴~]系統中，並可用於再行銷目的。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **點按後時間：**&#x200B;在設定過程中，此整合需要指派一個 eVar，而此 eVar 需點按後動作時間對應。此操作需要將收件者點按郵件中的連結後所執行動作的相關資訊傳送給[!UICONTROL ~合作夥伴~]。

* **點按後產品：**&#x200B;在設定過程中，此整合需要指派一個 eVar，而此 eVar 需與點按後動作相關的提供產品對應。此操作需要將收件者點按郵件中的連結後所執行動作的相關資訊傳送給[!UICONTROL ~合作夥伴~]。

* **點按後動作類型：**&#x200B;在設定過程中，此整合需要指派一個 eVar，而此 eVar 需點按後動作類型對應。此操作需要將收件者點按郵件中的連結後所執行動作的相關資訊傳送給[!UICONTROL ~合作夥伴~]。

* **隱私權法規遵循：**&#x200B;您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私權問題，需要您的組織實施適當的程序，例如向您的網站訪客提供通知並授予同意。

## 定價{#pricing}

請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任的合作夥伴之一 (如適用) 的服務合約產生費用。

啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。

### Adobe 定價考量事項 {#section-1f4f46c0d969435db57d38c1c310a05a}

Adobe Analytics 解決方案的現有客戶不需額外付費即可使用此 Data Connectors 整合。尚未改用新 Adobe Analytics 產品的客戶，請聯絡 Adobe 客戶代表瞭解詳情。

### 合作夥伴定價考量事項 {#section-f8ca71df32224412a5101efb6e356529}

此整合適用於[!DNL ~合作伙伴~]客戶，但需支付額外的整合費用。請聯絡 sales@optivo.com 以取得詳細的定價資訊。請聯絡[!DNL ~合作夥伴~]取得詳細的定價資訊。

## Adobe Analytics 變數{#adobe-analytics-variables}

此整合需要使用 Adobe Analytics 變數來追蹤量度。

在識別要與這項整合搭配使用的事件和 eVar 後，必須在 Analytics Admin Console 中啟用它們 (如需指示，請參閱[報表套裝](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/manage-report-suites/report-suites-admin.html))。
