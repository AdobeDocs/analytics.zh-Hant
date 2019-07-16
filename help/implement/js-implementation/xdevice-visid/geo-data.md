---
description: 地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。
keywords: Analytics 實施
seo-description: 地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。
seo-title: 地域劃分資料
solution: Analytics
title: 地域劃分資料
topic: 開發人員和實施
uuid: 8449fc11-c367-4698-a73 e-f6 cb59 f8 c945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 地域劃分資料

>[!IMPORTANT]
>
>不再建議這種識別跨裝置訪客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。

若客戶從家用電腦瀏覽了您的網站，然後又在 30 分鐘內從行動裝置再次瀏覽，地域劃分資料並不會變更。如果您使用VISTA以地域劃分資料填入eVar，則會以每次點擊中的IP位址為基礎。如果相同瀏覽的IP位址變更，則可能會產生多個地域劃分資料值。
