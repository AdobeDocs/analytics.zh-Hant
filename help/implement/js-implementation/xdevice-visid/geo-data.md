---
description: 地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。
keywords: Analytics 實作
seo-description: 地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。
seo-title: 地域劃分資料
solution: Analytics
title: 地域劃分資料
topic: 開發人員和實作
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 地域劃分資料

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。請參閱 [Adobe Experience cloud裝置合作檔案](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。

若客戶從家用電腦瀏覽了您的網站，然後又在 30 分鐘內從行動裝置再次瀏覽，地域劃分資料並不會變更。若您使用 VISTA 將地域劃分資料填入 eVar 中，填入的資料會以每次點擊中的 IP 位址為基礎。如此，若相同瀏覽的 IP 位址有所變更，則可能會產生多個地域劃分資料值。
