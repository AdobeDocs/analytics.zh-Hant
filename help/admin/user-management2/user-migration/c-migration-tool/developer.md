---
description: 'null'
title: 受移轉影響的 API
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 受移轉影響的 API{#apis-affected-by-the-migration}

## 受移轉影響的 API {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

Adobe 正在移轉所有透過 Analytics 登入的企業，使其從 [!DNL my.omniture.com] 登入，改成透過 Adobe Experience Cloud 驗證。一旦開始移轉作業，原本的 Analytics 專用權限，以及 Analytics Admin API 1.3 和 1.4 等版本所提供的 `GetLoginKey` 方法都將停用，屆時系統將不支援以這些方法建立及管理程式使用者。Experience Cloud 中的所有此類動作，現在都將透過 [!DNL adobe.io] 啟用。

## 受影響的 API 方法 {#section-d19051ac26cc49aeb124f767c4760254}

一旦開始移轉使用者，系統將不再支援 Admin API 1.3 和 1.4 版的以下 API 方法:

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## 可執行的動作{#section-8b0b89a862614f729ebdbe092ce99027}

如果貴公司目前仍在使用以上方法，請尋找最早於 2018 年 3 月 31 日發送的預先移轉通知。系統會在貴公司開始改用 Experience Cloud 驗證的至少 30 天前傳送通知，屆時這些方法將停止支援。

如果貴公司沒有使用上述任何方法，除了確保未開始使用這些方法之外，不需執行任何動作。

如需其他資訊，請參閱以下資源: 

* [一般使用者管理資訊](https://helpx.adobe.com/tw/enterprise/help/users.html)
* [透過 adobe.io 執行使用者管理 API](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [使用者管理 API 論壇](https://forums.adobe.com/community/umapi/overview)
* [將 Analytics 使用者存取和管理移轉至 Experience Cloud](https://marketing.adobe.com/resources/help/zh_TW/experience-cloud/admin-console/analytics-migration/)

