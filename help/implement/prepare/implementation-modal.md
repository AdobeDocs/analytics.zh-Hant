---
title: 實施強制回應視窗
description: 瞭解首次客戶實施 Adobe Analytics 的體驗。
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 實施強制回應視窗

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

「歡迎使用 Adobe Analytics 」強制回應視窗簡化了建立報表套裝的工作流程。Adobe 建議，每當組織需要更多報表套裝，均使用此工作流程。

![強制回應視窗螢幕擷取畫面](assets/implementation-modal.png)

## 必要條件

您的 Adobe ID 必須有權限存取 Adobe Analytics 和 Adobe Experience Platform Launch。如果您沒有 Launch 的存取權，系統可能會將您置於驗證迴圈中，無止盡地要求驗證您的憑證。請洽詢貴組織的系統管理員以取得 Launch 的存取權。

## 存取強制回應視窗

使用下列步驟，存取強制回應視窗以建立報表套裝。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下頂端的 9 格線圖示，然後按一下 [!UICONTROL Adobe Analytics]。
3. 如果您尚未建立報表套裝，強制回應視窗會自動顯示。如果此登入公司的報表套裝已存在，請按一下右上方的「說明」圖示，然後按一下[!UICONTROL 歡迎使用 Adobe Analytics]。

> [!NOTE] 只有透過 Adobe Experience Coud 登入時，才會顯示[!UICONTROL 歡迎使用 Adobe Analytics] 選項。如果您透過舊版網域登入，將無法使用此強制回應視窗。

## 建立報表套裝

按一下[!UICONTROL 開始設定]按鈕，開始建立報表套裝的工作流程。

![RS 精靈](assets/analytics-implementation-rs-wizard.png)

### 屬性類型

屬性類型可協助 Adobe 根據您實施 Analytics 的位置來決定某些後端設定。

* **網站**：如果您只打算為網站實施 Adobe Analytics。
* **原生行動應用程式**：如果您只打算為行動應用程式實施 Adobe Analytics。
* **兩者**：如果此報表套裝同時包含網站和行動應用程式的資料。

### 產業

指定您的主要商業模式。此設定可協助 Adobe 根據您的主要商業模式預先設定一些變數名稱和設定。

### 資料層

[資料層](data-layer.md)是 JavaScript 物件，可將實施中使用的所有變數整理到一個實用的位置。如需詳細資訊，請參閱[資料層](data-layer.md)。

### 資料儲存庫

為您的報表套裝提供好記的名稱。系統會根據好記名稱和登入公司自動產生您的報表套裝 ID (RSID)。

### 時區

確認 Adobe 是否偵測到報表套裝的正確時區。

### 估計每日頁面檢視次數

估計網站或應用程式每天的流量。此資訊可讓 Adobe 為您的報表套裝分配正確的處理資源量。

### 基本貨幣

決定報表套裝儲存貨幣值時所用的貨幣。

> [!IMPORTANT] 請務必指明正確的貨幣，尤其是如果您有與收入相關的報表要求。開始收集資料後就很難變更基本貨幣。

## 實施資源

建立報表套裝後，可藉由下列兩個選項其中一個繼續進行實施：

* **前往 Adobe Experience Platform Launch**：連結至 [launch.adobe.com](https://launch.adobe.com)，設定實施和下載部署程式碼。請參閱[透過 Launch 實施](../launch/overview.md)。Adobe 建議在多數情況下均使用 Launch。
* **下載實施程式碼**：提供用於下載 JavaScript 檔案的直接連結，以進行手動 JavaScript 實施。請參閱 [JavaScript 適用的 AppMeasurement](../js/overview.md)。
