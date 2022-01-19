---
description: 在 Analysis Workspace 中劃分維度和維度項目。
keywords: Analysis Workspace
title: 劃分維度
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Workspace Basics
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 9f0f17936de2597611728498c5ed82d36fd01d1c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 63%

---

# 劃分維度

在 Analysis Workspace 中劃分維度和維度項目。

您可針對特定需求，以無限方式劃分資料；使用相關量度、維度、區段、時間表及其他分析劃分值來建立查詢。

1. [建立專案](/help/analyze/analysis-workspace/home.md)並搭配資料表格。
1. 在資料表格中，以滑鼠右鍵按一下某個條列項目，並選取&#x200B;**[!UICONTROL 劃分]** > *`<item>`*。

   ![步驟結果](assets/fa_data_table_actions.png)

   您可以跨所選時段，依維度項目或受眾區段來劃分量度。您也可以更深入鑽研至更詳細的層級。

   >[!NOTE]
   >
   >表格中顯示的劃分數目上限為 200。匯出劃分時，此限制會提高。

## 將歸因模型套用到資料劃分

表格中的任何劃分也可套用任何歸因模型。此歸因模型可與父欄相同或不同。舉例來說，您可以在「行銷管道」維度中分析線性訂單，但將「U 形訂單」套用至管道中的特定追蹤代碼。若要編輯套用到劃分的歸因模型，請將滑鼠移到劃分模型上方，然後按一下&#x200B;**[!UICONTROL 編輯]**：

![劃分設定](assets/breakdown_settings.png)

這是將屬性模型應用於故障或編輯故障時的預期行為：

* 如果在不存在其他屬性時應用屬性，則屬性將應用於整個列樹。

* 如果在應用了屬性後添加細分，則如果該維具有預設值，則它將對添加的給定細分使用預設值。 否則，它將使用父列的細分。 某些維具有預設分配。  比如說， [!UICONTROL 時間] 維和 [!UICONTROL 引用者] 使用 [!UICONTROL 同一觸摸]。 的 [!UICONTROL 產品] 維使用 [!UICONTROL 上次觸摸]。 其他維沒有預設維，將使用父列分配。

* 如果列樹中已存在屬性，則更改屬性只會影響您正在編輯的屬性。

## 影片

在 Analysis Workspace 中新增維度和量度至您的專案：

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

在自由格式表格中使用維度：

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

以下是有關依位置的維度劃分的影片：

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
