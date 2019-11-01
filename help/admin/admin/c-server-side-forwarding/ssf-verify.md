---
description: 若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。
seo-description: 若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。
seo-title: 如何確認您的伺服器端轉送實作情形
solution: Audience Manager
title: 如何確認您的伺服器端轉送實作情形
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

---


# 如何確認您的伺服器端轉送實作情形

若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。

檢查伺服器端轉送狀態:

1. 載入包含已更新 AppMeasurement 程式碼的測試頁。
1. 使用瀏覽器的除錯工具或代理軟體，檢查 Analytics 追蹤請求中的 HTTP 回應 (您可以透過選取包含「b/ss」的任何路徑輕易篩選)。
1. 檢查 HTTP 回應。若回應中包含 Audience Manager 資料 (如下所示)，則伺服器端轉送正在執行。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. 請確定Identity service已正確部署，您已部署App Measurement模組，適用的報表套裝已對應至正確的IMS組織，且Analytics管理控制台中已啟用伺服器端轉送。

>[!MORELIKETHIS]
>
>* [Charles 網頁除錯工具](https://www.charlesproxy.com/)

