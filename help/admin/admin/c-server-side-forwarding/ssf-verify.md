---
description: 若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。
seo-description: 若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。
seo-title: 如何驗證您的伺服器端轉送實作
solution: Audience Manager
title: 如何驗證您的伺服器端轉送實作
uuid: e37296cc-0120-486a-a4 ca-78d648 cf6 a11
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 如何驗證您的伺服器端轉送實作

若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。

檢查伺服器端轉送狀態:

1. 載入包含已更新 AppMeasurement 程式碼的測試頁。
1. 使用瀏覽器的除錯工具或代理軟體，檢查 Analytics 追蹤請求中的 HTTP 回應 (您可以透過選取包含「b/ss」的任何路徑輕易篩選)。
1. 檢查 HTTP 回應。若回應中包含 Audience Manager 資料 (如下所示)，則伺服器端轉送正在執行。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. 請確定已正確部署Identity Service，您已部署App Measurement模組，且適用的報表套裝已對應至正確的IMS Org，且已在Analytics管理控制台中啓用伺服器端轉送。

>[!MORE_LIKE_THIS]
>
>* [Charles 網頁除錯工具](https://www.charlesproxy.com/)

