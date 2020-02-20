---
title: 交易ID資料來源
description: 瞭解使用交易ID資料來源的一般工作流程。
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

---


# 交易ID資料來源

交易ID資料來源不僅可讓您並排檢視線上和離線資料，還可將資料連結在一起。 它需要在您的Analytics實作 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 中使用變數。

當您傳送包含值的線上點擊時， `transactionID` Adobe會對當時所有已設定或持續存在的變數進行「快照」。 如果找到透過Data Sources上傳的相符交易ID，則離線和線上資料會系結在一起。 首先看到哪個資料來源並不重要。

## 交易ID資料來源的整體工作流程

使用下列一般工作流程開始使用交易ID資料來源：

1. 建立資料來源(「一般」類別和「一般資料來源（交易ID）」類型)。
1. 依照資料饋送設定精靈的指示，取得FTP位置以上傳資料並下載資料來源範本檔案。
1. 更新您的實作以包含變 `transactionID` 數。
1. 使用檔案將資料來源檔案上傳至FTP `.fin` 網站。
