---
description: Data Warehouse 指的是儲存和自訂報告所使用的 Analytics 資料複本，您可以透過篩選資料來執行這些資料。 您可以要求報告依據您的特定問題，從原始資料顯示進階資料關係。Data Warehouse 報告會透過電子郵件發送或發送給雲端儲存空間提供者，並且可能需要長達 72 小時的處理時間。處理時間依查詢的複雜度以及請求的資料量而定。
title: Data Warehouse 概觀
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 100%

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

Adobe 僅針對管理員層級使用者，在特定報告套裝上啟用 Data Warehouse(DataWarehouse 可在全域及子報告套裝上啟用，但不可用於統計報告套裝)。管理員可建立存取 Data Warehouse 的群組，然後將非管理員級別的使用者與該群組關聯。

請參閱「[管理 Data Warehouse 權限](/help/export/data-warehouse/t-dw-group.md)」。

## 建立 Data Warehouse 請求

有關如何建立 Data Warehouse 請求的資訊，請參閱「[建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)」。

## 管理 Data Warehouse 請求

有關如何管理 Data Warehouse 請求的資訊，請參閱「[管理 Data Warehouse 請求](/help/export/data-warehouse/data-warehouse-requests-manage.md)」。

## 常見問題

有關常見問題清單，請參閱「[Data Warehouse 常見問題](/help/export/data-warehouse/faq.md)」。