---
title: Campaign 追蹤工作流程
description: 使用 Adobe Analytics 追蹤您的行銷工作。
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 100%

---

# Campaign 追蹤工作流程

如果您的組織想要追蹤行銷工作的績效和點擊率，您可以使用下列流程。 這些步驟中的每一步在下方都有專屬區段，其中包含更多詳細資訊。

1. [建立追蹤程式碼產生流程](#establish-a-tracking-code-generation-process)
1. [將所需的追蹤程式碼新增到電子郵件中](#add-the-desired-tracking-code-to-the-email)
1. [設定或調整您的 Adobe Analytics 實施以包含追蹤程式碼資料](#include-campaign-variables-in-your-implementation)
1. [檢視 Analysis Workspace 中的報告](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/tw/products/campaign/adobe-campaign.html) 可以有助於簡化這些步驟中的每一步，進而從您的行銷工作中獲取最大價值。如需詳細資訊，請聯絡 Adobe 業務代表。

## 建立追蹤程式碼產生流程

每個組織對追蹤程式碼都有不同的需求。某些組織可能需求不大，而手動建立追蹤程式碼就已綽綽有餘。 其他組織可能希望進一步控制追蹤，並擁有多個系統來建立所需的追蹤程式碼。如果您的組織除了 Adobe Analytics 之外也使用 Google Analytics，您的組織可能已建有 `utm` 追蹤程式碼模型。

無論您選擇如何建立或產生追蹤程式碼，擁有一致的系統可讓您的組織更容易將追蹤程式碼群組在一起以進行報告。結構一致的追蹤程式碼允許您建立[分類規則](/help/components/classifications/crb/classification-rule-builder.md)，讓您能夠分析分類績效。

## 將所需的追蹤程式碼新增到 URL 中

獲得所需的追蹤程式碼值後，您可以將其新增到您在線上張貼的任何連結中，例如廣告、社交媒體或電子郵件。新增這些追蹤程式碼通常發生在連結的查詢字串中。 您使用哪個查詢字串參數取決於您組織的追蹤要求；一個常見的查詢字串參數是 `cid` (行銷活動 ID 的縮寫)。某些也使用 Google Analytics 的組織可能已經有多個活動查詢字串參數，例如 `utm_source`、`utm_medium` 和其他。

將查詢字串新增到電子郵件中的連結看起來如下：

```text
https://example.com?cid=EM989027
```

## 在實施中包含行銷活動變數

Adobe Analytics 有專屬的[追蹤程式碼](/help/components/dimensions/tracking-code.md)維度，您可以用來衡量整個組織的各種行銷工作。 但是，不同的組織可能有不同的追蹤要求。 重要的是要參考您組織的[解決方案設計文件](../prepare/solution-design.md)，一貫地追蹤正確變數中的正確值。

如果您的組織尚未設定行銷活動追蹤，您可以調整實施以設定 [`campaign`](/help/implement/vars/page-vars/campaign.md) 變數。 請參閱 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) 方法來了解如何收集特定於您組織實施的查詢字串參數值。

如果您的組織收集 `utm` 查詢字串，您可以選擇：

* 將 `utm` 查詢字串作為串連值全部傳送至追蹤程式碼維度。 然後您可以使用[分類規則](/help/components/classifications/crb/classification-rule-builder.md)建立其他維度，專注於各個 `utm` 參數。 此方法具有較複雜的學習曲線，但不使用任何額外的 eVar。
* 將每個 `utm` 查詢字串傳送到個別的 [eVar](/help/components/dimensions/evar.md)。 此方法總體上更易於實施，但需要使用額外的 eVar。

## 檢視 Analysis Workspace 中的報告

適當設定好實施以收集追蹤程式碼資料後，您可以在 Analysis Workspace 中檢視報告。

1. 登入 [Adobe Experience Cloud](https://experience.adobe.com) 並選取 [!UICONTROL Adobe Analytics]。
1. 建立 [Workspace 專案](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。
1. 在左側的元件清單中，將[追蹤程式碼](/help/components/dimensions/tracking-code.md)維度拖曳到工作區畫布。
1. 將所需的量度，例如[瀏覽次數](/help/components/metrics/visits.md)或[訂購量](/help/components/metrics/orders.md)，拖曳到工作區畫布的右側。

![行銷活動追蹤報告](../assets/campaign-tracking-report.png)
