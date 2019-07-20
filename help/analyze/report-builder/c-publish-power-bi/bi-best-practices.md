---
description: 'null'
seo-description: 'null'
seo-title: 最佳實務
title: 最佳實務
uuid: 6d55a9aa-030e-4e4d-963c-ec9 cc9 cf
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 最佳實務

## 在 Power BI 視覺效果中保留參考 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

建立請求後，該請求在 Power BI 中將一律具有相同的參考。但如果您刪除請求，則您針對相同維度所建立的新請求將會使用該參考。

如果您刪除活頁簿中的請求，請確認在 Power BI 中，您沒有指向該請求的視覺效果，否則該視覺效果將會中斷。

* 如果可以，請勿刪除您在 Report Builder 中建立的請求。
* 請確認如果您確實刪除 Report Builder 中的請求，也會一併刪除 Power BI 中對應的視覺效果。
* 如果無法確定: 請刪除您不再需要的請求，然後重新發佈，並前往 Power BI 以查看哪些視覺效果已中斷。

