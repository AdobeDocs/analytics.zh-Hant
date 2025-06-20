---
description: 列出在刪除區段之前，您應注意的一些事項。
title: 刪除區段
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: b96210a478c46f5d9cbf49c6288b698dc47d64fe
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 91%

---

# 刪除區段

列出在刪除區段之前，您應注意的一些事項。

當您刪除區段時，

* 已套用此區段的已計劃報表和控制面板會繼續正常運作，亦即區段或控制面板會繼續使用刪除的區段。
* 當您編輯同名區段時，已計劃的報告不會更新。以下是範例：假設您有 2 個同名區段分別位在不同報告套裝中：

  | 區段名稱 | 報告套裝 |
  |---|---|
  | 來自加州的造訪 | mainprod |
  | 來自加州的造訪 | maindev |


  您有個書籤是引用`mainprod`報表套裝的區段。 之後您因為該區段重複而刪除該區段。書籤將會繼續運作，引用已刪除之區段的定義。如果您將剩下那個區段的區段定義變更為納入聖卡塔利娜島和墨西哥提華納市，則書籤所套用的區段並不會變更。它會使用舊的定義。若要修正此問題，請將書籤更新為引用新的定義。如果您不確定書籤、儀表板或已計劃報告是否正在使用已刪除的區段，可以變更剩下那個區段的名稱，如此就更能清楚知道書籤是否正使用剩下那個區段。
