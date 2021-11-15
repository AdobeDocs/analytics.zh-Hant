---
title: Report Builder 常見問題集
description: Report Builder 常見問題。
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 51cac193cd2c88898139e079816a084c211a64f4
workflow-type: ht
source-wordcount: '420'
ht-degree: 100%

---

# Report Builder 常見問題集

Report Builder 相關的常見問題。

## 我是否可以在活頁簿中使用 `TODAY()` 或 `DATERANGE()` 函數。

Excel 中的 [`TODAY()` 函數](https://support.microsoft.com/zh-tw/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) 會傳回現在的日子。[`DATEVALUE()` 函數](https://support.microsoft.com/zh-tw/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) 將日期字串轉換為序列值。雖然這對 Excel 許多功能很有幫助，但 Adobe 強烈建議不要將這些函數用於 Report Builder 排程請求。 Adobe 客戶服務不支援使用上述任何一項功能的疑難排解請求。

排程報告會在可能不會以報表套裝分享時區的伺服器上處理。 使用者預期的 `TODAY()` 與處理伺服器使用的 `TODAY()` 通常可能不同。 此外，使用的日期是根據處理開始的時間。如果同時執行許多報表，則請求日期與因延遲而開始處理日期之間可能會變更。 如果排程時間接近午夜，則會發生此問題。

排程報告也會在可能不會共用日期語法的伺服器上處理。 例如，根據您所在的國家/區域，`7/1/YYYY` 可能指 7 月 1 日或 1 月 7 日。 在此日期使用 `DATEVALUE()` 函數會根據執行該函數的電腦產生不同的序列值。

除了使用這些 Excel 函數外，Adobe 還強烈建議在 Report Builder 請求中使用日期範圍。在請求精靈的第一頁，在下拉式清單中選取&#x200B;**[!UICONTROL &#x200B;預設日期]**，然後在「常用日期」下方，選取 **[!UICONTROL &#x200B;Today]** &#x200B;或其他需要的日期範圍。 此設定會花時間在執行報表套裝，而不是花時間在伺服器處理請求上。

## 我可以建立多大和多複雜的活頁簿？

Report Builder 支援的活頁簿的上限如下：

* **1000 項要求**: 單一活頁簿可包含最多 1000 項資料要求。如果您的報表或專案需要超過 1000 個請求，Adobe 建議將其分隔成多個活頁簿。
* **每家公司每小時 2 萬個請求**： Report Builder 會使用 Analytics 報表 API 來擷取資料。每個個別請求在建立或重新整理時都會使用 API 呼叫。 如果您的組織在指定小時內累積超過 20,000 個 API 呼叫，您必須等到下一小時再擷取資料。
* **4 小時處理時間**: 排程報告在處理經過 4 小時後逾時。如果您的活頁簿包含許多使用大型資料集的複雜請求，排程報告可能會失敗。
