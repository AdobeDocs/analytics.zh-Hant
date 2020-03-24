---
description: 在啟用這項整合之前，請針對您部署的 Adobe Analytics® 和您的電子郵件軟體檢閱下列項目。
title: 啟動這項整合的事前準備
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 啟動這項整合的事前準備 {#before-you-activate-this-integration}

在啟用這項整合之前，請針對您部署的 Adobe Analytics® 和您的電子郵件軟體檢閱下列項目。

這麼做可確保在啟動前已具備適當的最佳實務或必要條件，進而達成最佳的成功整合。

## Adobe Analytics 要求{#adobe-analytics-requirements}

檢閱與 Adobe Analytics 相關的下列 Data Connectors 整合資訊：

* **報表套裝專用：**&#x200B;請注意，此整合供報表套裝專用。啟動整合之前，請確定已選取您所需的報表套裝，且報表套裝中含有資料。
* **可用和已設定的 Analytics 變數：**&#x200B;此整合需要 10 個自訂事件和 1 個自訂 eVar。請參閱 [Analytics 整合變數](appfigures-before-activation.md#analytics-integration-variables)。

* **透過即時資料初始化的報表套裝：**&#x200B;如果您要針對此整合建立全新的報表套裝，必須已透過即時追蹤 appFigures 要求收到一些資料 (至少一個點擊)。如果尚未記錄即時資料，報表套裝將無法準備好接收整合的應用程式商店資料。

* **與應用程式商店的現有整合：**&#x200B;此整合可回填 13 個月的資料。為避免與您先前可能擁有的任何應用程式商店資料提供者重疊，請聯絡您的 appFigures 代表，讓他們知道您最後收到資料的日期，appFigures 會據此調整回填期間。

## appFigures 要求{#appfigures-requirements}

檢閱下列資訊，瞭解這個與 appFigures 相關的 Data Connectors 整合：

* **appFigures 的目前客戶：**&#x200B;此項整合需要您同時為 Adobe 和 appFigures 的使用者。如果您目前不是 appFigures 企業方案的使用者，就沒有完成整合精靈所需的資訊。如需詳細資訊，請造訪 appFigures 網站。
* **appFigures 帳戶金鑰：**&#x200B;必須有 appFigures 帳戶金鑰才能啟用 appFigures Data Connector。此帳戶金鑰可在「附加元件」部分中產生。如需詳細資訊，請參閱[設定整合](../appfigures-overview/t-appfigures-integration.md)。

* **資料最終處理**：每天都會同步前 7 天的下載、銷售和排名資訊。7 天後會將資料視為最終資料且不再更新。

## 定價{#pricing}

此 Data Connectors 整合包含您需要注意的定價考量事項。

以下章節包含更多資訊: 

### Adobe 定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

目前，啟用此項整合不需支付任何費用。不過，由於資料來源匯入，您可能會看到伺服器呼叫略有增加。

### appFigures 定價考量事項 {#section-c6afad08c34b43e3a7a3637eea3328c3}

目前此整合無任何相關費用。此整合目前僅開放企業客戶使用。如需詳細資訊，請[聯絡 appFigures](https://appfigures.com/support/contact)。

## Analytics 整合變數{#analytics-integration-variables}

appFigures 的 Data Connectors 整合使用 Analytics 變數來追蹤各種 appFigures 量度。

下表說明為 appFigures 整合自動啟用的 Analytics 變數。

### 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] 此整合針對應用程式商店資料使用專用的變數，因此您不需要指派自訂商務變數和事件。

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| eVar | 應用程式商店物件 ID | 從 appFigures 匯入。 | 使用造訪到期時間、最近的配置和基本子關聯設定此 eVar。 |
| 事件 (數值) | App Store 下載數 | 從 appFigures 匯入。 | 行動應用程式下載次數。 |
| 事件 (數值) | 應用程式商店購買數 (應用程式內) | 從 appFigures 匯入。 | 應用程式內購買項目和訂閱的數目。 |
| 事件 (數值) | 應用程式商店排名 | 從 appFigures 匯入。 | 用於定義平均 appFigures 計算量度。不直接使用。 |
| 事件 (數值) | 應用程式商店排名除數 | 從 appFigures 匯入。 | 用於定義平均 appFigures 計算量度。不直接使用。 |
| 事件 (數值) | 應用程式商店評等 | 從 appFigures 匯入。 | 用於定義平均 appFigures 計算量度。不直接使用。 |
| 事件 (數值) | 應用程式商店評等除數 | 從 appFigures 匯入。 | 用於定義平均 appFigures 計算量度。不直接使用。 |
| 事件 (貨幣) | 應用程式商店收入 (應用程式內) | 從 appFigures 匯入。 | 應用程式內收入減去商店費用金額。 |
| 事件 (貨幣) | 應用程式收入 (一次性) | 從 appFigures 匯入。 | 應用程式購買項目的總收入減去商店費用。 |
| 事件 (貨幣) | 應用程式版稅 (應用程式內) | 從 appFigures 匯入。 | 未使用 |
| 事件 (貨幣) | 應用程式版稅 (一次性) | 從 appFigures 匯入。 | 未使用 |
