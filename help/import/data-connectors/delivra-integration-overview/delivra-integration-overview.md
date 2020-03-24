---
description: 此 Adobe® Data Connectors™ 電子郵件整合功能結合了 Analytics® 與 Delivra 電子郵件行銷的行為資訊，成為一項功能強大的工具，可重新定義成功測量，並透過更具相關性的訊息鎖定對象。
title: Adobe Analytics 的 Delivra Data Connector
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics 的 Delivra Data Connector{#delivra-data-connector-for-adobe-analytics}

此 Adobe® Data Connectors™ 電子郵件整合功能結合了 Analytics® 與 Delivra 電子郵件行銷的行為資訊，成為一項功能強大的工具，可重新定義成功測量，並透過更具相關性的訊息鎖定對象。

向這些市場區塊傳遞相關電子郵件訊息可帶來全新的收入商機，進而推動全新和現有電子郵件促銷活動的轉換和收入。舉例來說，根據瀏覽期間檢視的產品或放棄的購物車中的產品來傳送相關電子郵件訊息，經證明對收入有顯著影響，而且對成本的影響最小，因為這只是運用您網站已獲得的訪客。這種行銷效率的提升，是整合 Analytics 與 Delivra 的主要優點之一。此外，這項整合會自動將電子郵件量度與 Analytics 資料同步化，封閉迴圈報表的同步頻率可達每小時一次。

## 主要優點{#key-benefits}

這項整合包含下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報表介面
* 透過轉換和對收入和網站成功的貢獻，最佳化電子郵件促銷活動。
* 根據動態行銷區段，再行銷關鍵訪客和市場區塊
* 提供幾乎即時的電子郵件量度同步功能，而不是標準的每天一次

## 動態行銷區段{#dynamic-marketing-segments}

此 Data Connectors 電子郵件整合支援動態行銷區段，可協助您推動業務。

這項整合具備下列立即可用的行銷區段：

* **購買設定檔：**&#x200B;透過鎖定訪客購買模式的促銷活動，增加重複訂購和平均訂購值。
* **產品/內容檢視行為設定檔：**&#x200B;根據產品檢視和內容存取分析，透過行銷區段觸及潛在客戶。
* **購物車放棄設定檔：**&#x200B;透過專為猶豫是否要將購物車完成結帳的訪客量身打造的微調促銷活動，協助將訪客轉化為客戶。
* 客戶也可以根據其使用者的需求，建立並排程自訂的再行銷區段。

## 整合程序與必要條件{#integration-procedure-and-prerequisites}

使用「隨插即用」精靈，直觀的逐步程序將引導您完成系統同步點，並初始化整合。

此 Data Connectors 整合需要下列項目：

### Adobe 必要條件 {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe Data Warehouse
* Adobe Analytics 帳戶
* 可用和設定的 Analytics 變數，包括 eVar 和自訂事件。

### Delivra 必要條件：{#section-bcb904574ccf42308bcf7a15e45b4d58}

* 啟用「Adobe 整合」選項的有效 Delivra 專業級 (或以上) 帳戶。

## 定價{#pricing}

此 Data Connectors 整合包含您需要注意的定價考量事項。

以下章節包含更多資訊: 

### Adobe 定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

此整合可能會產生週期性和實施的相關費用。如需價格方面的詳細資訊，請聯絡您的 Adobe 客戶代表。

### Delivra 定價考量事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

此整合可能會產生相關費用。

* 請聯絡您的 Delivra 客戶代表，以取得價格詳細資訊。

## 啟用這項整合前，您應先瞭解的事項{#what-you-should-know-before-activating-this-integration}

在啟用這項整合之前，請針對您部署的 Adobe Analytics® 和您的電子郵件軟體檢閱下列項目。

如此可確保在啟用之前已有適當的最佳實務或必要條件，進而產生最佳且成功的整合。

### Adobe Analytics{#adobe-analytics}

檢閱與 Adobe Analytics 相關的下列 Data Connectors 整合資訊：

* **報表套裝特定：**&#x200B;請注意，這項整合是報表套裝專用的。在啟用整合之前，請確定您已選取所需的報表套裝。
* **授權代表：**&#x200B;請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任合作夥伴之一 (如適用) 的服務合約產生費用。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。
* **Data Warehouse™：**&#x200B;這項整合需要啟用 Data Warehouse，才能產生再行銷區段。如果您尚未啟用 Data Warehouse，請聯絡 Adobe 瞭解詳情。
* **收件者 ID**：整合需要我們在 Analytics 變數 (eVar) 中擷取並儲存「訪客 ID」。訪客 ID (通常稱為「收件者 ID」) 是來自 Delivra 系統之電子郵件地址的編碼或數值表示。此「收件者 ID」與網站上的下游訪客行為 (購物車放棄、購買等等) 相關聯這些資料會被提取至 Delivra 系統中，並可用於再行銷目的。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **外部追蹤：**&#x200B;如果您目前未遵循針對您傳送之每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做以確保成功整合。如需詳細資訊，請參閱下方的 Delivra 區段。
* **隱私權法規遵循：**&#x200B;您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私權問題，需要您的組織實施適當的程序，例如向您的網站訪客提供通知並授予同意。

### Adobe Data Connectors 整合的 Delivra{#delivra-for-adobe-data-connectors-integration}

檢閱與 Delivra 相關的下列 Data Connectors 整合資訊：

* **有效的 Delivra 帳戶：**&#x200B;若要使用 Data Connectors 電子郵件整合，用戶端必須具備有效的 Delivra 帳戶。
* **Delivra 的目前客戶：**&#x200B;這項整合需要您同時身為 Adobe 和 Delivra 的客戶。如果您目前不是 Delivra 的客戶，便不具備完成整合精靈所需的資訊。如果您目前是 Delivra 的客戶，您需要您的 Delivra 帳戶 ID，或指派給您的組織的清單名稱，以便完成整合精靈。您必須向 Delivra 提供與整合相關聯的公司名稱和帳戶 ID，才能完成設定。
