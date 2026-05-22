---
title: 疑難排解Activity Map資料彙集
description: 判斷為何影像要求中看不到Activity Map資料
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
TQID: https://experienceleague.adobe.com/gv0QMe3b8xe17THNCvDN0g7bPy73XdakcSsZYio8K5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 429
ht-degree: 16%

---

# 疑難排解Activity Map資料彙集

如果您沒有看到Activity Map維度的資料，請使用此頁面協助判斷原因。

## 使用除錯工具確認資料收集

首先，請確定AppMeasurement正確收集Activity Map資料。

1. 下載並安裝[Adobe CX Enterprise Debugger Chrome Extension](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/debugger/home)。
2. 導覽至您的網頁，然後按一下連結。
3. 後續頁面載入時，請開啟偵錯工具。 驗證您看到夾在`activitymap.`和`.activitymap`之間的Activity Map內容資料變數：

## Activity Map資料不存在的可能原因

檢查下列專案，確認Activity Map元件是否存在：

* **AppMeasurement版本**： v1.6及更高版本支援Activity Map。 升級到最新穩定AppMeasurement版本時，許多Edge案例問題都已解決。
* **Activity Map模組**：檢查`AppMeasurement.js`檔案中是否有`AppMeasurement_Module_Activity_Map`模組。 如果您的實作使用Adobe Experience Platform來收集資料，請確定在&#x200B;**[!UICONTROL 連結追蹤]**&#x200B;下設定Analytics擴充功能時，已勾選&#x200B;**[!UICONTROL 啟用ClickMap]**。
* **`s_sq` Cookie**： Activity Map依賴於`s_sq` Cookie進行資料收集。
   * 請確定`cookieDomainPeriods`變數已正確設定，尤其是區域網域，例如`*.co.uk`或`*.co.jp`。
   * 請確定`linkInternalFilters`變數已設定為所要的值。 如果點按的連結與內部篩選器不符，Activity Map會將其視為退出連結，不會收集資料。
* **Activity Map覆蓋正在執行**：啟用AppMeasurement覆蓋時，Activity Map不會追蹤您網頁的點選資料。

顯示與使用 Activity Map 不相容的瀏覽器參數。 Adobe建議停用這些設定。

## Chrome

![](assets/Chrome1.png)

![](assets/Chrome2.png)

![](assets/Chrome3.png)

## Firefox

![](assets/Firefox.png)

## Safari

![](assets/Safari1.png)

![](assets/Safari2.png)

## Internet Explorer

![](assets/IE1.png)


**驗證**

使用 Developer Console 網路標記進行互動呼叫：

1. 在網站上載入開發啟動指令碼。
1. 在點選元素後，在「網路」標記中搜尋 &#39;/ee&#39;

Adobe Experience Platform Debugger：

1. 下載並安裝 [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)。
1. 前往「[!UICONTROL 記錄檔] > [!UICONTROL Edge] > [!UICONTROL 連接到 Edge]」。

* **網路索引標籤中的互動呼叫未觸發**：集合呼叫中的點選資料集合，使用`"/ee"`或`"collect?"`篩選。
* **收集呼叫沒有裝載顯示**：收集呼叫的設計方式不會影響到其他網站的導覽，因此檔案解除安裝功能適用於收集呼叫。 此功能不會影響您的資料收集，但如果您需要在頁面上驗證，請將`target="_blank"`新增至個別元素。 連結會在新標籤中開啟。
