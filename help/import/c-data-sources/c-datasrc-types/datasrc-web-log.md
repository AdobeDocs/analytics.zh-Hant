---
description: 網站記錄檔資料來源讓您匯入標準的網站伺服器記錄檔。
subtopic: Data sources
title: 網站記錄檔
topic: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 網站記錄檔

網站記錄檔資料來源讓您匯入標準的網站伺服器記錄檔。

支援下列常見的網站記錄檔類型:

| 欄名稱 | 說明 |
|--- |--- |
| NCSA 公用記錄檔 | Apache 預設 |
| NCSA 擴充 (結合) | Apache |
| W3C 擴充記錄檔 | IIS 4.0 及更高的版本所使用 |
| Microsoft IIS 記錄檔 | IIS 3.0 及早期的版本所使用 |

資料來源處理的主要記錄檔欄位有「IP 位址」、「請求的日期/時間」、「URL」。在少數情況下，例如 NCSA 延伸格式，資料來源也會處理「反向連結」和「使用者代理」欄位。

您可以使用標準的「頁面檢視」、「存取」及「訪客」行銷報表來檢視網站記錄檔資料。因為報表量度主要基於 cookie，而網站伺服器記錄檔基於 IP 地址，為了這個目的，Adobe 建議將網站伺服器記錄檔匯入獨立的報表套裝。

如需有關網站伺服器記錄檔的詳細資訊，請參閱您的網站伺服器文件。
