---
title: 銷售eVar和產品尋找方法
description: 深入探討銷售eVar背後的概念，以及其處理和配置資料的方式。
source-git-commit: 746c2cfd3236df7ec7498749015ddf75c1e558f5
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# 銷售eVar和產品尋找方法

本檔案說明銷售eVar背後的概念，這些eVar的處理和配置資料的方式與標準eVar不同。 也說明銷售eVar與「產品尋找方法」的關聯。

雖然大部分的零售網站都有許多尋找產品的方式，但Adobe認為下列是每個零售客戶在Adobe Analytics中都應追蹤的基本產品尋找方法：

* 內部搜尋關鍵字
* 內部促銷活動追蹤代碼
* 銷售/瀏覽類別
* 交叉銷售連結

就本檔案而言，我們將幾個eVar對應至以下解決方案：

* eVar2:內部搜尋關鍵字
* eVar3:內部促銷活動追蹤代碼
* eVar4:銷售/瀏覽類別
* eVar5:交叉銷售連結

我們可以使用其他eVar來測量所有產品尋找方法彼此相對的效能。 除了上述尋找方法外，比較中還會包含其他尋找方法，例如來自外部網站的產品詳細資料頁面連結。

* eVar1:產品尋找方法

您不應將其中任何變數設為標準eVar，而應將其設為銷售eVar。  使用銷售eVar可讓您將任何成功的活動分配給eVar在&#x200B;*per-product*&#x200B;層級擷取的值，而非&#x200B;*per-visit/per-order*&#x200B;層級。 在本檔案的其餘部分中，我將說明每項產品與每筆訂單分配之間的差異。
