---
title: Report Builder 常見問題集
description: Report Builder的常見問題。
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Report Builder 常見問題集

關於Report Builder的常見問題。

## 我可以在活頁簿中使用`TODAY()`或`DATERANGE()`函式嗎？

Excel中的[`TODAY()`函式](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9)會傳回當天。 [`DATEVALUE()`函式](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252)將日期字串轉換為序列值。 雖然這對Excel中的許多功能很有幫助，但Adobe強烈建議不要將這些函式用於Report Builder排程請求。 Adobe客戶服務不支援使用上述任一功能來疑難排解請求。

排程報表會在可能不會將時區作為報表套裝的伺服器上處理。 使用者預期的`TODAY()`和處理伺服器使用的`TODAY()`通常可能不同。 此外，使用的日期是根據處理開始的時間。 如果同時執行許多報表，則請求日期與因延遲而開始處理日期之間可能會變更。 如果排程時間接近午夜，則會發生此問題。

排程報表也會在可能不會共用日期語法的伺服器上處理。 例如，根據您的國家/地區，`7/1/YYYY`可以指7月1日或1月7日。 在此日期使用`DATEVALUE()`函式會根據執行該函式的電腦產生不同的序列值。

除了使用這些Excel函式，Adobe強烈建議在Report Builder請求中使用日期範圍。 在請求精靈的第一頁，在下拉式清單中選取&#x200B;**[!UICONTROL 預設日期]**，然後在「常用日期」下方，選取&#x200B;**[!UICONTROL Today]**&#x200B;或其他需要的日期範圍。 此設定需要的是報表套裝執行時的時間，而非伺服器處理請求的時間。

## 我可以建立多大和複雜的活頁簿？

Report Builder支援的活頁簿最多達下列限制：

* **1000個請求**:活頁簿在單一活頁簿中最多可包含1000個資料請求。如果您的報表或專案需要超過1000個請求，Adobe建議將它們分隔成多個活頁簿。
* **每公司每小時2萬個請求**:Report Builder使用Analytics報表API來擷取資料。每個個別請求在建立或重新整理時都會使用API呼叫。 如果貴組織在指定小時內累積超過20,000個API呼叫，您必須等到下一小時再擷取資料。
* **4小時處理時間**:排程報表在處理過去4小時後逾時。如果您的活頁簿含有許多使用大型資料集的複雜請求，排程報表可能會失敗。
