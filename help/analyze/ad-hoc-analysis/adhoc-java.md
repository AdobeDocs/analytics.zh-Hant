---
description: 關於如何使用Java 11執行臨機分析的指示。
title: 使用 Java 11 執行 Ad Hoc Analysis
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 使用 Java 11 執行 Ad Hoc Analysis

當您以 Java 11 執行 Ad Hoc Analysis 時，會有 Java 8 所沒有的額外步驟需遵照執行。

## 必備條件

請與 IT 團隊合作，確實備齊下列項目:

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* 安裝 JavaFX，並將 *PATH_TO_FX_SDK* 環境變數指向 JavaFX SDK 目錄。例如，*PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* (Mac)，或 *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* (PC)。

## 安裝適用於 Java 11 的 Ad Hoc Analysis

1. Go to **[!UICONTROL Analytics &gt; Tools &gt; Ad Hoc Analysis]**.
1. Click **[!UICONTROL Ad Hoc Analysis (Java 11)]**. 系統會隨即下載 zip 檔。
1. 將下載的檔案解壓縮。
1. **選取 .bat (PC) 或 .sh (Mac) 檔**。請查看Adobe Analytics URL中的"sc"號碼，以選取適當的資料中心檔案。 (3 = LON, 4 = SIN, 5 = PNW)如果您使用PC，請前往「關於您的PC」以驗證您是在運行32位還是64位Windows作業系統。 接著選取對應的 .bat 檔。
1. **執行選取的檔案**。PC: 按兩下 .bat 檔。Mac: 在 .sh 檔上按一下右鍵，然後選取&#x200B;**[!UICONTROL 「開啟檔案 &gt; 其他...  &gt; 公用程式」&gt; (啟用所有應用程式) &gt; 選取終端機 &gt; 開啟」]**。
1. 登入 Ad Hoc Analysis。

> [!NOTE] 同盟和企業ID驗證方法與Java 11版的臨機分析不相容。

## Ad Hoc Analysis (Java 11) 不支援的功能

與臨機分析相容的Java 11版本有一些已知限制：

* 不支援 Federated ID 和 Enterprise ID 驗證方法。
* 不支援 Linux 作業系統。
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). 這可能會導致 Ad Hoc Analysis 無故關閉，且系統毫無警告。請改用 Ad Hoc Analysis 內的選單。
* 在 MacOS 上執行 Ad Hoc Analysis 時，不支援網站分析視覺化。

## 常見問題集

**問：我會收到「找不到\bin\javaw」錯誤（範例如下）-我該怎麼辦？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

答: 如果出現此錯誤，請與 IT 團隊合作，設定以 Java 11 執行 Ad Hoc Analysis 所需的 *JAVA_HOME* 環境變數。
