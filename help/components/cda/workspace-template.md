---
title: CDA Workspace 範本
description: 說明 Analysis Workspace 中 CDA 範本的各個欄位。
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/Zui1m27pi3eQnm-dac2akfGRF01IbPaQ0SwLD01iDAE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: e38cbddc-1633-4cd5-bed5-9f289f2a6029id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 92%

---

# CDA Workspace 範本

{{available-existing-customers}}

Adobe 提供可檢視重要跨裝置效能資料的範本。

1. 導覽至 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) 並使用您的 AdobeID 憑證登入。
1. 按一下頂端的 9 格線圖示，然後按一下「Analytics」。
1. 按一下頂端的 [!UICONTROL 「工作區」]，然後按一下[!UICONTROL 「建立新專案」]。
1. 找出「跨裝置分析」範本，然後按一下「[!UICONTROL 建立]」。
1. 如果出現提示，請變更為支援 CDA 的報表套裝。

已建立包含數個面板的 Analysis Workspace 專案。 頂端會顯示目錄和簡介，以便檢視報表內容並導覽至個別報表。 按一下目錄內的連結，或展開面板的摺疊式功能表，即可檢視那些報表。

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **使用者身分識別**：顯示使用以 Cross-Device Analytics 為基礎之方法識別網站訪客的頻率。
* **衡量客群規模**：顯示「不重複裝置」與「人物」的比較。 這兩個數字的比例稱為「跨裝置壓縮」，也就是此面板中顯示的計算量度。 此轉換量度取決於多種因素：
   * 登入率：登入您網站的使用者越多，Adobe 就越能跨裝置識別並連結訪客。 登入率低的網站壓縮率也會很低。
   * Experience Cloud ID 涵蓋範圍：系統只會連結具有 ECID 的訪客。 使用 ECID 造訪您網站的訪客比例較低，與壓縮率較低有關。
   * 使用多部裝置：若您網站的訪客沒有使用多部裝置，則壓縮率會較低。
   * 報告顆粒度: 依日計算的壓縮通常比依月或年計算的壓縮還小。 依個人在一天內使用多部裝置的機率，會比整個月的機率小。 分段、篩選或使用劃分維度也可以顯示較低的壓縮率。
* **以人物為基礎的區段**：包含區段下拉式清單，可讓您檢視裝置特定資料。 此面板鼓勵您試用區段，以便了解納入或排除裝置類型對報表有何影響。
* **分析跨裝置歷程**：根據裝置類型提供流量和流失報表。
* **跨裝置歸因**：將跨裝置分析和歸因的功能結合在一起。
* **其他秘訣與技巧**：可協助您更順利使用 CDA 的實用主題。
