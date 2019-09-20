---
description: 在 Adobe Analytics 中手動部署動態標籤管理時插入 AppMeasurement 代碼。
keywords: 動態標籤管理；連結帳戶；連結帳戶；編輯代碼；appmeasurement;appmeasurement代碼
seo-description: 在 Adobe Analytics 中手動部署動態標籤管理時插入 AppMeasurement 代碼。
seo-title: 插入核心 AppMeasurement 代碼
solution: Experience Cloud,Analytics,Target，動態標籤管理
title: 插入核心 AppMeasurement 代碼
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 插入核心 AppMeasurement 代碼

在 Adobe Analytics 中手動部署動態標籤管理時插入 AppMeasurement 代碼。

1. On the [!DNL Adobe Analytics] tool page, expand the **[!UICONTROL General]** section, then click **[!UICONTROL Open Editor]**.
1. 將您在部 [!DNL AppMeasurement_JavaScript*.zip] 署Adobe Analytics中下載的 [檔案解壓縮](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E)。

   如果您選擇使用自訂程式庫，當您開啟視窗，該視窗即會顯示最新的代碼版本。不需從管理主控台下載 zip。
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe 建議在此區段上新增下列代碼 *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Click **[!UICONTROL Save and Close]**.

   如果您要使用媒體模組、整合模組或實施外掛程式，也可以將之複製到代碼區域。動態標籤管理中的受管理代碼完全可以像傳統實施中的 JavaScript 檔案一樣來設定。

