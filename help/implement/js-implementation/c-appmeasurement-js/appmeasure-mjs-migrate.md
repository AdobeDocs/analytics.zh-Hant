---
description: 下表包含您在移轉實施時所需執行的工作清單。
keywords: Analytics實作；appmeasurement；移轉；移轉；javascript
seo-description: 下表包含您在移轉實施時所需執行的工作清單。
seo-title: 移轉至 JavaScript 適用的 AppMeasurement
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 移轉至 JavaScript 適用的 AppMeasurement
topic: 開發人員和實施
uuid: 5be345a8-5a95-4176-a2 e6-97139b9 b46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 移轉至 JavaScript 適用的 AppMeasurement

下表包含您在移轉實施時所需執行的工作清單。

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) 檢查外掛程式相容性

其中：s\_ code. js

有些外掛程式已不受支援。See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) 下載新的 AppMeasurement

其中：管理員&gt;代碼管理器

下載 zip 包含縮小的 AppMeasurement.js 檔案，以及「媒體」和「整合」模組的 Javascript 檔案。

![](assets/step3_icon.png) 將s\_ code. js自訂複製 `AppMeasurement.js`。

其中：s\_ code. js和AppMeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (可選) 更新外掛程式

其中：AppMeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (可選) 更新「媒體」和「整合」模組

其中：AppMeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) 部署新的 JavaScript

其中：您的網站

您可以根據標準程序部署新的 JavaScript 檔案。您現有的頁面程式碼與此版本相容。