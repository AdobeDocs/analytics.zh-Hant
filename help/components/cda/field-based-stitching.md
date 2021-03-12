---
title: 依欄位彙整
description: 了解使用依欄位彙整方式來結合資料的先決條件和限制。
translation-type: tm+mt
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 35%

---


# 依欄位彙整

跨裝置分析提供將資料彙整在一起的兩種不同方法。此方法依賴 Analytics 變數 (例如 [prop](/help/implement/vars/page-vars/prop.md) 或 [eVar](/help/implement/vars/page-vars/evar.md)) 包含人員識別碼。使用該變數當作將裝置連結在一起的基礎。

## 依欄位彙整的專屬必要條件

如果想使用依欄位彙整來實作跨裝置分析，需具備下列條件。請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* [概觀頁面](overview.md)上列出的所有必要條件。
* 您的實作必須設定 prop 或 eVar，才能盡可能唯一識別個人身分，例如當使用者登入或開啟電子郵件時。這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。為依欄位彙整進行佈建時，請將所需的識別變數傳達給您的客戶經理。

## 依欄位彙整的專屬限制

* 以欄位為基礎的拼接功能最適合具有高使用者識別／驗證率的報表套裝。
* 雖然prop和eVar都有處理大小寫字元以用於報告用途的規則，但欄位式拼接不會以任何方式轉換用於拼接的prop或eVar。 欄位式拼接會使用指定欄位中的值，因為它存在於後VISTA規則和後置處理規則。 縫合過程區分大小寫。 例如，如果prop/eVar中有時出現「Bob」一詞，有時出現「BOB」一詞，則縫合程式會將這些人視為兩個不同的人。
* 鑑於欄位式拼接區分大小寫，Adobe建議檢閱適用於欄位式拼接之prop或eVar的任何VISTA規則或處理規則。 需要審查這些規則，以確保這些規則都未引入相同ID的新形式。 例如，您應確定沒有VISTA或處理規則將小寫引入只有部分點擊的prop或eVar。
* 現場拼接不支援使用多個prop或eVar進行拼接。 例如，如果eVar12包含登入ID，而eVar20包含電子郵件ID，您必須選擇其中一個。
* 欄位式拼接不會合併或串連欄位(例如，eVar10 + prop5)。
* prop或eVar應包含單一類型的ID。 例如，prop或eVar不應包含登入ID和電子郵件ID的組合。
* 如果同一位訪客的時間戳記相同，但拼接prop或eVar中的值不同，則CDA會根據字母順序進行選擇。 因此，如果訪客A有兩個點擊，且其中一個點擊指定Bob，而另一個點擊指定Ann,CDA會選擇Ann。


## 後續步驟

一旦貴組織符合所有要求並瞭解限制後，您就可以開始「設定跨裝置分析」([ Setting up Cross-Device Analytics)](setup.md)。
