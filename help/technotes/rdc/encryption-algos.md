---
title: 支援的 HTTPS 加密算法
description: 2022 年 6 月 23 日起，我們將針對加密安全等級設定為「高」的客戶，除移對其運用 SHA1 或 CBC 的 TLS 1.2 加密支援服務。
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: a1ae98d6907960135c1dfa03ed10738eac8bec0d
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# 支援的 HTTPS 加密算法

Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。這些等級會決定與我們伺服器 HTTPS 連線時支援的加密算法。客戶預設為「標準」，只會支援現代化加密算法。「高」等級會為更關注這類連線的客戶支援較小型的加密算法列表。對於這兩個安全等級，Adobe 會根據當前的安全實務來定期更新支援的算法集。如果您想變更加密的安全設定，請聯絡客戶服務。

2022 年 6 月 23 日起，我們將針對加密安全等級設定為「高」的客戶，除移對其運用 SHA1 或 CBC 的 TLS 1.2 加密支援服務。此變更將影響使用較舊作業系統的用戶的安全資料彙集。

不再支援下列 TLS 1.2 加密：

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

由於缺乏對當前加密標準的支援，已知下列客戶端會受到此變更的影響：

* Windows 8.1 和較舊版本 (最後更新於 2018 年)
* Windows Phone 8.1 和較舊版本 (最後更新於 2016 年)
* OS X 10.10 和較舊版本 (最後更新於 2017 年)
* iOS 8.4 和較舊版本 (最後更新於 2015 年)

Android 裝置不會受到此變更的影響。

加密安全等級設定為「標準」的客戶不會受到此變更的影響。
