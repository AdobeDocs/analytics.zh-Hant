---
description: 您可以從接觸點建立區段、新增區段作為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: 在流失分析中套用區段
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 在流失分析中套用區段

您可以從接觸點建立區段、新增區段作為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。

>[!IMPORTANT]在流失分析中當作查核點使用的區段，其所用容器的層級必須低於流失視覺效果的整體設定。分析訪客相關流失率時，當作查核點使用的區段必須為「造訪」或「點擊」相關區段。分析造訪相關流失率時，當作查核點使用的區段必須為「點擊」相關區段。如果使用無效的組合，流失率會計為 100%。我們在「流失視覺效果」中新增一項警告功能，會在您將不相容區段新增為接觸點時顯示。特定的無效區段容器組合會產生無效的流失率圖表，例如：

* 使用以訪客為基礎的區段，作為訪客內容流失視覺效果內的接觸點
* 使用以訪客為基礎的區段，作為造訪內容流失視覺效果內的接觸點
* 使用以造訪為基礎的區段，作為造訪內容流失視覺效果內的接觸點

## 從接觸點建立區段 {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 從您特別感興趣的某個接觸點建立區段，之後您可以將此區段套用於其他報表。若要這麼做，請以滑鼠右鍵按一下接觸點並選取 **[!UICONTROL Create segment from touchpoint]**。

   ![](assets/segment-from-touchpoint.png)

   「區段產生器」會隨即開啟，預先填入符合您所選接觸點的預先建立連續區段：

   ![](assets/segment-builder.png)

1. 為區段提供標題和說明並儲存。

   您現在可以在任何您想要的報表中使用此區段。

## 將區段新增為接觸點 {#section_17611C1A07444BE891DC21EE8FC03EFC}

如果您想查看美國使用者 (舉例來說) 的趨勢以及如何影響流失，只需將美國使用者區段拖曳至流失中：

![](assets/segment-touchpoint.png)

或者，您也可以將美國使用者區段拖曳至另一個查核點，以建立AND觸點。

## 比較流失率中的區段 {#section_E0B761A69B1545908B52E05379277B56}

您可以比較「流失」視覺化中不限數量的區段。

1. 從左側的邊欄選取您要比 [!UICONTROL Segments] 較的區段。 在我們的範例中，已選取 2 個區段：美國使用者和非美國使用者。
1. 將它們拖曳至頂端的「區段」拖放區。

   ![](assets/segment-drop.png)

1. 選用：您可將「所有造訪」保留作為預設容器，也可將其刪除。

   ![](assets/seg-compare.png)

1. 您現在可以比較兩個區段的流失，例如某個區段的績效高於另一個區段的位置，或是其他見解。
