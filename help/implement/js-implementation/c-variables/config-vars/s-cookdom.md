---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostname`. Instead of using , you can explicitly set  to what you want to use in your implementation. `s.cookieDomainPeriods``s.cookieDomain`舉例來說，您可以使用下列語法，以完全合格的頁面名稱來設定 Cookie:

`s.cookieDomain = window.location.hostname;`
