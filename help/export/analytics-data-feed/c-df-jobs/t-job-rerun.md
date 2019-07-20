---
description: 您可以重新執行「工作」清單中的一或多項工作。
keywords: 資料饋送；工作；rerun
seo-description: 您可以重新執行「工作」清單中的一或多項工作。
seo-title: 重新執行工作
solution: Analytics
title: 重新執行工作
uuid: caf95da-dd888 b1 a-a-a081-684f4 fd1 f714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 重新執行工作

您可以重新執行「工作」清單中的一或多項工作。

1. 選取一或多個要重新執行的工作。
1. Click **[!UICONTROL Rerun Job]**.

   重新執行程序取決於目前的工作狀態:

   | 狀態 | 在伺服器快取檔案名稱 | 程序 |
   |---|---|---|
   | 完成 | 是 | 重新傳送檔案 |
   | 完成 | 否 | 重新處理工作，然後再重新傳送。 |
   | 已失敗 | 否 | 重新處理工作，然後再重新傳送。  |
   | 其他狀態 | 不適用 | 不支援。 |

