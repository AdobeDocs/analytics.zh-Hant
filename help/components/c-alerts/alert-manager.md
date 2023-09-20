---
description: 管理警報。
title: 警報管理器概觀
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 69b763bc5740223be54309c0c0b98f40536c4d7e
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 33%

---

# 警報管理器

警報管理員的結構相當類似於 [區段管理員](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hant) 和 [計算量度管理員](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=zh-Hant).

![](assets/alert-manager.png)

## 存取「警報管理器」

1. 在Adobe Analytics中，選取 [!UICONTROL **元件**] > [!UICONTROL **警報**].

## 「警報管理器」中的可用動作

在「警報管理器」中，您可以：

* 按一下&#x200B;**[!UICONTROL 「+ 新增」]**&#x200B;以存取警報產生器。
* 標記警報。這可讓您組織警報以方便使用。
* 刪除警報。
* 重新命名警報。
* 核准警報。
* 複製警報。
* 啟用/停用警報。
* **更新**&#x200B;警報到期日。選取一或多個警報後，按一下&#x200B;**[!UICONTROL 「續訂」]**&#x200B;即可續訂警報。如此一來，到期日將從按一下&#x200B;**[!UICONTROL 「續訂」]**&#x200B;之日算起延長 1 年，無論原始到期日為何。
* 將警報匯出為 .CSV 檔案。
* 按兩下警報標題以編輯警報。
* 搜尋警報。
* 新增警報至其他報表套裝。
* 指定/變更警報的擁有者。
* 新增其他篩選器
* 定義警報&#x200B;**到期日**。

## 設定欄

您可以設定顯示的資料欄，以設定「警示管理員」中每個警示顯示的資訊。

若要在「警報管理員」中設定可見欄：

1. 在Adobe Analytics中，選取 **[!UICONTROL 元件]** 索引標籤，然後選取 **[!UICONTROL 警報]**.

1. 在警報管理器中，選取 **自訂欄** 圖示 ![自訂欄圖示](assets/customize-columns-icon.png)，然後選取您要在「警報管理員」中顯示的欄。

   可使用下列欄:

   | 欄標題 | 說明 |
   |---|---|
   | 我的最愛 | 在每一個警示旁邊顯示星號圖示，讓您將警示標示為我的最愛。 <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | 標題和說明 | 這些值會在警報產生器中提供。 若要編輯標題和說明，請選取標題連結以開啟警報產生器。 |
   | 報表套裝 | 指出上次將警報儲存到的目標報表套裝。 |
   | 所有者 | 指出警報的擁有者。 如果您不是管理員，就只能看見自己所擁有或已共用給您的警報。 |
   | 標記 | 顯示套用至警示的標籤，這些標籤是由您自己或與您共用警示的人員所設定。 |
   | 共用對象 | 列出您共用警報的個人或群組（僅限管理員）或全部（僅限管理員）。 |
   | 修改日期 | 表示上次修改警示的日期。 |
   | 上次使用 | **注意：** 此功能處於發行的有限測試階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱 [Adobe Analytics功能發行](/help/release-notes/releases.md).<p>顯示上次使用警示的日期。</p> <p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>此資訊不包括API、Report Builder或Data Warehouse的使用情況。</p> |

   {style="table-layout:auto"}
