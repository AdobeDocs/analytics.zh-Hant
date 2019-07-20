---
description: Analytics 部署可統整為三個主要步驟。
keywords: Analytics 實施
seo-description: Analytics 部署可統整為三個主要步驟。
seo-title: 最佳化總覽
solution: Analytics
subtopic: 疑難排解
title: 最佳化總覽
topic: 開發人員和實施
uuid: 8e8ic5b-d4 b1-4d13-8525-39e4924 df247
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 最佳化總覽

Analytics 部署可統整為三個主要步驟。

1. 步驟之一是將 HTML 程式碼片段貼到網站的每個頁面 (或頁面範本) 上。HTML 程式碼片段非常小 (400 到 1,000 位元組)，且包含 JavaScript 變數和其他可加速進行資料收集程序的識別碼。
1. 程式碼片段會呼叫 JavaScript 程式庫檔案；此檔案中包含 Analytics 專用、在度量收集期間使用的 JavaScript 函數。若 Analytics 程式碼正確實施，瀏覽器執行 JavaScript 程式庫檔案時通常很快即可完成。

1. 此程式庫檔案會向 Adobe 資料收集伺服器提出影像要求。伺服器在收集所要提交的資料後，會將 1x1 透明影像傳回至訪客的瀏覽器。第三個步驟會略為增加頁面下載的總時間。

>[!NOTE]
>
>客戶可以採取其他步驟，將Analytics負荷降至最低。

