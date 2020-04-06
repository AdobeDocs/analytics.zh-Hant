---
description: 使用 Java 11 執行 Ad Hoc Analysis 相關說明
title: 使用 Java 11 執行 Ad Hoc Analysis
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 使用 Java 11 執行 Ad Hoc Analysis

與使用Java 8執行臨機分析相比，在使用Java 11執行臨機分析時，您需要執行其他步驟。

## 必備條件

請與 IT 團隊合作，確實備齊下列項目：

* 務必安裝 Java 11，並設定好 *JAVA_HOME* 環境變數。
* 必須安裝JavaFX，且 *PATH_TO_FX_SDK* 環境變數指向JavaFX SDK目錄。 例如， *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* ，或 *PC上的PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* 。

## 安裝Java 11的臨機分析

1. 前往 **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]** 。
1. 按一下 **[!UICONTROL Ad Hoc Analysis (Java 11)]**. 這會下載zip檔案。
1. 解壓縮下載的檔案。
1. **選擇。bat(PC)或。sh(Mac)檔案**。 從 Adobe Analytics URL 中找到「sc」之後的數字，依此數字選取相對應的資料中心檔案。(3 = LON, 4 = SIN, 5 = PNW) 如果您使用的是 PC，請前往「關於您的電腦」，確認 PC 執行的是 32 位元或 64 位元的 Windows 作業系統。然後選取適當的。bat檔案。
1. **運行選定的檔案**。 PC：按兩下 .bat 檔。針對Mac:按一下右鍵。sh檔案，然後選擇 **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**。
1. 登入 Ad Hoc Analysis。

>[!NOTE]Java 11 版的 Ad Hoc Analysis 與 Federated ID 和 Enterprise ID 驗證方法不相容。

## Ad Hoc Analysis (Java 11) 不支援的功能

與 Ad Hoc Analysis 相容的 Java 11 版具有幾項已知限制：

* 不支援同盟與企業ID驗證方法。
* 不支援Linux作業系統。
* 使用 Mac 時，請勿使用 Mac 應用程式選單 (包括 *cmd + Q*)。這可能會導致臨機分析關閉而無警告。 請改用臨機分析內的功能表。
* 在MacOS上執行臨機分析時，不支援網站分析視覺化。

## 常見問題解答

**問：畫面顯示「找不到 \bin\javaw」錯誤 (如下所示)，該怎麼辦？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

答：如果出現此錯誤，請與 IT 團隊合作，設定以 Java 11 執行 Ad Hoc Analysis 所需的 *JAVA_HOME* 環境變數。
