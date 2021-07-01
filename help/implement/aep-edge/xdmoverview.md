---
title: 透過 Analytics 使用 XDM 資料
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料概觀
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# 透過 Analytics 使用 Adobe Experience Platform Edge 資料

您可以使用 [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=zh-Hant)，將資料傳送至 Adobe Analytics。將 [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 轉譯為 Analytics 使用的格式即可。

Analytics 透過兩種方法收集 XDM 資料：

* 自動從 XDM 結構對應
* 手動對應至內容資料

## 自動對應

自動對應仰賴 XDM 中的預設[結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hant)，會自動填入典型 Analytics 資料收集所包含的 JSON 物件。自動從 XDM 對應至您設定之報表套裝的 Analytics 變數，不需要開發人員支援即可整合。

## 手動對應

[](xdm-manual.md)手動將 XDM 資料對應至 Analytics 仰賴 [Analytics 內容資料](../vars/page-vars/contextdata.md)變數。這些變數會放入符合適用結構的 JSON 物件中。您的開發團隊一般會在實作時新增內容資料，然後管理員會設定[處理規則](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)，將該資料套用至指定的報表套裝。

## 設定

若要將 Analytics 設定為可接受 XDM 資料：

1. 安裝及[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant)。

2. 請確定適用的報表套裝已對應至您想要的資料。XDM 資料會自動從 Adobe Experience Platform 進入報表套裝。
