---
title: 使用Adobe Experience Platform移動SDK實施Adobe Analytics
description: 使用Adobe Experience Platform資料收集中的移動SDK擴展將資料發送到Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---


# 使用Adobe Experience Platform移動SDK實施Adobe Analytics

Adobe Experience Platform移動軟體開發工具包幫助您的移動應用中提供Adobe的Experience Cloud解決方案和服務。 它適用於Android、iOS和各種跨平台開發框架。 配置通過Adobe Experience Platform資料收集UI處理。

要使用Mobile SDK將資料發送到Adobe Experience Edge，請執行以下操作：

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection)。
2. 從清單中選擇所需的屬性，或 [設定移動屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。
3. 轉到「擴展」頁籤，然後安裝 [邊緣網路的標識](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) 擴展。
4. 安裝 [Adobe Experience Platform邊緣網路](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension)。
5. [配置資料流](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)，將Adobe Analytics添加為指向所需報告套件的服務。
6. [安裝SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) 在你的移動應用上。

>[!IMPORTANT]
>
>資料收集UI中也提供Adobe Analytics擴展。 如果安裝此擴展，則不會利用XDM或邊緣網路。
