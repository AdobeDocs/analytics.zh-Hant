---
description: 當行動裝置向 Web 伺服器要求頁面時，要求會透過閘道傳送；閘道會將行動裝置要求 (通常採用 WAP 或 I-Mode 通訊協定) 轉換為傳送至 Web 伺服器的 HTTP 要求。
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
title: 行動通訊協定網路閘道
topic: Developer and implementation
uuid: a2c92ce2-53a9-4b5b-be1a-89d9f1bf776f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 行動通訊協定網路閘道

當行動裝置向 Web 伺服器要求頁面時，要求會透過閘道傳送；閘道會將行動裝置要求 (通常採用 WAP 或 I-Mode 通訊協定) 轉換為傳送至 Web 伺服器的 HTTP 要求。

當行動裝置向 Web 伺服器要求頁面時，要求會透過閘道傳送；閘道會將行動裝置要求 (通常採用 WAP 或 I-Mode 通訊協定) 轉換為傳送至 Web 伺服器的 HTTP 要求。Web 伺服器會回應閘道，再由閘道將要求轉送至電話。此閘道的作用非常類似於標準 Proxy 伺服器。但閘道會將行動裝置的使用者代理字串傳送至 Web 伺服器。這可讓 Web 伺服器對要求頁面的裝置回應特別為其建置的頁面。

因為 WAP 行動裝置上的螢幕大小極有限，因此行動頁面極簡潔，通常只包含文字和一個快取影像。當影像標記新增至頁面時，每個頁面都會對 Adobe 伺服器傳送影像要求。當影像 (WBMP) 傳回時，Adobe 伺服器會指示瀏覽器不要加以快取。因此，後續的頁面會再次要求影像。此時應使用前述的隨機數字，來防止未遵循 Adobe 不快取指示的瀏覽器。
