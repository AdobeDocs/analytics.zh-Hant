---
title: 查看當前Adobe Analytics發行說明
description: 最新分析發行說明
source-git-commit: f8c2d98e49ead838781b175aa9f22712d6802a9d
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 98%

---


# 最新Adobe Analytics發行說明

## Adobe Analytics 新功能 {#aa-features}

| 功能 | 說明 | 目標日期 |
| ----------- | ---------- | ------- |
| 不適用 |  | 參閱[一般可用性](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=zh-Hant) |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 和 Customer Journey Analytics 的漏洞修復 {#aa-fixes}

* 修正維度項目遺失 Audience ID 處的 Analysis Workspace 問題。 (AN-262038；AN-279315)
* 修正載入 Workspace 所儲存 [!DNL Target] 專案時無法載入用戶的問題。 (AN-277461；AN-275825；AN-266397)
* 修正 UI 內可見未啟用功能的問題。(AN-262006)
* 修正使用 Workspace 內日期欄位變更日期時發生的問題。 如此將會使[!UICONTROL 結束時間]從晚上 11:59 變更為午夜 12:00。 (AN-277269；AN-277481)
* 修正將新區段加至已載入區段時導致區段 UI 中斷的問題。 (AN-260827)
* 修正用戶無法存取共用 Workspace 專案的問題。 (AN-267529)
* 已新增一個錯誤消息；這是會在滾動日期範圍的開始日期晚於結束日期時顯示的訊息。(AN-270488)
* 已修復各種資料摘要的問題。 (AN-275876、AN-270512、AN-277284、AN-277290、AN-274893、AN-274606、AN-269651)
* 修正圖形中日期範圍忽略表格日期過濾器的問題。 (AN-263999)
* 修正因日光節約時間而使排程報告過早發送的問題。 (AN-276410；AN-276305)
* 修正在 Workspace 內無法將專案下載至 `.csv` 檔案的問題。 (AN-275834)

### Adobe Analytics 中的其他修正

AN-253294；AN-254976；AN-255377；AN-255561；AN-258550；AN-259336；AN-263935；AN-265094；AN-269441；AN-269486；AN-269855；AN-271166；AN-271588；AN-272088；AN-272249；AN-272859；AN-272873；AN-272885；AN-273229；AN-273913；AN-274237；AN-274472；AN-274491；AN-274619；AN-274766；AN-275248；AN-275259；AN-275271；AN-275315；AN-275388；AN-275418；AN-275597；AN-275643；AN-275650；AN-275651；AN-275675；AN-275682；AN-275704；AN-275711；AN-275796；AN-275834；AN-275923；AN-275941；AN-276044；AN-276125；AN-276157；AN-276397；AN-276597；AN-276789；AN-276834；AN-276861；AN-276870；AN-276963；AN-276975；AN-277000；AN-277044；AN-277093；AN-277200；AN-277215；AN-277271；AN-277281；AN-277362；AN-277419；AN-277492；AN-277498；AN-277533；AN-277619；AN-277675；AN-277681；AN-277767；AN-277805；AN-277810；AN-277818；AN-277875；AN-277933；AN-277988；AN-278105；AN-278115；AN-278122；AN-278192；AN-278407；AN-278437；AN-278559；AN-278604；AN-278610；AN-278709；AN-278835；AN-278849；AN-278881；AN-279067；AN-279103；AN-279111；AN-279219；AN-279237；AN-279312

## 給 [!DNL Analytics] 管理員的重要通知 {#aa-notices}

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和舊版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允許清單延長即將到期。此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 目前透過允許清單擴展功能使用舊版 [!DNL Analytics] OAuth/JWT 憑證的客戶，以及在 2022 年 5 月 25 日尚未完成移轉至 IMS 的客戶，都將會失去使用 Adobe 服務的權限。直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| [!DNL Reports & Analytics] EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 及其隨附的報告和功能。 [!DNL Reports & Analytics]支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知說明生命週期結束程序。](https://spark.adobe.com/page/6WnF8JK6IRDhf/) |
| 安全檔案傳輸通訊協定 (SFTP) 服務升級 | 2022 年 1 月 13 日 | 在 **2022 年 5 月 2 日**，[!DNL Adobe Analytics] 將會升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。在這次變更後，我們將不再支援某些 SFTP 用戶端設定。我們也會新增一些連線選項，這些選項將會在 **2022 年 3 月 1 日**&#x200B;之前提供。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定將不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 將符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)詳述的變更。 |
| 「_全球 + 中國_」RDC 類型 | 2021 年 11 月 22 日 | 「_全球 + 中國_」是一種新的地區資料收集 (RDC) 類型，它使用[!UICONTROL 中國效能最佳化附加元件套件]簡化了全球客戶的流量路由。在過去，您必須決定資料應該路由至中國收集端點或其中一個全球收集端點。現在您可以選擇這個 RDC *類型*，讓 Adobe 根據用戶的地理位置來決定最佳收集端點。 |
| 資料來源中完整處理的生命週期結束 | 2021 年 10 月 18 日 | 在 **2022 年 1 月 31 日**，Adobe 將終止完整處理的服務。此服務可讓用戶將離線點擊資料擷取至 Analytics。此功能透過 [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 提供。[了解更多](https://experienceleague.adobe.com/docs/analytics/import/data-sources/data-types-and-categories/datasrc-fullproc-eol.html?lang=zh-Hant?lang=zh-Hant) |

{style=&quot;table-layout:auto&quot;&quot;

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 版本注意事項](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。