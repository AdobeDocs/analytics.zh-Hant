---
title: CDA 工作區範本
description: 說明 Analysis Workspace 中 CDA 範本的各個欄位。
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 93%

---

# CDA 工作區範本

{{available-existing-customers}}

Adobe 提供可檢視重要跨裝置效能資料的範本。

1. 導覽至 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) 並使用您的 AdobeID 憑證登入。
1. 按一下頂端的 9 格線圖示，然後按一下「Analytics」。
1. 按一下頂端的 [!UICONTROL 「工作區」]，然後按一下[!UICONTROL 「建立新專案」]。
1. 找出「跨裝置分析」範本，然後按一下「[!UICONTROL 建立]」。
1. 如果出現提示，請變更為支援 CDA 的報表套裝。

已建立包含數個面板的 Analysis Workspace 專案。頂端會顯示目錄和簡介，以便檢視報表內容並導覽至個別報表。按一下目錄內的連結，或展開面板的摺疊式功能表，即可檢視那些報表。

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **使用者身分識別**：顯示使用以 Cross-Device Analytics 為基礎之方法識別網站訪客的頻率。
* **衡量客群規模**：顯示「不重複裝置」與「人物」的比較。這兩個數字的比例稱為「跨裝置壓縮」，也就是此面板中顯示的計算量度。此轉換量度取決於多種因素：
   * 登入率：登入您網站的使用者越多，Adobe 就越能跨裝置識別並連結訪客。登入率低的網站壓縮率也會很低。
   * Experience Cloud ID 涵蓋範圍：系統只會連結具有 ECID 的訪客。使用 ECID 造訪您網站的訪客比例較低，與壓縮率較低有關。
   * 使用多部裝置：若您網站的訪客沒有使用多部裝置，則壓縮率會較低。
   * 報表粒度：依日計算的壓縮通常比依月或年計算的壓縮還小。依個人在一天內使用多部裝置的機率，會比整個月的機率小。分段、篩選或使用劃分維度也可以顯示較低的壓縮率。
* **以人物為基礎的區段**：包含區段下拉式清單，可讓您檢視裝置特定資料。 此面板鼓勵您試用區段，以便了解納入或排除裝置類型對報表有何影響。
* **分析跨裝置歷程**：根據裝置類型提供流量和流失報表。
* **跨裝置歸因**：結合歷程IQ和歸因的功能。
* **其他秘訣與技巧**：可協助您更順利使用 CDA 的實用主題。
