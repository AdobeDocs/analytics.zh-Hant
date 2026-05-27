---
description: 管理員負責監控資料字典的健康狀況。 這包括元件是否正在收集資料、獲得核准、包含特定說明，以及沒有重複。
title: 監視資料字母排序健康狀況
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 100%

---

# 監視資料字母排序健康狀況 {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="共用主要元件"
>abstract="選取此選項後，主要元件會與可存取重複元件的每個人 (所有者和與之共用元件的任何人) 共用。 然後，這些使用者就可以從元件清單中選取主要元件，以供未來的專案使用。 但是，他們無法編輯該元件，即使他們是已合併之重複元件的所有者亦然。 <br/>此選項只有在主要元件是細分群體、計算量度或日期範圍時才可用。 量度和維度始終可供所有使用者使用。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="刪除所取代的重複項目"
>abstract="選取此選項後，合併的重複項目將不再可用。 如果您想要讓重複項目繼續可用，請取消選取此選項。"

<!-- markdownlint-enable MD034 -->

Analytics 管理員負責維持健康的資料字典。

## 健康資料字典的特徵

健康的資料字典是所有的元件：

* 正在使用且正在收集資料

* 包含有用的說明，讓使用者了解如何善加利用各種元件

* 沒有不必要的重複

* 經管理員核准

## 檢查資料字典的健康狀況

在您的資料字典中識別健康問題：

1. 開啟 Analysis Workspace 專案。

1. 選取 Analysis Workspace 左邊的資料字典圖示。 (存取資料字典的替代方法說明請見[資料字典概觀](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![資料字典管理員檢視](assets/data-dictionary-admin.png)

1. 確定在下拉選單中選取正確的報告套裝。

1. 在 [!UICONTROL **字典健康**] 標籤上選擇以下任一選項旁邊的 [!UICONTROL **檢視**]：

   * [!UICONTROL **個元件缺少說明**]

   * [!UICONTROL **個元件有重複項**]

   * [!UICONTROL **個元件未連接任何資料**]

   根據您所選取的，適當的篩選器將套用於資料字典，並且僅顯示相關的元件。

1. 編輯任何元件以提升資料字典的健康狀況。 有關如何在資料字典中編輯元件的資訊，請參閱[在資料字典中編輯元件條目](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)。
