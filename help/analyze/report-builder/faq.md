---
title: Report Builder 常見問題集
description: 關於Report Builder的常見問題。
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---


# Report Builder 常見問題集

關於Report Builder的常見問題。

## 我可以在活頁簿中使用`TODAY()`或`DATERANGE()`函式嗎？

Excel中的[`TODAY()`函式](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9)會傳回當天。 [`DATEVALUE()`函式](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252)將日期字串轉換為序列值。 雖然Excel中的許多功能很實用，但Adobe強烈建議您不要將這些函式當成Report Builder排程請求的一部分。 Adobe客戶服務不支援使用上述任一功能進行疑難排解的要求。

排程報表會在伺服器上處理，這些伺服器可能不會將時區共用為報表套裝。 使用者預期的`TODAY()`和處理伺服器使用的`TODAY()`通常可能不同。 此外，使用的日期是根據處理開始的時間而定。 如果同時執行多份報表，則日期會在請求時間和由於延遲而開始處理之間變更。 如果排程時間接近午夜，就會出現此問題。

排程報表也會在可能不共用日期語法的伺服器上處理。 例如，`7/1/YYYY`可參照7月1日或1月7日，視您的國家／地區而定。 在此日期使用`DATEVALUE()`函式會根據執行該函式的電腦產生不同的串列值。

除了使用這些Excel函式外，Adobe強烈建議在Report Builder請求中使用日期範圍。 在請求精靈的第一頁，在下拉式清單中選擇&#x200B;**[!UICONTROL 預設日期]**，然後在「常用日期」下，選擇&#x200B;**[!UICONTROL 今天]**&#x200B;或其他所需的日期範圍。 此設定會佔用報表套裝執行時的時間，而非伺服器處理請求的時間。

## 我可以製作多大和複雜的活頁簿？

Report Builder支援的活頁簿最多以下限制：

* **1000個請求**:活頁簿在單一活頁簿中最多可包含1000個資料請求。如果您有需要超過1000個請求的報表或專案，Adobe建議將它們分隔成多個活頁簿。
* **每家公司每小時20K個要求**:Report Builder使用Analytics報表API來擷取資料。每個個別請求在建立或重新整理時都會使用API呼叫。 如果貴組織在指定小時內累計超過20,000個API呼叫，您必須等到下一小時再擷取資料。
* **4小時處理時間**:排程報表在處理過去4小時後逾時。如果您的活頁簿包含許多使用大型資料集的複雜請求，則排程報表可能會失敗。
