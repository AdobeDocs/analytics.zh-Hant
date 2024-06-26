---
title: 分類匯入工具處理時間
description: 了解 Adobe 處理分類檔案的時間範圍，以及如何將處理時間縮到最短。
feature: Classifications
exl-id: 6b8b87f1-5dbc-46b8-9912-0e3086ff4b2a
source-git-commit: a83195c7805ff1bfb854b3c2714857f437cf8955
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 100%

---

# 分類匯入工具處理時間

分類檔案的處理時間視檔案大小和 Adobe 處理的檔案總數而定。處理分類通常不會超過 24 小時。不過，使用 Adobe Analytics 的組織使用大量分類的時段，可能會造成處理檔案的時間超過 24 小時。Adobe 發現，佳節假期之前的幾個月內會大量使用分類。

如果您想要查看分類檔案是否已完成，請執行下列動作：

1. 登入 Adobe Analytics，然後導覽至&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 分類匯入工具」]**。
2. 選取相關的報表套裝和資料集。
3. 如果處理尚未完成，會出現下列其中一則訊息：

   * ![通知](assets/icon_notice_notice.gif) 所選報表含有正在處理的分類匯入。
   * ![通知](assets/icon_notice_notice.gif) 所選報表含有尚未傳播至所有伺服器的分類資料。

若想將分類匯入時間縮到最短，Adobe 強烈建議您遵循下列准則：

* **盡可能使用分類規則產生器**：分類規則產生器處理資料的方式與傳統分類匯入工具不同。如果分類資料遵循特定模式，強烈建議使用此功能。
* **僅上傳已變更的列**：分類檔案不會依未變更的列排序，所以此方法可大幅縮短處理分類檔案所花的時間。Adobe 強烈建議只上傳已變更的列。
* **預先規劃**：請盡早開始上傳分類資料，尤其是會在佳節假期期間使用這些資料時。
* **盡可能合併分類檔案**：如果單一變數有多個分類，請上傳含有全部適用分類的單一檔案。避免為相同變數上傳多個分類。
* **避免上傳超過 500 MB 的檔案**：如果處理大量分類資料，Adobe 建議將檔案分割為 100 MB 到 500 MB 的檔案。
* **避免將大量檔案上傳至 FTP**：如果您打算透過 FTP 將相同的檔案上傳至許多報表套裝，請限制一次上傳的檔案數。Adobe 建議檔案數乘以適用報表套裝數目小於 1000。如果需要將 100 個檔案上傳至 100 個報表套裝，則檔案總數為 10,000。與其一次上傳全部 100 個檔案，不如一次分成 10 組 10 個檔案。
* **透過瀏覽器匯入工具上傳小型檔案**：如果檔案小於 1 MB (少於 50,000 列)，Adobe 建議使用瀏覽器匯入工具。瀏覽器匯入幾乎永遠比 FTP 匯入快。
