---
description: 自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。
keywords: Analytics 實施;eVar;轉換變數;eVar 值;轉換;成功事件
seo-description: 自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。
seo-title: 轉換變數 (eVar)
solution: Analytics
title: 轉換變數 (eVar)
topic: 開發人員和實作
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 轉換變數 (eVar)

自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。

eVar 最適合用來測量原因和結果，如:

* 哪些內部促銷活動影響收入
* 哪些橫幅廣告最終產生註冊
* 下訂單前使用的內部搜尋次數

>[!IMPORTANT]
>
>實作 Analytics 時，請務必瞭解您將使用哪些 eVar 和使用的 eVar 數量，這些非常重要。您也應該瞭解在 Admin Console 中設定那些 eVar 的方式。如需 eVar 的相關詳細資訊，請參閱 Analytics 說明和參考文件中的[轉換變數 (eVar)](https://marketing.adobe.com/resources/help/zh_TW/reference/conversion_var_admin.html)。

eVar 可以瀏覽為準，其功能類似於 Cookie。傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。

當 eVar 被設定為某個訪客的值，Adobe 會自動記住該值，直到其過期。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。

>[!NOTE]
>
>影像要求的 eVar 中僅可儲存單一數值。如果 eVar 值中需要多個數值，建議您實施[](/help/implement/js-implementation/c-variables/page-variables.md)清單變數 (list vars)。

如需變數的詳細資訊，請參閱:

* [本說明中的 Analytics 實施及報告之變數](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB)
* [變數 - 在報表中的使用方式](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [頁面變數](/help/implement/js-implementation/c-variables/page-variables.md)
* [促銷活動變數](/help/implement/js-implementation/c-variables/page-variables.md)
* [產品變數](/help/implement/js-implementation/c-variables/page-variables.md)
* 行動 SDK 文件中的[產品變數](https://marketing.adobe.com/resources/help/zh_TW/mobile/android/products.html)

