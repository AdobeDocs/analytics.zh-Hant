---
description: 「計算量度」頁面提供許多管理量度的方式，例如共用、篩選、標籤、核准、複製、刪除和標示為我的最愛。
title: 計算量度管理器
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: bd588a06546c59e9a5a61b0260229bafaba150f1
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 11%

---

# 計算量度管理器

「計算量度」頁面提供許多管理量度的方式，例如共用、篩選、標籤、核准、複製、刪除和標示為我的最愛。

「計算量度」頁面會顯示您所擁有以及已經與您共用的區段。 管理層級使用者可以查看組織中的所有自訂量度。

<!-- add screenshot -->

## 存取計算量度管理員

1. 在Adobe Analytics中，選取 [!UICONTROL **元件**] > [!UICONTROL **計算量度**].

## 計算量度管理員中的可用動作

在計算量度管理員中，您可以：

* [篩選計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [將計算量度標示為我的最愛](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [核准計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [標記計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [共用計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* 將計算量度匯出至CSV檔案。

* [複製計算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* 刪除計算量度

## 設定欄

您可以透過設定顯示的欄，來設定在「計算量度管理員」中為每個計算量度顯示的資訊。

若要在計算量度管理員中設定可見欄：

1. 在Adobe Analytics中，選取 **[!UICONTROL 元件]** 索引標籤，然後選取 **[!UICONTROL 計算量度]**.

1. 在計算量度管理員中，選取 **自訂欄** 圖示 ![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您要在計算量度管理員中顯示的欄。

   可使用下列欄:

   | 欄標題 | 說明 |
   |---|---|
   | 我的最愛 | 在每個計算量度旁邊顯示星號圖示，讓您將計算量度標示為我的最愛。 如需詳細資訊，請參閱 [將計算量度標示為我的最愛](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | 標題和說明 | 這些值會在計算量度產生器中提供。 若要編輯標題和說明，請選取標題連結以開啟計算量度產生器。 |
   | 報表套裝 | 指出上次將量度儲存到的目標報表套裝。 |
   | 擁有者 | 指出擁有自訂量度的人員。如果您不是管理員，就只能看見自己所擁有或已共用給您的量度。 |
   | 標記 | 顯示套用至量度的標籤（由您自己或與您共用計算量度的人員套用）。 |
   | 共用對象 | 列出您共用計算量度的個人或群組（僅限管理員）或「全部」（僅限管理員）。 <p>共用計算量度時，計算量度名稱旁會顯示共用圖示。</p> |
   | 修改日期 | 表示上次修改自訂量度的日期。 |
   | 使用位置 | **注意：** 此功能處於發行的有限測試階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱 [Adobe Analytics功能發行](/help/release-notes/releases.md).<p>顯示計算量度目前使用中的元件數量。 <p>例如，如果計算量度用於40個專案和2個警報，則此欄的值顯示為 [!UICONTROL **42個元件**].</p> <p>選取此欄中的值，可檢視使用計算量度的明細(例如 [!UICONTROL **專案(40)**]， [!UICONTROL **警報(2)**])。</p><p>計算量度可用於下列任何元件型別：</p> <ul><li>警報</li><li>專案</li><li>已排程的專案</li></ul><p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</p><p>您可以使用 [資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 連同此資訊可協助您追蹤並更瞭解組織中如何使用元件。</p><p>此 [!UICONTROL **使用位置**] 預設不會顯示欄。 [設定欄](#configure-columns) 以顯示。</p> |
   | 上次使用 | **注意：** 此功能處於發行的有限測試階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱 [Adobe Analytics功能發行](/help/release-notes/releases.md).<p>顯示計算度量最後用於下列任何元件型別的日期：</p> <ul><li>警報</li><li>計算量度</li><li>專案</li><li>已排程的專案</li></ul> <p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</p><p>您可以使用 [資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 連同此資訊可協助您追蹤並更瞭解組織中如何使用元件。 |

   {style="table-layout:auto"}
