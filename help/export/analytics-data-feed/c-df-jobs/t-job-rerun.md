---
description: 您可以重新執行「工作」清單中的一或多項工作。
keywords: Data Feed;job;rerun
solution: Analytics
title: 重新執行工作
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

