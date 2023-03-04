---
title: 疑難排解 Data Warehouse 請求傳送時間
description: 判斷可能延長 Data Warehouse 請求傳送時間的潛在問題。
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 97%

---

# 疑難排解 Data Warehouse 請求傳送時間

傳送指定的 Data Warehouse 請求可能需要一小時以內至數天或更長時間。由於下列因素，很難估計處理請求所需的確切時間：

* 請求的日期範圍
* 請求時段內報表套裝收到的流量
* 區段內的規則數，以及區段內使用的變數
* 區段中包含的資料量
* 使用的劃分數，以及每個劃分內的不重複值數
* 使用的量度數
* 處理中的同時請求數
* VISTA 規則，如果已設定為套用至 DataWarehouse 請求

如果您發現每個 Data Warehouse 請求都需要很長的時間處理，請考慮變更您的請求以符合下列條件：

* **使用包含較小資料樣本的區段**：請求處理的資料越少，傳回報表的速度就越快。
* **以 14 天或更短時間為間隔執行請求**：處理較小請求的速度比處理較大的請求來得快。
* **使用較少劃分：** Data Warehouse 請求中的許多劃分會讓處理所需時間以指數方式增加。

>[!IMPORTANT]
>
> *Data Warehouse 請求的傳送速度無法加快。*

如果您需要更及時使用這些類型的報表，請考慮下列替代方案：

* **Analysis Workspace**：雖然不提供無限制的維度項目，但幾乎包含 Data Warehouse 提供的所有其他使用案例。
* **資料摘要**：每日擷取報表套裝中的所有原始資料，並傳送至 FTP 站台。如此一來，您可以將這些資料匯入您自己的資料庫，並執行查詢以取得您想尋找的資料。
* **自訂工程技術服務解決方案**：Adobe 工程技術服務可為貴組織提供自訂解決方案，但需支付額外費用。如需詳細資訊，請連絡您的Adobe帳戶團隊。
