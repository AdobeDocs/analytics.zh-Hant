---
description: 此Adobe® Data Connectors™電子郵件整合功能結合了Analytics®的行為資訊與Delivra電子郵件行銷，以建立功能強大的工具來重新定義成功評估，並運用更相關的訊息鎖定受眾。
seo-description: 此Adobe® Data Connectors™電子郵件整合功能結合了Analytics®的行為資訊與Delivra電子郵件行銷，以建立功能強大的工具來重新定義成功評估，並運用更相關的訊息鎖定受眾。
seo-title: Adobe Analytics的Delivra Data Connector
title: Adobe Analytics的Delivra Data Connector
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Delivra Data Connector for Adobe Analytics{#delivra-data-connector-for-adobe-analytics}

此Adobe® Data Connectors™電子郵件整合功能結合了Analytics®的行為資訊與Delivra電子郵件行銷，以建立功能強大的工具來重新定義成功評估，並運用更相關的訊息鎖定受眾。

向這些市場細分傳遞相關電子郵件訊息可帶來全新的營收商機，進而推動新電子郵件和現有電子郵件宣傳的轉化率和營收。 例如，根據瀏覽期間檢視的產品或放棄購物車中的產品，傳送相關的電子郵件訊息已證明對收入有顯著影響，而且對成本的影響最小，因為這只是利用您網站已獲取的訪客。 行銷效率的提升是整合Analytics與Delivra的主要優點之一。 此外，此整合將自動將電子郵件量度與Analytics資料同步化，與閉環報告的每小時同步頻率相同。

## 主要優點{#key-benefits}

此整合包含下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報告介面
* 透過轉化和對收入和網站成功的貢獻，最佳化電子郵件宣傳
* 根據動態行銷區隔，重新行銷關鍵訪客和市場區隔
* 幾乎即時的電子郵件量度同步可用，而標準的每天一次

## 動態行銷區段{#dynamic-marketing-segments}

此Data Connectors電子郵件整合支援動態行銷區段，以協助您推動業務。

此整合具備下列立即可用的行銷區段：

* **** 購買設定檔：透過訪客購買模式所定位的促銷活動，增加重複訂單和平均訂單值。
* **** 產品／內容檢視行為設定檔：根據產品檢視和內容存取分析，透過行銷細分觸及潛在客戶。
* **** 購物車放棄設定檔：透過專為猶豫是否要完成購物車的訪客量身打造的微調促銷活動，協助訪客轉化為客戶。
* 客戶也可以根據其使用者的需求建立並排程自訂的再行銷區段。

## 整合程式與先決條件{#integration-procedure-and-prerequisites}

使用「即插即用」嚮導，直觀的逐步過程將引導您完成系統同步點並初始化整合。

此「資料連接器」整合需要下列項目：

### Adobe先決條件 {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe資料倉庫
* Adobe Analytics帳戶
* 可用和設定的Analytics變數，包括eVar和自訂事件。

### 提供先決條件： {#section-bcb904574ccf42308bcf7a15e45b4d58}

* 啟用「Adobe整合」選項的有效Delivra專業級（或以上）帳戶。

## 定價{#pricing}

此Data Connectors整合包含您需要注意的價格考量。

以下章節包含更多資訊: 

### Adobe定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此整合可能會產生經常性和實施費用。 如需價格詳細資訊，請連絡您的Adobe客戶代表。

### 提供定價考慮事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此整合可能會產生相關費用。

* 請洽詢您的Delivra帳戶代表以取得價格詳細資訊。

## 啟動此整合前，您應先瞭解的事項{#what-you-should-know-before-activating-this-integration}

在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。

如此可確保在啟動前已有適當的最佳實務或先決條件，進而產生最佳且成功的整合。

### Adobe Analytics{#adobe-analytics}

檢視與Adobe Analytics相關之此「資料連接器」整合的下列資訊：

* **** 報表套裝特定：請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所需的報表套裝。
* **** 授權代表：請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。 啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。
* **** Data Warehouse™:此整合需要啟用「資料倉庫」才能產生再行銷區段。 如果您尚未啟用「資料倉庫」，請聯絡Adobe以取得詳細資訊。
* **** 收件者ID:整合需要我們擷取並儲存Analytics變數(eVar)中的「訪客ID」。 訪客ID（通常稱為「收件者ID」）是Delivra系統電子郵件位址的編碼或數值表示。 此「收件者ID」與網站上的下游訪客行為（購物車放棄、購買等）相關聯被拉進Delivra系統，並可用於再行銷目的。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。
* **** 外部追蹤：如果您目前未遵循針對您傳送的每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做，以確保成功整合。 如需詳細資訊，請參閱下方的Delivra一節。
* **** 隱私權規範：您應瞭解，透過啟用「收件者」或「訪客ID」追蹤，此功能可追蹤您網站訪客的個人識別資訊。 這涉及隱私權問題，需要貴組織實施適當的程式，例如向網站訪客提供通知並給予同意。

### Adobe Data Connectors整合的傳遞{#delivra-for-adobe-data-connectors-integration}

檢視與Delivra相關之此資料連接器整合的下列資訊：

* **** 有效傳送帳戶：若要使用「資料連接器」電子郵件整合，用戶端必須有有效的Delivra帳戶。
* **** Delivra的當前客戶：此項整合要求您同時成為Adobe和Delivra的客戶。 如果您目前不是Delivra的客戶，將沒有完成整合精靈所需的資訊。 如果您目前是Delivra的客戶，您將需要您的Delivra帳戶ID或指派給您組織的清單名稱，以完成整合精靈。 您必須提供與整合相關的公司名稱和帳戶ID給Delivra，才能完成設定。
