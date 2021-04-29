---
title: 實作Adobe Analytics行銷渠道的最佳實務
description: 更新搭配Attribution IQ和Customer Journey Analytics使用行銷渠道的最佳實務
translation-type: tm+mt
source-git-commit: 5422a051be1c55f394cf3f7fc5bb4f8822a7fb90
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 4%

---


# 與行銷管道搭配使用Attribution IQ-最佳實務

[行銷](/help/components/c-marketing-channels/c-getting-started-mchannel.md) 渠道是Adobe Analytics的重要且強大功能。目前關於行銷渠道實作的指引是在[Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace)和[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)不存在時制定的。

為了讓行銷管道的實作能夠在日後得到證實，並確保與Attribution IQ及Customer Journey Analytics一致地建立報告，我們推出一套更新的最佳實務。 如果您已使用行銷渠道，則可從這些新准則中選擇最佳選項。 如果您是行銷渠道的新手，我們建議您遵守所有新的最佳實務。

首次推出行銷渠道時，僅提供首次接觸和上次接觸維度。 有了現行版本的歸因，就不再需要明確的首次/最後接觸維度。Adobe提供一般的「行銷渠道」和「行銷渠道詳情」維度，以便您將其與所需的歸因模型搭配使用。 這些一般維度的行為與「上次接觸渠道」維度相同，但標示不同，以防止在使用不同歸因模型的「行銷渠道」時混淆。

由於行銷渠道維度取決於傳統的瀏覽定義（由其處理規則定義），因此無法使用虛擬報表套裝來變更其瀏覽定義。 這些修訂的做法使CJA和CJA都能提供清晰、可控的回顧窗口。

## 最佳實踐#1:利用Attribution IQ進行受控分析

我們建議使用[Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace)來取代現有行銷渠道屬性，以微調您的行銷渠道分析。 遵循其他最佳實務，確保分析的一致性與強穩控制，並提供Attribution IQ。

## 最佳實踐#2:無直接和會話刷新渠道定義

不建議直接和內部／工作階段重新整理頻道用於自訂歸因模型(Attribution IQ)。

如果您的組織已設定「直接重新整理」和「工作階段重新整理」，該怎麼辦？ 在此情況下，我們建議您為行銷渠道建立分類，並保留這兩個渠道未分類。 分類的維度會產生與從未設定過的相同Attribution IQ結果。

## 最佳實踐#3:啟用覆寫所有渠道的上次接觸渠道

啟用此設定時，與「工作區」中的「行銷管道」維度搭配使用的自訂歸因模型最能運作。 啟用此設定會在遇到新渠道／詳細資料時，計算行銷渠道例項。 除了直接或內部／工作階段重新整理（我們不再建議與自訂歸因模型搭配使用）外，您應對所有渠道啟用此功能。

## 最佳實踐#4:將訪客參與時間減至最少

將「訪客參與」期間設為「1天」最低值，可將持續值的可能性降至最低。 由於自訂歸因模型(AIQ)允許有彈性的回顧視窗，因此我們建議設定最小值，以盡量降低此設定的影響。

## 最佳實踐#5:行銷渠道處理規則僅適用於已啟用的渠道

請確定您移除已停用渠道的任何行銷渠道處理規則。 只有已勾選為啟用的行銷渠道才應有規則。
