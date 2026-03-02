---
title: 設定Report Builder
description: 透過完整指南瞭解如何安裝和設定Adobe Analytics Report Builder for Excel。 緊密整合的逐步設定指示。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 39%

---

# 設定Report Builder

本文概述在[!DNL Microsoft] [!DNL Excel]中針對Adobe Analytics使用Report Builder的需求。 以及如何安裝及設定增益集。

## 需求

下列作業系統和網頁瀏覽器支援適用於Adobe Analytics的Report Builder。

### macOS

- 10.x 或更新版本的 macOS
- 所有[!DNL Microsoft] [!DNL Excel]版本

### Windows

- 1904 或更新版本的 Windows 10
- [!DNL Excel]版本2106或更新版本

  所有Windows案頭[!DNL Excel]使用者都必須安裝Microsoft Edge Webview2，才能使用增益集。 若要安裝控制器：

   1. 前往 <https://aka.ms/webview2installer>。
   1. 選取並下載 Evergreen Standalone Installer。
   1. 遵循安裝提示進行。

### 網頁版 Office

- 支援所有的瀏覽器和版本


## Report Builder Excel 增益集

您必須安裝Report Builder [!DNL Excel]增益集，才能使用Adobe Analytics的[!DNL Report Builder]。 安裝Report Builder [!DNL Excel]增益集後，您就可以從開啟的[!DNL Excel]活頁簿存取Report Builder。

### 下載並安裝 Report Builder 增益集

若要下載並安裝 Report Builder 增益集

1. 啟動[!DNL Excel]並開啟新的活頁簿。

1. 選取&#x200B;**[!UICONTROL 插入]** > **[!UICONTROL 取得增益集]**。

1. 在 Office 增益集對話框中，選取「商店」索引標籤。

1. 搜尋「Report Builder」並按一下&#x200B;**[!UICONTROL 新增]**。

1. 在[授權條款與隱私權原則]對話方塊中，按一下[繼續]。**&#x200B;**

**如果未顯示「商店」索引標籤**

1. 在[!DNL Excel]中，選取檔案>帳戶>管理設定。

1. 勾選「啟用選擇性連線體驗」旁的方框。

1. 重新啟動[!DNL Excel]。

**如果您的組織封鎖對 Microsoft Store 的存取權**

- 和您的 IT 或安全小組洽詢，要求核准使用 Report Builder 增益集。取得核准後，在Office增益集對話方塊中，選取&#x200B;**[!UICONTROL 管理員管理的]**&#x200B;索引標籤。

  ![Office增益集對話方塊中的[管理員管理]索引標籤。](./assets/image1.png)

- 或者，您可以手動擷取[資訊清單檔案](https://reportbuilder.an.adobe.com/manifest.xml)，並將檔案託管在您自己的IT基礎結構上。 <br/>請依照Microsoft Office [線上檔案](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish)取得如何安裝未從Microsoft市集提供的Excel資訊清單檔案的說明。

安裝Report Builder增益集後，「首頁」索引標籤下的[!DNL Excel]功能區中會顯示Report Builder圖示。

![Excel中的Report Builder圖示](/help/analyze/report-builder/assets/rb_app_icon.png)

## 登入 Report Builder

為您的作業平台或瀏覽器安裝Report Builder for Excel增益集後，請依照下列步驟登入Report Builder。

1. 開啟 Excel 活頁簿。

1. 按一下 Report Builder 圖示，即可啟動 Report Builder。

1. 在Adobe Report Builder工具列中，按一下&#x200B;**[!UICONTROL 登入]**。

   ![按一下Report Builder登入按鈕。](/help/analyze/report-builder/assets/rb_login.png)

1. 輸入您的 Adobe Experience ID 帳戶資訊。您的帳戶資訊應該與您的Adobe Analytics憑證相符。

   ![您的登入圖示和組織。](/help/analyze/report-builder/assets/image4.png)

登入後，您的登入圖示和組織會顯示在面板頂端

## 切換組織

第一次登入時，您會登入指派給您的設定檔的預設組織。

1. 按一下您登入時顯示的組織名稱。

1. 從可用組織清單中選取一個組織。只會列出您有存取權限的組織。

   ![您可以存取的組織清單。](/help/analyze/report-builder/assets/image5.png)

## 登出

您可從使用者設定檔登出 Report Builder。

1. 將變更儲存在任何開啟的活頁簿。

1. 按一下個人頭像圖示，以顯示您的使用者設定檔。

   ![您的使用者設定檔頭像和[登出]按鈕。](/help/analyze/report-builder/assets/image6.png)

1. 按一下「**登出**」。
