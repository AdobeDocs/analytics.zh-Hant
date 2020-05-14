---
description: 說明Adobe Analytics的全新連續功能發行策略
title: Adobe Analytics —— 功能發佈策略
translation-type: tm+mt
source-git-commit: 0b00405e9e27a427a85b0f4a0d970671ada4aa67
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# Adobe Analytics —— 功能發佈策略

過去，Adobe Analytics功能的發行會遵循固定的每月計畫。 從2020年4月開始，Adobe Analytics將改採持續的傳送模型，讓功能部署更具延展性、更分階段。

## 發佈策略

[!UICONTROL 分析工作區] (Analysis Workspace)使用功能標幟（也稱為「切換」）來控制新功能的可見性，允許在完整版發行之前進行受控縮放測試。 此發行策略包含下列階段：

* **發佈至生產(RTP)**: 程式碼會發佈至生產環境，並在「分析工作區」中關閉功能可見性。 **注意**: 目前，2.0 Analytics API中可能提供此功能。

* **有限測試**: 階段發行從內部Adobe使用者的測試開始。 然後，在兩個月內，此版本的可用性從0%擴充至100%。 分階段推出會在Experience Cloud組織層級進行，因此組織中所有有權使用的使用者都會獲得相同的體驗。

* **通用性(GA)**: 此功能可供100%有權使用的Experience Cloud組織使用，功能發行已完成。

在每個功能版本中，從RTP到GA的時間軸可能會有所不同。 其目標是縮短發行時間，以便在發行開始(RTP)後的2個月內，將推出GA功能。

## 福利

分階段發行可讓Adobe更精確地擴充軟體部署程式，並確保功能在全面推出之前已完全強化。 此外，還可讓功能一推出，就能立即發佈，而不需附加固定的每月發行視窗。

## 常見問題解答

| 問題 | 回答 |
|---|---|
| 我是否可要求提早存取功能？ | 不可以，不會授與提早存取權。<br>如果您想要測試早期的Analytics概念，建議您嘗試 [Adobe Analytics Labs](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/tech-previews/overview.html) ，以提供我們領先業界的創新意見回應。 |
| 此發行策略是否會影響我存取功能？ | 不可以，功能一旦通過正式登入，您就可以存取該功能（如果該功能已包含在您的Analytics套件中）。<br>您可以在「管理員 [!UICONTROL >公司設定] >功能存取層級」下，檢視Analytics套 [!UICONTROL 件的詳細資訊][](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)。 |