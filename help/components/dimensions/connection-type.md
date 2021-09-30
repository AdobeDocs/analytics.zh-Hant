---
title: 連線類型
description: 訪客如何連線至網際網路。
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# 連線類型

「連線類型」維度會顯示訪客如何連線至網際網路。 此維度可用來判斷訪客如何連線至網際網路以瀏覽您的網站。 您可以使用它，根據訪客的連線速度來最佳化網站內容。

## 將資料填入此維度中

此維度使用[`ct`查詢字串](/help/implement/validate/query-parameters.md)和Adobe伺服器端邏輯的組合。 Adobe使用下列規則來判斷其值：

1. 如果`ct`查詢字串等於`"modem"`，請將維度項目設為`"Modem"`。 AppMeasurement只會在不支援的Internet Explorer瀏覽器上收集此資料，因此此維度項目不常見。
1. 檢查點擊的IP位址，並參考至Adobe內部的查閱表格。 如果IP位址來自行動電信業者，請將維度項目設為`"Mobile Carrier"`。
1. 如果`ct`查詢字串等於`"lan"`，請將維度項目設為`"LAN/Wifi"`。
1. 如果點擊源自於[資料來源](/help/import/c-data-sources/datasrc-home.md)或被視為特殊類型的點擊，請將維度項目設為`"Not specified"`。
1. 如果未滿足上述任何規則，則預設為`"LAN/Wifi"`值。

## 維度項目

Dimension項目包括`LAN/Wifi`、`Mobile Carrier`、`Modem`和`Not Specified`。

* **`LAN/Wifi`**:訪客透過固定線或wifi熱點連線至網際網路。
* **`Mobile Carrier`**:訪客透過行動電信業者連線至網際網路。
* **`Modem`**:訪客在不支援的Internet Explorer瀏覽器上透過資料機連線至網際網路。
* **`Not Specified`**:點擊沒有連線類型。
