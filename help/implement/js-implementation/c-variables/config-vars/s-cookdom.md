---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

變數會判斷 [!DNL Analytics] Cookie `s_cc` 和 `s_sq` 設定的網域。

`s.cookieDomainPeriods` 通常是用來從 `window.location.hostname` 產生 `s.cookieDomain`。您可將 `s.cookieDomain` 明確設定為您要在實施中使用的網域，不必使用 `s.cookieDomainPeriods`。舉例來說，您可以使用下列語法，以完全合格的頁面名稱來設定 Cookie:

`s.cookieDomain = window.location.hostname;`
