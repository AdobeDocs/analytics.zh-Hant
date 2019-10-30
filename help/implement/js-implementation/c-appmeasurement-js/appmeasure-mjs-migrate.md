---
description: 下表包含您在移轉實施時所需執行的工作清單。
keywords: Analytics 實施;AppMeasurement;移轉;移轉;JavaScript
seo-description: 下表包含您在移轉實施時所需執行的工作清單。
seo-title: 移轉至 JavaScript 適用的 AppMeasurement
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 移轉至 JavaScript 適用的 AppMeasurement
topic: 開發人員和實作
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: ht
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 移轉至 JavaScript 適用的 AppMeasurement

下表包含您在移轉實施時所需執行的工作清單。

>[!NOTE]
>
>當您移轉至 JavaScript 適用的 [!DNL AppMeasurement] 時，建議您移轉至 [Identity 服務](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07)。

![](assets/step1_icon.png) 檢查外掛程式相容性

其中：s\_code.js

有些外掛程式已不受支援。詳情請參閱 [AppMeasurement 外掛程式支援](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A)。

![](assets/step2_icon.png) 下載新的 AppMeasurement

其中：管理員 &gt; 代碼管理器

下載 zip 包含縮小的 AppMeasurement.js 檔案，以及「媒體」和「整合」模組的 Javascript 檔案。

![](assets/step3_icon.png) 將 s\_code.js 自訂複製到 `AppMeasurement.js`。

其中：s\_code.js 和 AppMeasurement.js

將 s\_code.js 中所有出現在 `DO NOT ALTER ANYTHING BELOW THIS LINE` 區段前面的程式碼，移至 AppMeasurement.js 的開頭處。

![](assets/step4_icon.png) (可選) 更新外掛程式

其中：AppMeasurement.js

若您使用 getQueryParam 外掛程式，請更新這些呼叫，以使用新的公用程式 [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)。

![](assets/step5_icon.png) (可選) 更新「媒體」和「整合」模組

其中：AppMeasurement.js

若您使用其中一個模組，請從 AppMeasurement\_Module\_Media.js 和 (或) AppMeasurement\_Module\_Integrate.js 複製程式碼，並在 AppMeasurement.js 中將其貼在 `DO NOT ALTER ANYTHING BELOW THIS LINE` 前面。

![](assets/step6_icon.png) 部署新的 JavaScript

其中：您的網站

您可以根據標準程序部署新的 JavaScript 檔案。您現有的頁面程式碼與此版本相容。