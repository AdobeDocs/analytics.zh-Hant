---
description: 整合程式碼需要整合模組存在於您的Adobe Analytics部署中。
seo-description: 整合程式碼需要整合模組存在於您的Adobe Analytics部署中。
seo-title: 包含整合模組
title: 包含整合模組
uuid: e574f3db-49fa-4f72-bbcf-fd98540 d3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 包含整合模組{#including-the-integrate-module}

整合程式碼需要整合模組存在於您的Adobe Analytics部署中。

如果您尚未將Integrate模組當做部署的一部分，請依您擁有的實作類型完成下列步驟。

## 適用於AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. 解壓縮您從 **[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 代碼管理器]**」下載的AppMeasurement壓縮檔。

1. 開啓命名 [!DNL AppMeasurement_Module_Integrate.js]的檔案。
1. 複製檔案內容並貼到主要 [!DNL AppMeasurement.js] 檔案中。

   >[!NOTE]
   >
   >將它貼在檔案內DO NOT ALTER ANYTHING BELOW HIS LINE BELOW HANTHING BELOW LINE.

## 舊版程式碼(H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 從Data Connectors UI中的「資源」區域下載Integrate模組(位於「支援」標籤下)。

   ![](assets/h_code.png)

1. 複製檔案內容並貼入 [!DNL s_code] 檔案中。

   >[!NOTE]
   >
   >將它貼在檔案內DO NOT ALTER ANYTHING BELOW HIS LINE BELOW HANTHING BELOW LINE.

