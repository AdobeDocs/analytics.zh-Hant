---
description: '以下是資料摘要處理和提交的幾點最佳應用。建議您 '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
solution: Analytics
title: 最佳作法和一般資訊
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# 最佳實務

以下是資料摘要處理和提交的幾點最佳應用。

* 務必提前傳達預期的流量尖峰。延遲會直接影響資料饋送的處理時間。 請參 [閱「管理員使用指南](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) 」中的「排程流量尖峰」。
* 除非您與Adobe的合約中明確注明，否則資料饋送不包含服務層級合約。 動態消息通常在報告視窗通過後數小時內傳送，但有時需要12小時或更長時間。
* FTP 站台務必具備足夠空間。定期從目標位置移除檔案，以免不慎耗用磁碟空間。
* 使用多個檔案傳送程式，以最快的速度傳送每小時動態消息。 如果組織優先順序較高，請考慮使用每小時多個檔案饋送。
* 如果使用sFTP，請勿讀取或刪除含有尾碼的 `.part` 檔案。 尾碼 `.part` 表示檔案已部分傳輸。 一旦傳輸檔案，尾碼 `.part` 就消失。
* 如果您將動態消息擷取程式自動化，請考慮檔案可能可以多次傳輸。 使用者可重新傳送重複檔案，Adobe很少會重新傳送重複檔案。
