---
description: 「Activity Map 設定面板」可讓您修改所有覆蓋圖視覺效果類型的設定和屬性。
title: 設定 Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
translation-type: tm+mt
source-git-commit: d4296a721e01e37c57a8fb44b67599a3cc9e4758
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 60%

---

# 設定 Activity Map

「Activity Map 設定面板」可讓您修改所有覆蓋圖視覺效果類型的設定和屬性。

按一下 Activity Map 工具列上的齒輪圖示，即可存取「Activity Map 設定」面板。

## 一般設定 {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 公司]** | 選擇適用的登入公司。 |
| **[!UICONTROL 報告套裝]** | 您能存取的報表套裝清單不再僅限於網頁標籤所定義的報表套裝。您現在可以使用其他報表套裝替代所選取的報表套裝 (對應至該頁面任一標籤)。此新的報表套裝不需要連結至該頁面上的標籤。如果您變更「Activity Map設定」中選取的報表套裝，「儲存」程式會重新整理所有受影響的Analytics報表。<br>**重要**: [!UICONTROL 虛擬報] 表套裝與即時模 [!UICONTROL 式不相容]，只與標 [!UICONTROL 準模式相容]。如果您處於標準報表套裝的「即時模式」中，但在此對話方塊中選取「虛擬報表套裝」[!UICONTROL ，則當您按一下此處的「確定」**[!UICONTROL 「確定」]**&#x200B;時，就會顯示「標準模式」。 ]此外，日曆控制項已重新初始化，以符合報表套裝的日曆類型（西曆、零售、自訂……）。 |
| **[!UICONTROL 頁面名稱]** | 這些設定套用至的頁面。 |
| **[!UICONTROL 語言]** | 此選項對應至「Adobe Analytics」所提供的語言。 |
| **[!UICONTROL 標籤覆蓋圖表示方式]** | <ul><li>**[!UICONTROL 沒有標籤]**：僅適用於漸層覆蓋圖。在此情況下，覆蓋的顏色會傳達連結排名的感覺</li><li>**[!UICONTROL 值]**：該連結的原始量度總計</li><li>**[!UICONTROL 百分比]**：此連結量度相對於頁面總量度的百分比。</li><li>**[!UICONTROL 排名]**：此連結在已轉譯頁面中呈現之所有連結間的排名</li></ul> |
| **[!UICONTROL 標籤字型大小]** | 可讓您使用滑桿來增加/減少覆蓋圖的標籤字型大小，以提高可讀性。 |
| **[!UICONTROL 漸層／氣泡顏色]** | 若要顯示漸層或氣泡覆蓋圖視覺化的覆蓋圖連結排名，請在一系列顏色中選取。 |
| **[!UICONTROL 顏色漸層根據]** | <ul><li>**[!UICONTROL 前 30 名排行]**：針對前 30 個值標準化色彩強度。</li><li>**[!UICONTROL 絕對量度值]**：色彩強度是絕對量度值的函數。</li></ul> |
| **[!UICONTROL 漸層透明度]** | 選取漸層覆蓋圖的透明度。此設定不會影響[!UICONTROL Bubble]覆蓋圖。 |

## 標準設定{#section_24DB95376E1A448494ECF3F57743FC19}

這些設定會套用至標準模式覆蓋。

![](assets/settings_standard.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 動態資料篩選]** |  |
| **[!UICONTROL 隱藏未收到點擊之連結的覆蓋圖]**。 | 此核取方塊可讓您隱藏未收到點擊之連結的覆蓋圖，以降低介面中的雜訊。 |

## 即時設定{#section_D30F6E62FB5D404090B588F396A460AF}

這些設定會套用至即時模式覆蓋。

![](assets/settings_live.png)

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 顯示排名最前的]** | 若要將&#x200B;**[!UICONTROL 獲益者]**&#x200B;或&#x200B;**[!UICONTROL 損失者]**（或兩者）顯示為覆蓋圖，請選取連結數。 |
| **[!UICONTROL 排除最後 (%)]** | 選取以消除資料稀少的獲益者-損失者連結。過濾掉連結變更的最後百分比，僅檢視具有足夠資料可顯示相關獲益或損失的連結。百分比是根據該頁面的連結數來計算。例如，篩選200個連結清單中的底部10%會篩選出底部20個連結。 |
| **[!UICONTROL 自動更新資料]** | 可讓您決定在計算新時段時，介面中顯示的Analytics資料是否會自動更新。 |
| **[!UICONTROL 自動更新時段]** | 勾選此選項時，每次擷取新資料都會重新整理網頁，以讓頁面上的連結與所收集的資料更緊密同步。 |
