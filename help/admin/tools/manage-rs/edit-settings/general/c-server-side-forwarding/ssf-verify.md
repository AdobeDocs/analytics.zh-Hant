---
description: 若要確認伺服器端轉送已正確啟用，您必須檢查來自Analytics追蹤請求的HTTP回應。 這些指示說明必須顯示哪些指標以確保正確啟用伺服器端轉送。
solution: Analytics
title: 如何確認您的伺服器端轉送實作情形
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 36%

---

# 如何確認您的伺服器端轉送實作情形

若要確認伺服器端轉送已正確啟用，您必須檢查來自Analytics追蹤請求的HTTP回應。 您可以使用瀏覽器的開發人員工具或代理工具（例如Charles網頁除錯工具）來達成此目的。 下列指示說明必須顯示哪些指示器，才能確保正確啟用伺服器端轉送。

檢查伺服器端轉送狀態：

1. 載入包含更新AppMeasurement程式碼的測試頁面。
1. 在瀏覽器的除錯工具或使用Proxy軟體時，請檢查Analytics追蹤請求的HTTP回應（只要選取包含「b/ss」的任何路徑，即可輕鬆篩選此專案）。
1. 檢查HTTP回應。 如果回應包含Audience Manager資料（如下圖所示），表示伺服器端轉送運作正常。

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>如果回應包含索引鍵值配對 `"status":"SUCCESS"` 或 2 x 2 影像，表示伺服器端轉送設定不正確。 請確認身分識別服務已正確部署，且您已部署 App Measurement 模組，將適用的報表套裝對應到正確的組織 ID，並在 Analytics 管理員工具中啟用了伺服器端轉送。

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
