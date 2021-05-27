---
description: 以下是資料摘要處理和提交的幾點最佳應用。
keywords: 資料摘要；最佳實務；流量尖峰；每小時；ftp
title: 最佳作法和一般資訊
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 8f6c6aabf1e41cfd4b143a5d4cf14e73cdcbb603
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 66%

---

# 最佳實務

以下是資料摘要處理和提交的幾點最佳應用。

* 務必提前傳達預期的流量尖峰。延遲會直接影響資料摘要的處理時間。請參閱管理員使用指南中的[排程流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)。

* 除非您與 Adobe 的合約中有明確提及，否則資料摘要並不包含服務層級的協議。摘要通常會在報表回溯期結束後的數小時內送達，但有時需要 12 小時或更長時間。

* FTP 站台務必具備足夠空間。請定期移除目的地中的檔案，以免無意間用盡磁碟空間。

* 採用多檔案傳送的每小時摘要具有最快的處理速度。如果您的組織高度重視及時資料傳送，建議採用每小時多檔案摘要。

* 如果使用 sFTP，請勿讀取或刪除含有 `.part` 尾碼的檔案。`.part` 尾碼表示已部分傳輸的檔案。一旦檔案傳輸完成，`.part` 尾碼就會消失。

* 如果您讓摘要擷取程式自動化，請考慮點擊和檔案可能多次傳輸的可能性。 您的摘要擷取程式需要處理重複點擊和重複檔案，而不需要錯誤擷取或重複資料。 建議使用`hitid_high`和`hitid_low`欄的組合來唯一識別點擊。

   在少數情況下，您可能會看到重複的`hitid_high`和`hitid_low`值。 如果發生此情況，請確認先前未傳送及處理檔案。 如果檔案中只有某些列重複，請考慮新增`visit_num`和visit_page_num`以協助判斷獨特性。
