---
title: 最佳做法
description: 瞭解一些細分最佳實務。
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 60%

---

# 細分最佳實務

通常需要複雜的區段才能取得所需的資料。如果複雜的區段效率不彰，且用於大型報表套裝中，那麼報表的執行時間會長得多。建立或編輯區段時，請考慮下列資源，將複雜性降至最低。

## 僅使用`Contains`運運算元作為最後手段

[**[!UICONTROL Contains &#x200B;]**&#x200B;運運算元](/help/components/segmentation/seg-reference/seg-operators.md)是分段中需要最多處理的功能之一，因為運運算元必須分析每個值的全部內容。 如果所需值位於字串的開頭或結尾，請考慮使用其他運運算元，例如&#x200B;**[!UICONTROL &#x200B;開頭為&#x200B;]**&#x200B;或&#x200B;**[!UICONTROL &#x200B;結尾為&#x200B;]**。

如果區段中的&#x200B;**[!UICONTROL Contains]**&#x200B;運運算元傳回大量結果，報表通常會逾時。 例如，如果您建立了區段，其中&#x200B;**[!UICONTROL 反向連結]** **[!UICONTROL 等於]** `"."`，則區段會搜尋每個值的內容。 請考慮改用&#x200B;**[!UICONTROL 存在]**&#x200B;運運算元。

## 使用分類將維度項目分組

如果您有許多區段條件，可能會快速降低區段效能。例如，**[!UICONTROL 頁面]** **[!UICONTROL 等於]** `X` **[!UICONTROL OR]** **[!UICONTROL 頁面]** **[!UICONTROL 等於]** `Y` **[!UICONTROL OR]** **[!UICONTROL 頁面]** **[!UICONTROL 等於]** `Z`重複數百個不同的值。 與其寫出這些數以百計的條件，請將所有所需值分類至區段中，然後在區段中使用分類值。

1. 為您使用的變數建立分類。
2. 下載分類範本，然後在您需要的試算表或文字編輯器中開啟它。
3. 為您要納入區段中的每個維度項目指定相同的值。
4. 使用分類匯入工具將試算表匯入 Adobe Analytics 中
5. 分類完成處理後，請使用分類值建立區段。

此方法可大幅提升效能，並提供修改區段條件的簡單方式。您可以新增或移除分類中的維度項目，而不需使用不同的值來編輯區段。
