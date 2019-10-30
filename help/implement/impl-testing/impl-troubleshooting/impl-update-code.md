---
description: Adobe 在更新 Analytics 程式碼方面提供了幾項最佳實務準則。
keywords: Analytics 實作
seo-description: Adobe 在更新 Analytics 程式碼方面提供了幾項最佳實務準則。
seo-title: 取代 Analytics 程式碼
solution: Analytics
subtopic: 疑難排解
title: 取代 Analytics 程式碼
topic: 開發人員和實作
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 取代 Analytics 程式碼

Adobe 在更新 Analytics 程式碼方面提供了幾項最佳實務準則。

客戶常會使用 Adobe [!UICONTROL 程式碼管理員]將其程式碼取代為最新版本。只要您留意幾項要點，這就是個理想的作法。

## 使用不正確的資料收集伺服器 ID{#section_1726CEB1ABEC408492569B06664410C8}

有時候，並非由 Adobe 程式碼管理員產生的通用 [!DNL s_code.js] 檔案會傳送給在您的網站上實施程式碼的使用者。帳戶因此使用了不正確的資料收集伺服器 ID (如 [!UICONTROL s.dc] 變數中所示)。最佳作法是直接從[!UICONTROL 程式碼管理員]為特定報表套裝產生新程式碼，而不是重複使用其他報表套裝的程式碼。如此最能確保 [!UICONTROL s.dc] 變數正確填入。

## 外掛程式{#section_53650E52D6A54A4795F95E491E7548D1}

有些客戶會實施外掛程式以提升其 Adobe 的使用經驗。當您取代程式碼時，別忘了該程式碼中包含您的外掛程式。以[!UICONTROL 程式碼管理員]建立的程式碼不會附有任何外掛程式程式碼，因此所有外掛程式都必須手動移轉至較新的程式碼基底。請複製您現有的程式碼，以備日後發生狀況而需要還原為原有程式碼時使用。
