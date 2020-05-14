---
title: 搭配Analytics使用XDM資料
description: '在Adobe Analytics中使用Experience Platform中的XDM資料概觀 '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 4%

---


# 搭配Analytics使用Adobe Experience Platform Edge


您可以使 [用Adobe Experience Platform(AEP)Web SDK](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) ，將資料傳送至Adobe Analytics。 這可將 [Experience Data Model(XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) 轉換為Analytics使用的格式。

Analytics透過兩種方法收集XDM資料：

* 從XDM架構自動映射

* 手動對應至上下文資料

## 自動對應

自動對應依賴於XDM中 [的預設結構](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) ，可自動填入典型Analytics資料收集所包含的JSON物件。 自 [](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) 動從XDM映射至您設定的報表套裝的Analytics變數不需要任何開發人員支援來整合。

## 手動映射

手動將XDM資料對應至Analytics需仰賴 [Analytics上下文資料變數](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) 。 這些變數會放入對應至適用結構描述的JSON物件中。 通常，您的開發團隊會在實施時新增上下文資料，然後管理員設定 [處理規則](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) ，將該資料套用至指定的報表套裝。


## 設定

要設定Analtyics以接收XDM資料，請執行以下操作：

1. 安裝 [及設](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) 定 [](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform Web SDK。

2. 請確定適用的報表套裝已對應至您想要的資料。 XDM資料會自動從Adobe Experience平台流入報表套裝。

