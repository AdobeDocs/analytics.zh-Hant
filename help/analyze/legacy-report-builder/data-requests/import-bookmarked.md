---
description: 現在，所有書籤化報表與控制面板報表都已列為「請求精靈步驟1」中的維度，並且可匯入作為Report Builder請求。
title: 匯入書籤化報告與儀表板小報告
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 63%

---

# 匯入書籤化報告與儀表板小報告

{{legacy-arb}}

現在，所有書籤化報表與控制面板報表都已列為「請求精靈步驟1」中的維度，並且可匯入作為Report Builder請求。

當您選取書籤化報表時，「請求精靈」會填入定義此書籤化報表的所有維度和量度。 日期範圍、顆粒度及選取的區段也會根據選取的書籤加以更新。

以下說明「請求精靈步驟 1」如何顯示儀表板及其報表：

![熒幕擷圖顯示「請求精靈」步驟2之1 (反白顯示「擷取您的儀表板」及「擷取您的書籤」。](assets/import_dashboard_reportlet.png)

按一下「**[!UICONTROL 擷取您的儀表板]**」或「**[!UICONTROL 擷取您的書籤]**」時，就會擷取您現有的儀表板和/或書籤資料並貼入工作表中。

>[!NOTE]
>
>系統只會匯入資料，因此，如果書籤中包含圖表，或是儀表板小報表僅由圖表組成，系統只會匯入用來填寫圖表的資料。

一旦您匯入儀表板報表 (或書籤) 建立請求後，請求便會與報表 (或書籤) 的主要維度建立關聯。 因此，如果您編輯請求，樹狀檢視就不會再選取儀表板報表樹狀檢視節點 (或書籤節點)，而會選取請求的主要維度。

