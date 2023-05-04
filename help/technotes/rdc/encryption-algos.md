---
title: 支援的 HTTPS 加密算法
description: TLS密碼安全設定和證書類型。
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 299de03c05f6a8af4f6c5d98c76bae54eec4c088
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 30%

---

# 支援的 HTTPS 加密算法

## 密碼安全級別

Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。這些等級會決定與我們伺服器 HTTPS 連線時支援的加密算法。Adobe會根據目前的安全性實務，定期檢閱並更新支援的演算法集。 如果您想要變更密碼安全設定，請聯絡客戶服務。

「Standard」需要TLS 1.2或更新版本，且至少需要128位元加密。 它旨在提供最廣泛的設備相容性，同時維護安全加密。

「高」密碼安全級別需要TLS 1.2或更新版本，並且不支援較弱的密碼。 它專為希望獲得最強加密技術、且不關心對較舊設備的支援的客戶而設計。

已知以下客戶端無法與設為「High」的密碼安全設定連接。

* Windows 8.1 和較舊版本 (最後更新於 2018 年)
* Windows Phone 8.1 和較舊版本 (最後更新於 2016 年)
* OS X 10.10 和較舊版本 (最後更新於 2017 年)
* iOS 8.4 和較舊版本 (最後更新於 2015 年)

## 支援的HTTPS憑證類型

Adobe支援RSA和ECC證書類型，以滿足不同的客戶需求。 RSA證書在客戶端中受到更廣泛的支援，但ECC證書在伺服器端和客戶端上的處理量較少。 對於Adobe管理證書，提供了RSA和ECC。 對於客戶管理的證書，建議同時使用RSA和ECC。 現代客戶機支援RSA和ECC。 下列客戶端已知僅支援RSA證書：

* Windows Vista及舊版（上次於2012年更新）
* Windows Phone 8.0 和較舊版本 (最後更新於 2014 年)
* OS X 10.8 和較舊版本 (最後更新於 2013 年)
* iOS 5.1 和較舊版本 (最後更新於 2012 年)
* Android 4.3及舊版（上次於2013年更新）
