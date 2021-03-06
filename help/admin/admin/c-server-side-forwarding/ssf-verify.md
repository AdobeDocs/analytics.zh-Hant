---
description: 若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。
solution: Analytics
title: 如何確認您的伺服器端轉送實作情形
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 84%

---

# 如何確認您的伺服器端轉送實作情形

若要確認伺服器端轉送是否正確啟用，您必須檢查 Analytics 追蹤請求的 HTTP 回應。您可以使用瀏覽器的開發人員工具，或者使用代理工具來完成此步驟，例如 Charles 網頁除錯工具。下列指示說明哪些指標必須出現，才可確保伺服器端轉送已正確啟用。

檢查伺服器端轉送狀態：

1. 載入包含已更新 AppMeasurement 程式碼的測試頁。
1. 使用瀏覽器的除錯工具或代理軟體，檢查 Analytics 追蹤請求中的 HTTP 回應 (您可以透過選取包含「b/ss」的任何路徑輕易篩選)。
1. 檢查 HTTP 回應。若回應中包含 Audience Manager 資料 (如下所示)，則伺服器端轉送正在執行。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>如果回應包含索引鍵值配對 `"status":"SUCCESS"` 或 2 x 2 影像，表示伺服器端轉送設定不正確。請確保正確部署了Identity Service，您已部署了App Measurement模組，已將適用的報告套件映射到正確的組織ID，並且已在Analytics管理控制台中啟用了伺服器端轉發。

>[!MORELIKETHIS]
>
>* [Charles 網頁除錯工具](https://www.charlesproxy.com/)

