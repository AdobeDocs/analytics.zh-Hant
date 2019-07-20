---
description: 您可以從接觸點建立區段、新增區段做為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。
keywords: 流失和分段；流失分析中的區段；比較流失中的區段
seo-description: 您可以從接觸點建立區段、新增區段做為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。
seo-title: 在流失分析中套用區段
title: 在流失分析中套用區段
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 769d076549484c6939157ef217225493ddbe130e

---


# 在流失分析中套用區段

您可以從接觸點建立區段、新增區段做為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。

>[!IMPORTANT]
>作為流失中查核點的區段必須使用低於「流失」視覺化整體上下文的容器。有了訪客內容流失，作為查核點的區段必須是瀏覽或點擊型區段。透過瀏覽內容流失，作為查核點的區段必須是點擊型區段。如果您使用無效組合，流失將是100%。我們已對流失視覺效果新增警告，當您新增不相容區段做為接觸點時會顯示此警告。某些無效的區段容器組合會導致無效的流失圖表，例如

>* 使用以訪客為基礎的區段，作為訪客內容流失視覺效果內的接觸點
>* 使用以訪客為基礎的區段，作為造訪內容流失視覺效果內的接觸點
>* 使用以造訪為基礎的區段，作為造訪內容流失視覺效果內的接觸點


## Create a segment from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 首先，從您特別感興趣的某個接觸點建立區段，然後就可以將此區段用於其他報表。You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   「區段產生器」會隨即開啟，預先填入符合您所選接觸點的預先建立連續區段:

   ![](assets/segment-builder.png)

1. 提供區段的標題和描述，然後將其儲存。

   您現在可以在任意報表中使用這個區段了。

## Add a segment as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

如果您想查看美國使用者 (舉例來說) 的趨勢以及如何影響流失，只需將美國使用者區段拖曳至流失中:

![](assets/segment-touchpoint.png)

或者，您也可以將美國使用者區段拖曳至其他檢查點尚，用以建立 AND 接觸點。

## Compare segments in fallout {#section_E0B761A69B1545908B52E05379277B56}

您可以在「流失」視覺效果中比較無數區段。

1. 從左側的[!UICONTROL 「區段」]欄選取您想要比較的區段。在我們的範例中，已選取 2 個區段: 美國使用者和非美國使用者。
1. 將這些區段拖曳至頂端的「區段」拖放區域。

   ![](assets/segment-drop.png)

1. 可選: 您可將「所有造訪」保留做為預設容器，也可將其刪除。

   ![](assets/seg-compare.png)

1. 您現在可以比較這兩個區段的流失，例如某個區段在哪裡表現較另一個區段優秀，或是使用其他分析角度。

