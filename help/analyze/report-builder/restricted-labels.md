---
title: 什麼是 Report Builder 中受限制的標籤
description: 說明 Report Builder 中受限制的標籤
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: aa2182f9-a140-4239-b2fb-f723e2767260
source-git-commit: c333a82848ed74a002a07f8c5e2857426a78425c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Report Builder 中受限制的標籤

一般而言，Adobe Analytics中的資料控管相關設定是從Adobe Experience Platform繼承的。 Adobe Analytics與Adobe Experience Platform資料控管之間的整合可讓您標示敏感的Adobe Analytics資料強制執行隱私權原則。

在Experience Platform使用的資料集上建立的隱私權標籤和原則，可以在Adobe Analytics報表套裝工作流程中顯示。 這些標籤會阻止或警告從敏感性欄位建立量度和/和維度的使用者。如需資料集的資訊，請參閱 [資料集概觀](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=zh-Hant)。

此外，從Adobe Analytics （透過報告、匯出、API等）匯出資料時，便會新增警告或標籤，以通知使用者報告包含需要以特定方式處理敏感性資訊。

此整合可讓您更輕鬆地管理合規性。在您組織中的資料監管員可以設定限制使用的原則。因此，您的Adobe Analytics使用者可以更自信地使用資料，瞭解資料符合資料管理員定義的原則。

如需詳細資訊，請參閱[Adobe Analytics和資料控管](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=zh-Hant)

## 查看 Report Builder 中受限制的資料

Adobe Analytics中出現兩個Adobe定義的原則，這些原則會影響報告、下載和共用：

* 強制執行 Analytics 原則
* 強制執行下載原則

受這些原則影響的元件會顯示為灰色。當您將滑鼠懸停在套用了原則的元件上時，會顯示一個包含以下內容的註解：**原則已套用於此欄位，禁止使用此資料。**&#x200B;如需詳細資訊，請參閱 [標籤與原則](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=zh-Hant)。

![指示禁止使用資料的原則備註。](assets/rb-restricted-label.png)

## 更新報告包含受限制的資料

如果使用者建立的 Report Builder 報告包含後來受到限制的資料元素，則重新整理報告時會顯示錯誤訊息。

![資料元素稍後受到限制後所顯示的錯誤訊息。](assets/error-restricted-data.png)
