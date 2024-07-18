---
title: 連線類型
description: 訪客如何連線至網際網路。
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 94%

---

# 連線類型

「連線型別」[維度](overview.md)顯示訪客如何連線至網際網路。 此維度對於判斷訪客如何連線至網際網路來瀏覽您的網站很有幫助。您可利用它來根據訪客的連線速度將網站內容最佳化。

## 將資料填入此維度中

此維度會利用[`ct`查詢字串](/help/implement/validate/query-parameters.md)和 Adobe 伺服器端邏輯的組合。Adobe 為判斷其值會使用以下規則:

1. 如果`ct`查詢字串等於 `"modem"`，將維度項目設為 `"Modem"`。AppMeasurement 只會在不受支援的 Internet Explorer 瀏覽器上收集這項資料，使得此維度項目並不常見。
1. 檢查點擊的 IP 位址，並將其參照至 Adobe 內部的查詢表。如果該 IP 位址來自行動電信業者，則將此維度項目設定為 `"Mobile Carrier"`。
1. 如果`ct`查詢字串等於 `"lan"`，將維度項目設為 `"LAN/Wifi"`。
1. 如果點擊來自[資料來源](/help/import/data-sources/overview.md)，或被視為某種特殊類型的點擊，則將維度項目設定為 `"Not specified"`。
1. 如果不符合上述任何規則，則預設為 `"LAN/Wifi"` 的值。

## 維度項目

維度項目包括 `LAN/Wifi`、`Mobile Carrier`、`Modem` 和 `Not Specified`。

* **`LAN/Wifi`**: 訪客透過有線電話或 Wi-Fi 熱點連線至網際網路。
* **`Mobile Carrier`**: 訪客透過行動電信業者連線至網際網路。
* **`Modem`**: 訪客透過數據機在未受支援的 Internet Explorer 瀏覽器上連線至網際網路。
* **`Not Specified`**: 該點擊並沒有連線類型。
