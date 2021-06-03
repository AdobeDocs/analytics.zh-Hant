---
description: 此 Adobe® Data Connectors™ 電子郵件整合項目結合 Adobe Analytics® 的行為資訊與電子郵件行銷功能，打造出功能強大的工具，透過更相關的傳訊重新定義成功測量及鎖定受眾。
title: Adobe Analytics 的 Aprimo Data Connector
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
exl-id: cd5191c9-68fb-42ad-98f6-23d5a72878da
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 97%

---

# Adobe Analytics 的 Aprimo Data Connector{#aprimo-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我們將於2021年8月1日終止AdobeData Connector技術。 [更多詳情...](/help/import/data-connectors/data-connectors-eol.md)

此 Adobe® Data Connectors™ 電子郵件整合項目結合 Adobe Analytics® 的行為資訊與電子郵件行銷功能，打造出功能強大的工具，透過更相關的傳訊重新定義成功測量及鎖定受眾。

向這些市場區塊傳遞相關電子郵件訊息可帶來全新的收入商機，進而推動全新和現有電子郵件促銷活動的轉換和收入。舉例來說，根據瀏覽期間檢視的產品或放棄的購物車中的產品來傳送相關電子郵件訊息，經證明對收入有顯著影響，而且對成本的影響最小，因為這只是運用您網站已獲得的訪客。

這種行銷效率的提升，是整合 [!DNL Adobe Analytics] 與 Aprimo 的主要優點之一。此外，這項整合會自動將電子郵件量度與 [!DNL Adobe Analytics] 資料同步化，封閉迴圈報表的同步頻率可達每小時一次。

## 主要優點和功能{#key-benefits-and-features}

這項整合包含下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報表介面。
* 透過轉換和對收入和網站成功的貢獻，最佳化電子郵件促銷活動。
* 根據動態行銷區段，再行銷關鍵訪客和市場區塊。

## 動態行銷區段{#dynamic-marketing-segments}

這項整合提供下列動態行銷區段：

* **購買設定檔：**&#x200B;透過鎖定訪客購買模式的促銷活動，增加重複訂購和平均訂購值。
* **產品/內容檢視行為設定檔：**&#x200B;根據產品檢視和內容存取分析，透過行銷區段觸及潛在客戶。
* **購物車放棄設定檔：**&#x200B;透過專為猶豫是否要將購物車完成結帳的訪客量身打造的微調促銷活動，協助將訪客轉化為客戶。
* 客戶也可以根據其使用者的需求，建立並排程自訂的再行銷區段。

## 在您啟用前{#before-you-activate}

在開始進行 Data Connectors 整合之前，請先完成下列需求：

### Adobe Analytics 需求 {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **報表套裝特定：**&#x200B;請注意，這項整合是報表套裝專用的。在啟用整合之前，請確定您已選取所需的報表套裝。
* **可用和已設定的 Adobe Analytics 變數：**&#x200B;此整合需要自訂事件和自訂 eVar，以及選用的其他事件和其他 eVar。
* **授權代表：**&#x200B;請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任合作夥伴之一 (如適用) 的服務合約產生費用。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。
* **Data Warehouse™：**&#x200B;這項整合需要啟用 Data Warehouse，才能產生再行銷區段。如果您尚未啟用 Data Warehouse，請聯絡 Adobe 瞭解詳情。
* **[!UICONTROL 合作夥伴~]：**&#x200B;此整合需要我們在 Adobe Analytics 變數 (eVar) 中擷取並儲存「[!DNL ~合作夥伴~]」。此 ID 是來自[!DNL ~合作夥伴~]系統之電子郵件地址的編碼或數值表示法。此「[!DNL ~合作夥伴~]」與網站上的下游訪客行為 (放棄購買、購買等) 相關聯，這些資料會被提取至[!DNL ~合作夥伴~]系統中，並可用於再行銷目的。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **外部追蹤：**&#x200B;如果您目前未遵循針對您傳送之每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做以確保成功整合。如需詳細資訊，請參閱下方的[!DNL ~合作夥伴~]區段。
* **隱私權法規遵循：**&#x200B;您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私權問題，需要您的組織實施適當的程序，例如向您的網站訪客提供通知並授予同意。

## 定價{#pricing}

請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任的合作夥伴之一 (如適用) 的服務合約產生費用。

啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。

### Adobe 定價考量事項 {#section-1f4f46c0d969435db57d38c1c310a05a}

這項整合可能會產生週期性和實施的相關費用，包括透過此整合產生的伺服器呼叫數增加的成本。如需價格方面的詳細資訊，請聯絡您的 Adobe 客戶代表。

### ~合作夥伴~定價考量事項 {#section-f8ca71df32224412a5101efb6e356529}

此整合可能會產生週期性和實施的相關費用。請聯絡[!DNL ~合作夥伴~]取得詳細的定價資訊。

## Adobe Analytics 變數{#adobe-analytics-variables}

此整合需要使用 Adobe Analytics 變數來追蹤量度。

識別要與此整合搭配使用的事件和 eVar 後，請在 Adobe Analytics Admin Console 中啟用它們 (如需指示，請參閱[報表套裝](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) )。
