---
description: 在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。
seo-description: 在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。
seo-title: 啟動此整合之前
title: 啟動此整合之前
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# 啟動此整合之前 {#before-you-activate-this-integration}

在啟動此整合之前，請針對您部署的Adobe Analytics®和電子郵件軟體檢視下列項目。

如此可確保在啟動前已有適當的最佳實務或先決條件，進而產生最佳且成功的整合。

## Adobe Analytics Requirements{#adobe-analytics-requirements}

檢視與Adobe Analytics相關之此資料連接器整合的下列資訊：

* **** 報表套裝專用：請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所要的報表套裝，且報表套裝包含資料。
* **** 可用和設定的Analytics變數：此整合需要10個自訂事件和1個自訂eVar。 請參 [閱Analytics整合變數](appfigures-before-activation.md#analytics-integration-variables)。

* **** 報表套裝已初始化為即時資料：如果您要針對此整合建立全新的報表套裝，則必須透過即時追蹤appFigures需求收到一些（至少一次點擊）資料。 如果尚未記錄即時資料，報表套裝將無法準備好接收整合的App Store資料。

* **** 與App Store的現有整合：此整合可回填13個月的資料。 為避免與您先前可能擁有的任何App Store資料提供者重疊，請聯絡您的appFigures代表。 讓他們知道您最後收到資料的日期。 appFigures會相應調整回填期間。

## appFigures Requirements{#appfigures-requirements}

檢視與appFigures相關之此資料連接器整合的下列資訊：

* **** appFigures的目前客戶：此項整合需要您同時使用Adobe和appFigures。 如果您目前不是appFigures企業計畫的使用者，將沒有完成整合精靈所需的資訊。 如需詳細資訊，請造訪網路上的appFigures。
* **** appFigures帳戶金鑰：必須有appFigures帳戶金鑰才能啟動appFigures資料連接器。 此帳戶金鑰可在「附加元件」區段中產生。 如需詳細 [資訊，請參閱](../appfigures-overview/t-appfigures-integration.md) 「設定整合」。

* **資料定版**:下載、銷售和排名資訊會在前7天每天同步。 7天後，資料會視為最終資料，不再更新。

## 定價{#pricing}

此資料連接器整合包括您需要注意的價格考量。

以下章節包含更多資訊: 

### Adobe定價考量事項 {#section-2d1c79c895a5479bad8fdd97961ba6a3}

目前，啟用此項整合不需支付任何費用。 不過，由於資料來源匯入，您可能會看到伺服器呼叫略有增加。

### appFigures定價考量 {#section-c6afad08c34b43e3a7a3637eea3328c3}

目前此整合併無相關費用。 此整合目前僅適用於企業客戶。 如需詳 [細資訊，請連絡appFigures](https://appfigures.com/support/contact) 。

## Analytics Integration Variables{#analytics-integration-variables}

appFigures的資料連接器整合使用Analytics變數來追蹤各種appFigures量度。

下表說明自動為appFigures整合啟動的Analytics變數。

### 必要變數 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>此整合使用專用的變數來處理應用程式商店資料，因此您不需要指派自訂商務變數和事件。

| 變數類型 | 名稱 | 填入方法 | 說明 |
|---|---|---|---|
| eVar | 應用程式商店物件 ID | 從appFigures匯入。 | 設定此eVar的瀏覽過期時間、最近的配置和基本子關聯。 |
| 事件（數值） | App Store 下載數 | 從appFigures匯入。 | 行動應用程式下載次數。 |
| 事件（數值） | App Store購買項目（在應用程式中） | 從appFigures匯入。 | 應用程式內購買項目和訂閱的數目。 |
| 事件（數值） | 應用程式商店排名 | 從appFigures匯入。 | 用於定義「平均appFigures計算量度」。 未直接使用。 |
| 事件（數值） | 應用程式商店排名除數 | 從appFigures匯入。 | 用於定義「平均appFigures計算量度」。 未直接使用。 |
| 事件（數值） | 應用程式商店評等 | 從appFigures匯入。 | 用於定義「平均appFigures計算量度」。 未直接使用。 |
| 事件（數值） | 應用程式商店評等除數 | 從appFigures匯入。 | 用於定義「平均appFigures計算量度」。 未直接使用。 |
| event(currency) | App Store收入（在應用程式中） | 從appFigures匯入。 | 應用程式內收入金額減去商店費用。 |
| event(currency) | App Store收入（一次） | 從appFigures匯入。 | 應用程式購買的總收入減去商店費用。 |
| event(currency) | App Store版稅（在應用程式中） | 從appFigures匯入。 | 未使用 |
| event(currency) | App Store版稅（一次） | 從appFigures匯入。 | 未使用 |
