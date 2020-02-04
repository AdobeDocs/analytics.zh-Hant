---
title: 實作模式
description: 瞭解首次客戶實施 Adobe Analytics 的體驗。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 實作模式

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

「歡迎使用Adobe Analytics」模式視窗可簡化建立報表套裝的工作流程。 Adobe建議您在組織中需要更多報表套裝時，使用此工作流程。

![模式螢幕擷取](assets/implementation-modal.png)

## 必備條件

您的Adobe ID必須能夠存取Adobe Analytics和Adobe Experience Platform Launch。 如果您沒有啟動的存取權，則可將您置於驗證循環中，驗證循環會要求無限期驗證您的認證。 請洽詢您組織中的系統管理員，以取得Launch的存取權。

## 存取模型

使用下列步驟存取模型以建立報表套裝。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. Click the 9-grid icon at the top, then click [!UICONTROL Adobe Analytics].
3. 如果您尚未建立報表套裝，則會自動顯示該模型。 如果此登入公司有報表套裝，請按一下右上方的「說明」圖示，然後按一下「歡 [!UICONTROL 迎使用Adobe Analytics]」。

> [!NOTE] 只有 [!UICONTROL 當您透過Adobe Experience cloud登入時，才會顯示「歡迎使用Adobe Analytics] 」選項。 如果您透過舊版網域登入，此模型將無法使用。

## 建立報表套裝

按一下「 [!UICONTROL 開始設定] 」按鈕，開始建立報表套裝工作流程。

![RS精靈](assets/analytics-implementation-rs-wizard.png)

### 屬性類型

屬性類型可協助Adobe根據您要在何處實作Analytics，來判斷某些後端設定。

* **網站**:如果您只想為網站實作Adobe Analytics。
* **原生行動應用程式**:如果您只想為行動應用程式實作Adobe Analytics。
* **兩者**:如果此報表套裝同時包含網站和行動應用程式的資料。

### 產業

指定您的主要商業模式。 此設定可協助Adobe根據您的主要商業模型預先設定一些變數名稱和設定。

### 資料層

資 [料層](data-layer.md) 是JavaScript物件，可將實作中使用的所有變陣列織在單一有用的位置。 如需詳 [細資訊](data-layer.md) ，請參閱資料層。

### 資料儲存庫

為您的報表套裝提供好記的名稱。 您的報表套裝ID(RSID)會根據好記名稱和登入公司自動產生。

### 時區

驗證Adobe是否偵測到報表套裝的正確時區。

### 預計的每日頁面檢視次數

估計您的網站或應用程式每天的流量。 這項資訊可讓Adobe為您的報表套裝分配正確的處理資源量。

### 基本貨幣

確定報表套裝所儲存的貨幣值。

> [!IMPORTANT] 請務必指出正確的貨幣，尤其是如果您有收入相關的報告要求。 資料收集開始後，很難變更基本貨幣。

## 實作資源

建立報表套裝後，您有下列兩個選項之一可繼續實施：

* **前往Adobe Experience Platform Launch**:連結至 [launch.adobe.com](https://launch.adobe.com) ，以設定實作和下載部署程式碼。 請參閱[透過 Launch 實作](../launch/overview.md)。Adobe建議在大多數情況下使用Launch。
* **下載實施代碼**:提供下載JavaScript檔案的直接連結，以進行手動JavaScript實作。 請參閱 [JavaScript 適用的 AppMeasurement](../js/overview.md)。
