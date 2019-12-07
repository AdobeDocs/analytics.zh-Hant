---
description: 客戶可使用標準型編碼 (例如 gzip) 來壓縮 JavaScript 程式庫檔案。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 檔案壓縮
topic: Developer and implementation
uuid: 609fec4b-2732-4ef5-9263-32192e4f0825
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 檔案壓縮

客戶可使用標準型編碼 (例如 gzip) 來壓縮 JavaScript 程式庫檔案。

一般的壓縮演算法可讓 JavaScript 檔案的大小減少 40-60%，甚至更多。

> [!NOTE]並非所有的瀏覽器都支援各種檔案壓縮標準，或是以相同的方式解譯壓縮檔案。Adobe 不保證在所有環境中都能有可靠的檔案壓縮。客戶在部署前，應先行在其支援的瀏覽器與設定中進行壓縮測試。

