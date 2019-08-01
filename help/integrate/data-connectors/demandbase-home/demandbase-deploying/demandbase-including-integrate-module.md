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
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

整合程式碼需要整合模組存在於您的Adobe Analytics部署中。

如果您尚未將Integrate模組當做部署的一部分，請依您擁有的實作類型完成下列步驟。

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >將它貼在檔案內DO NOT ALTER ANYTHING BELOW HIS LINE BELOW HANTHING BELOW LINE.

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 從Data Connectors UI中的「資源」區域下載Integrate模組(位於「支援」標籤下)。

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >將它貼在檔案內DO NOT ALTER ANYTHING BELOW HIS LINE BELOW HANTHING BELOW LINE.

