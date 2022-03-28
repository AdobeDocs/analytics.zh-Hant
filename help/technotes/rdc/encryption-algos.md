---
title: 支援的HTTPS加密算法
description: 2022年6月23日，我們將取消對TLS 1.2密碼的支援，這些密碼對密碼安全級別設定為「高」的客戶使用SHA1或CBC。
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 支援的HTTPS加密算法

Adobe提供兩個密碼安全級別，以滿足客戶對第一方資料收集的不同安全需求。 這些級別決定了支援哪些加密算法用於與我們的伺服器進行HTTPS連接。 客戶預設為「標準」，它只支援現代加密算法。 「High」支援為更關心這些連接的客戶提供一個較小的加密算法清單。 對於兩個安全級別，Adobe會根據當前的安全實踐定期更新一組受支援的算法。 如果要更改密碼安全設定，請與「客戶服務」聯繫。

2022年6月23日，我們將取消對TLS 1.2密碼的支援，這些密碼對密碼安全級別設定為「高」的客戶使用SHA1或CBC。  此更改將影響較舊作業系統上最終用戶的安全資料收集。

不再支援以下TLS 1.2密碼：

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

已知以下客戶端受此更改影響，因為他們不支援當前加密標準：

* Windows 8.1及更早版本（上次更新於2018年）
* Windows Phone 8.1及更早版本（上次更新於2016年）
* OS X 10.10及更早版本（上次更新時間為2017年）
* iOS8.4及更早（上次更新於2015年）

Android設備不受此更改的影響。

密碼安全級別設定為「標準」的客戶不受此更改的影響。

