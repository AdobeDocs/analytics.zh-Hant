---
description: 以下為 Report Builder 與 Power BI 搭配使用時的一些常見問題。
seo-description: 以下為 Report Builder 與 Power BI 搭配使用時的一些常見問題。
seo-title: Power BI整合疑難排解
title: Power BI整合疑難排解
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Power BI整合疑難排解

以下為 Report Builder 與 Power BI 搭配使用時的一些常見問題。

## 步驟 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

需要發佈至 Power BI 的排程活頁簿仰賴 Power BI 服務來執行作業。無法發佈的兩大主因為:

* Power BI 服務可能已停機。
* 將活頁簿排程的使用者已無有效的 Microsoft 帳戶憑證。

在每次排程執行時，每個 Report Builder 排程任務會嘗試執行三次。

* 第一次嘗試失敗後，您會看到這則訊息:「我們無法將此排程活頁簿發佈至 Microsoft Power BI。我們將稍後再試一次。」
* 第二次嘗試失敗後，您不會收到任何訊息。
* 第三次嘗試失敗後，您會看到這則訊息:「我們無法將此活頁簿發佈至 Power BI。」

## 步驟 2.Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

以下是將 Report Builder 請求發佈至 Power BI 後，視覺效果可能中斷的主要原因:

* 您在 Report Builder 中編輯請求，例如變更量度或維度，然後重新發佈至 Power BI。編輯請求可能會中斷視覺效果。
* 您刪除了視覺效果中使用的請求。

