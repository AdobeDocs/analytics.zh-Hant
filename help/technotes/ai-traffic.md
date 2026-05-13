---
description: 瞭解如何報告來自AI聊天機器人的流量
title: 分析來自AI聊天機器人的流量
feature: Metrics, Data Configuration and Collection
exl-id: 0b013b7d-02a2-405d-bdd6-c991f0baac8e
TQID: https://experienceleague.adobe.com/lyzSP-7iZ8Y5XiTG1t7Axsg1f5AJf6BbcZbu7MmkwWU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b7156124-d291-4de4-ac0c-ed17d8078449id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 2%

---

# 分析來自對話式AI工具的流量

Adobe Analytics提供可分析網站上AI流量的工具。

分析AI流量時，您首先需要瞭解可以發生的AI流量型別以及哪些型別會產生點選。 接著，您就可以在Analysis Workspace中分析流量。

## 瞭解AI流量

### 瞭解AI流量的型別

您網站上的AI流量會在以下任何情況下發生：

* **預先訓練期間**：當您的網站內容被刮取並擷取到AI訓練資料中時，不常發生。

* **當回應隨選提示時**：當使用者以問題提示AI且AI聊天機器人回應時發生。 AI聊天機器人會執行網頁搜尋，而您網站中的內容會包含在回應中。 (這類互動有時稱為「擷取 — 擴大產生」(Retrieval-Enhanced Generation， RAG)。)

  有些AI聊天機器人回應包含您網站上原始資料的連結，有些則沒有。

* **執行代理式工作流程時**：當AI代理程式在瀏覽器中點進一連串網頁以回應使用者要求時，瀏覽您的網站時就會發生。 在這種情況下，AI會作為提出請求之使用者的代理程式。

### 瞭解何時產生AI流量的點選

在頁面上執行JavaScript時，會在網頁上產生點選。 根據網站上發生之AI流量的型別，JavaScript可能會執行，也可能不會執行。

| AI流量型別 | 產生點選 | 考量事項 |
|---------|----------|---------|
| **預先培訓** | 是 | 將您網站的內容擷取至AI時，會在預先訓練期間產生點選。 但是，預先訓練並不常進行，並且包含在AI預先訓練中的內容可以在未來的回應中一次又一次地重複使用，而無需在您的網站上產生進一步的點選。 <p>換言之，在AI預先訓練期間發生的單一點選可重複用於多個隨選回應，而不需在您的網站上產生其他點選。</p><p>如需有關如何在Analysis Workspace中分析此類AI流量的資訊，請參閱[使用機器人偵測分析AI流量](#analyze-ai-traffic-using-bot-detection)。</p> |
| **隨選提示** | 否 | AI回應不會產生任何點選，因為回應會使用以下組合：<ul><li>預先訓練的資料<br/>資訊已包含在AI的預先訓練知識中，因此AI不會在頁面上執行JavaScript。</li><li>隨選網路搜尋<br/>在網路搜尋期間只會擷取網頁的原始HTML，因此AI不會在頁面上執行JavaScript。</li></ul> |
| AI回應中的&#x200B;**Source資料連結** | 是 | 當使用者按一下包含在AI回應中的原始資料的連結時，就會產生點選。 如果回應中包含連結，且使用者未點按該連結，則不會產生點選。 <p>有些AI聊天機器人回應包含原始資料的連結，有些則沒有。 </p><p>如需有關如何在Analysis Workspace中分析此型別AI流量的資訊，請參閱[依反向連結型別分析AI流量](#analyze-ai-traffic-by-referrer-type)。</p> |
| **代理式工作流程** | 是 | 點選會在每個頁面上產生，因為AI代理程式會代表使用者點進工作流程。 <p>如需有關如何在Analysis Workspace中分析此型別AI流量的資訊，請參閱[依反向連結型別分析AI流量](#analyze-ai-traffic-by-referrer-type)。</p> |

## 在Analysis Workspace中分析AI流量

### 依反向連結型別分析AI流量

您可以在Analysis Workspace中使用反向連結型別維度，以分析下列型別的AI流量：

* AI回應中的Source資料連結

* 代理式工作流程

反向連結型別維度包含[交談式AI工具維度專案](/help/components/dimensions/referrer-type.md#conversational-ai-tools)。 此維度項目包含已預先定義的 AI 聊天機器人清單。

如需詳細資訊，請參閱[反向連結型別](/help/components/dimensions/referrer-type.md)。

### 使用機器人偵測分析AI流量

您可以在Analysis Workspace中使用機器人偵測來分析來自預先訓練的AI流量。
