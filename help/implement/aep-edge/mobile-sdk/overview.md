---
title: 使用 Adobe Experience Platform Mobile SDK 實作 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Mobile SDK 擴充功能傳送資料給 Adobe Analytics。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '206'
ht-degree: 100%

---

# 使用 Adobe Experience Platform Mobile SDK 實作 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助於在行動應用程式中強化 Adobe 的 Experience Cloud 解決方案和服務。 它適用於 Android、iOS 及各種跨平台開發架構。 透過 Adobe Experience Platform Data Collection 進行設定。

若要使用 Mobile SDK 傳送資料給 Adobe Experience Edge：

1. 登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 從清單中選取所需的屬性，或[設定行動屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。
3. 前往「擴充功能」索引標籤，並安裝[適用於 Edge Network 的身分識別](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network)擴充功能。
4. 安裝 [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension)。
5. [設定資料串流](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)，新增 Adobe Analytics 當作指向所需報表套裝的服務。
6. 在您的行動應用程式上[安裝此 SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk)。

>[!IMPORTANT]
>
>Adobe Analytics 擴充功能也可以在 Adobe Experience Platform Data Collection 中取得。如果您安裝此擴充功能，就不會利用 XDM 或 Edge Network。
