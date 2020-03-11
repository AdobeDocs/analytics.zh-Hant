---
description: '以下是資料摘要處理和提交的幾點最佳應用。建議您 '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: 最佳作法和一般資訊
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最佳實務

以下是資料摘要處理和提交的幾點最佳應用。

* 務必提前傳達預期的流量尖峰。延遲會直接影響資料摘要的處理時間。請參閱管理員使用指南中的[排程流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)。
* 除非您與 Adobe 的合約中有明確提及，否則資料摘要並不包含服務層級的協議。摘要通常會在報表回溯期結束後的數小時內送達，但有時需要 12 小時或更長時間。
* FTP 站台務必具備足夠空間。請定期移除目的地中的檔案，以免無意間用盡磁碟空間。
* 採用多檔案傳送的每小時摘要具有最快的處理速度。如果您的組織高度重視及時資料傳送，建議採用每小時多檔案摘要。
* 如果使用 sFTP，請勿讀取或刪除含有 `.part` 尾碼的檔案。`.part` 尾碼表示已部分傳輸的檔案。一旦檔案傳輸完成，`.part` 尾碼就會消失。
* 如果您採用自動化摘要接收程序，請注意同一檔案可能經多次傳輸。使用者可能會重新傳送重複檔案，而 Adobe 極少數情況下也會如此。
