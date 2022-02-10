---
title: 查看當前Adobe Analytics發行說明
description: 最新分析發行說明
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 44bbcabf0bdc74b560a650ce1892a52b4d98052c
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 61%

---

# 本Adobe Analytics發行說明（2022年2月）

>[!IMPORTANT]
>
>本發行說明包含可能更改的預發行資訊。

**上次更新**:2022年2月10日

了解關於 [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。取得 Experience League 上的最新自助文件、教學課程和課程。

## Adobe Analytics 新功能 {#aa-features}

| 功能 | 說明 | [目標日期](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=zh-Hant) |
| ----------- | ---------- | ------- |
| 移動記分卡項目預覽模式 | 從記分卡生成器直接啟動移動記分卡在分析儀表板應用中的外觀預覽。 預覽模式允許用戶以應用程式中的方式與篩選器和圖表交互，從而在保存和共用記分卡之前預覽體驗。 用戶還可以在預覽模式下使用設備選取器查看其記分卡在不同設備上的外觀。 | 2022 年 2 月 16 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 解決了 [!UICONTROL 伺服器調用使用情況]。 (AN-279134、AN-279878、AN-280802、AN-279097、AN-191284、AN-269720)
* 已修復導致Data Warehouse導出空.csv檔案的問題。 (AN-280291)
* 已修復導致最近段未填充受眾名稱的問題。 (AN-279715)
* 已修復報告時間較慢的問題。 (AN-280055)
* 已修復分類未對所有維項分類的問題。 (AN-280031)


### Adobe Analytics 中的其他修正

AN-268093、AN-273820、AN-274435、AN-274904、AN-275356、AN-275947、AN-275947276160、AN-276258、AN-276705、AN-277051、AN-277957、AN-278693、AN-278882、AN-279000、AN-279046、AN-279362、AN-279460、AN-279488、AN-279554、AN-279572、AN-279663、AN-279755、AN-279825、AN-280002、AN-280013、AN-280019、AN-280033、AN-280086、AN-280232、AN-280264、AN-280288、AN-280342、AN-280347、AN-280360、AN-280370、AN-280724、AN-280830、AN-280941、AN-281353、AN-281424、AN-281533


## 給 [!DNL Analytics] 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和舊版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允許清單延長即將到期。此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 目前透過允許清單擴展功能使用舊版 [!DNL Analytics] OAuth/JWT 憑證的客戶，以及在 2022 年 5 月 25 日尚未完成移轉至 IMS 的客戶，都將會失去使用 Adobe 服務的權限。直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| [!DNL Reports & Analytics] EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 及其隨附的報告和功能。 [!DNL Reports & Analytics]支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知說明生命週期結束程序。](https://spark.adobe.com/page/6WnF8JK6IRDhf/) |
| 安全檔案傳輸通訊協定 (SFTP) 服務升級 | 2022 年 1 月 13 日 | 在 **2022 年 5 月 2 日**，[!DNL Adobe Analytics] 將會升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。在這次變更後，我們將不再支援某些 SFTP 用戶端設定。我們也會新增一些連線選項，這些選項將會在 **2022 年 3 月 1 日**&#x200B;之前提供。這僅影響使用SFTP發送到Adobe Analytics或從其檢索到的資料。 FTP協定不受影響。 為避免服務中斷，請確保您的SFTP客戶端（代碼、工具、服務）符合詳細更改 [這裡](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)。 |

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 版本注意事項](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 版本說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)

