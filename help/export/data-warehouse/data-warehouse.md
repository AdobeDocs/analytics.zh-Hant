---
description: 瞭解Data Warehouse以及如何篩選資料，讓您建立和執行自訂報表。
title: Data Warehouse概觀
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 79%

---

# Data Warehouse 概觀

Data Warehouse 允許您為儲存空間和建立自訂報告而複製 Adobe Analytics 資料，您可以透過篩選資料來執行這些資料。 

## 報告概觀

Data Warehouse 報告可依據您的特定問題，顯示來自原始資料的進階資料關係。這些報告可在單一請求中包含不限數量的資料列 (針對個別、已排程和下載的報告)。

>[!NOTE]
>
>Data Warehouse 會報告在報告時段遇到的第一個值。

>[!IMPORTANT]
>
>依據分類的值進行分段時，Analysis Workspace 和 Data Warehouse 會將「未指定」的值視為不同的值處理。工作區中的「未指定」是指未分類的值，而 Data Warehouse 中的「未指定」是指您分類為「未指定」的值。

## 傳遞概觀

Data Warehouse 報告會透過電子郵件發送或發送給雲端儲存空間提供者，並且會需要長達 72 小時的處理時間。處理時間依查詢的複雜度以及請求的資料量而定。

Data Warehouse 會自動壓縮大小超過 1 MB 的檔案。電子郵件附件大小上限是 10 MB。

## 存取權

Adobe 僅針對管理員層級使用者，在特定報告套裝上啟用 Data Warehouse（全域和子報表套裝可啟用此功能，統計報表套裝則無法啟用。） 管理員可以建立具有Data Warehouse存取權的群組，然後將非管理員層級的使用者與該群組相關聯。

請參閱「[管理 Data Warehouse 權限](/help/export/data-warehouse/t-dw-group.md)」。

## 建立 Data Warehouse 請求

有關如何建立 Data Warehouse 請求的資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

## 管理 Data Warehouse 請求

有關如何管理 Data Warehouse 請求的資訊，請參閱「[管理 Data Warehouse 請求](/help/export/data-warehouse/data-warehouse-requests-manage.md)」。

