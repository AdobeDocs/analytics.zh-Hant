---
description: 設定使用者並了解資料取樣。
title: 管理
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 管理

設定使用者並了解資料取樣。

如需 [!DNL Admin Console] 相關說明，請參閱 [Analytics 參考資料](https://marketing.adobe.com/resources/help/zh_TW/reference/index.html)。

## 使用者許可 {#concept_C1440741C77C471EB38A243B013EA620}

若想登入，使用者首先須獲得使用者授權。使用者授權是並行使用授權。使用者可以共用使用者授權，但任何時間的使用者人數受限於購買的使用者授權數量。

<!-- 

c_user_license.html

 -->

當登入使用者的數量超出可用授權數量時，會出現一個對話方塊，通知使用者所有的可用授權都在使用中。並顯示使用者在佇列中的位置，以及一個用來重新檢查佇列位置的連結。有可用授權時，會以電子郵件通知使用者，並出現快顯對話方塊指出可以存取 Ad Hoc Analysis。然後使用者有 15 分鐘的回應時間，否則將丟失在佇列中的位置。

## 授予使用者許可 {#task_22AE669703EC48BA9685414538D8B1FA}

說明本機「Reports &amp; Analytics」管理員如何透過權限系統授予使用者授權的步驟。

<!-- 

t_user_licenses.xml

 -->

1. 登入 [!DNL Experience Cloud]。
1. 按一下&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 使用者管理」]**。
1. 按一下「**[!UICONTROL 編輯群組]**」。

   若您的公司已購買使用者授權，則[!UICONTROL 「Ad Hoc Analysis 授權使用者」]群組會顯示於[!UICONTROL 「群組名稱」]欄。亦會顯示使用者登入的可用授權數量。

1. 按一下&#x200B;**[!UICONTROL 編輯]**。
1. 在[!UICONTROL 指派使用者登入]下，選取想要新增至群組的使用者，然後按一下&#x200B;**[!UICONTROL 新增]**。
1. 按一下&#x200B;**[!UICONTROL 「儲存群組」]**。

   授權系統不會限制新增至群組的使用者人數。但所購買使用者授權數目的同時使用量有限制。

## 管理使用者作業 {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

說明管理員如何終止   使用者作業的步驟。這個功能無法防止已終止的使用者再次登入。

<!-- 

t_managing_users.xml

 -->

1. 按一下&#x200B;**[!UICONTROL 「Adobe Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 使用者管理」]**，然後按一下&#x200B;**[!UICONTROL 「管理使用者」]**。
1. 找到使用者，然後按一下&#x200B;**[!UICONTROL 終止]**。

   在[!UICONTROL 「作用中的 Ad Hoc Analysis 作業」]頁面中，閒置最久的使用者會顯示在清單頂端。

## 權限 {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

您可到 [!DNL Administration Console] 設定報表套裝的存取權限。您可在報告套裝層級設定權限。例如，如果您啟用了多個報表套裝，但您不想授予每個使用者所有報表套裝的存取權，則您可以為特定的報表套裝建立群組，然後將這些使用者指派至適用群組。

## 新增使用者至完全報表存取群組 {#task_E821BF3B4FDB434D844A98AAB15487A9}

說明如何授權非管理員使用者存取所有報表套裝的步驟。

<!-- 

t_permissions.xml

 -->

1. 登入 **[!UICONTROL Experience Cloud]**。
1. 按一下「**[!UICONTROL Adobe Adone Analytics > 管理員]** > **[!UICONTROL 使用者管理]** > **[!UICONTROL 編輯群組]**」。
1. 按一下&#x200B;**[!UICONTROL 完全報表存取]**。
1. 在[!UICONTROL 現存使用者]中，選取使用者，然後按一下&#x200B;**[!UICONTROL 新增]**。
1. 按一下&#x200B;**[!UICONTROL 「儲存群組」]**。

## 建立權限群組 {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

為非管理員使用者建立特定報表套裝的權限群組。

<!-- 

t_permission_groups.xml

 -->

1. 登入 **[!UICONTROL Experience Cloud]**。
1. 按一下「**[!UICONTROL Adobe Adone Analytics > 管理員]** > **[!UICONTROL 使用者管理]** > **[!UICONTROL 編輯群組]**」。
1. 為非管理員使用者建立權限群組，包括您想讓使用者存取的已啟動 Ad Hoc Analysis 報表套裝。

   建立新專案時，使用者可用的報表套裝會顯示在 [!UICONTROL Report Cloud] 功能表中。

## 在 Java 中設定 Proxy 政策 {#task_3B03F58519544025B55CF54FACF8F4F5}

說明在收到伺服器連線錯誤時，如何設定 Proxy 政策的步驟。

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis 使用 HTTP 來與伺服器通訊。與其他 HTTP 流量相同，它也必須遵守相同的 Proxy 政策。

1. 在 [!DNL Windows Control Panel] 中，啟動[!UICONTROL 「Java 控制面板」]。
1. 在&#x200B;**[!UICONTROL 一般]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL 網路設定]**。
1. 選取&#x200B;**[!UICONTROL 使用瀏覽器設定]**，或手動設定 Proxy 設定。
1. 按一下&#x200B;**[!UICONTROL 確定]**，然後按一下 **[!UICONTROL Java 控制面板]**&#x200B;上的[!UICONTROL 確定]。

## 資料取樣的方式 {#concept_8433CFD38E0243849E92DF4F1E743AC3}

對訪客資料取樣可以產生有意義的精確報告。並使用日期範圍作為載入專案的資料片段。一個片段通常代表目前所在月份，以及前兩個月。

<!-- 

c_overview_data_sampling.xml

 -->

為了實現最佳化處理，Ad Hoc Analysis 在每個片段最多可使用大約 7.5 億次點擊。(點擊率 = 頁面檢視 + 事件。) 

為了得到預計的取樣率，系統會計算每個資料集的預計點擊率，然後除以 7.5 億，如下所示：

* (平均每日點擊次數 x 片段的天數) / 7.5 億

例如，如果每日有 1000 萬次點擊，資料片段為 90 天：

* (10,000,000 x 90) / 750,000,000 = 1.2

因此，爲了將此 90 日片段的點擊次數控制在 750,000,000 次以內，應以 1.2:1 的比例取樣資料，但是，由於僅取整數，因此，取樣率應為 2:1。

另舉一例，如果每日有 1000 萬次點擊，資料片段為 365 天：

* (10,000,000 x 365) / 750,000,000 = 4.8

因此，為了將此 365 日片段的點擊次數控制在 750,000,000 次以內，應以 4.8:1 的比例取樣資料，但是，由於 Discover 僅取整數，因此，取樣率應為 5:1。
