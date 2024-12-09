---
description: 瞭解Analytics中資料摘要處理和傳送的最佳實務。
keywords: 資料摘要；最佳做法；流量尖峰；每小時；ftp
title: 最佳作法和一般資訊
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 84%

---

# 資料摘要最佳作法

以下是資料摘要處理和交付的幾個最佳做法。

* 務必提前傳達預期的流量尖峰。延遲會直接影響資料摘要的處理時間。請參閱管理員使用指南中的[排程流量尖峰](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)。

* 除非您與 Adobe 的合約中有明確提及，否則資料摘要並不包含服務層級的協議。摘要通常會在報表回溯期結束後的數小時內送達，但有時需要 12 小時或更長時間。

* 採用多檔案傳送的每小時摘要具有最快的處理速度。如果您的組織高度重視及時資料傳送，建議採用每小時多檔案摘要。

* 如果您將摘要擷取流程自動化，請考量點擊和檔案可能經多次傳輸的可能性。 您的摘要擷取流程需要在不會出錯或複製資料的情況下處理重複的點擊和重複的檔案。 我們建議使用 `hitid_high` 和 `hitid_low` 欄的組合，以唯一方式識別點擊。

  在罕見的情況下，您可能會看到重複的 `hitid_high` 和 `hitid_low` 值。 如果發生這種狀況，請確認之前並未傳送及處理該檔案。 如果檔案中只有一些列重複，請考慮新增 `visit_num` 和 `visit_page_num` 來協助判斷唯一性。

* 若使用FTP （不建議），請確保您的FTP站台有足夠的空間。 請定期移除目的地中的檔案，以免無意間用盡磁碟空間。

* 如果使用sFTP （不建議），請勿讀取或刪除尾碼為`.part`的檔案。 `.part` 尾碼表示已部分傳輸的檔案。一旦檔案傳輸完成，`.part` 尾碼就會消失。