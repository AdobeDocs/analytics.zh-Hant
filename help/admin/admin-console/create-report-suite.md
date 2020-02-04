---
title: 建立報表套裝
description: 在 Adobe Analytics 中建立資料收集的基本容器。
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# 建立報表套裝

報表套裝是 Adobe Analytics 用來提取報表的獨立資料單位。組織可以有許多報表套裝，每個報表套裝都包含不同的資料集。雖然過去使用者較重視個別產生報表，但如今使用單一報表套裝已變得更具優勢了。虛擬報表套裝和報表時間處理的推出，讓使用者能夠建立自己的資料子集，進而靈活地取得全域和網站特定資料。

本文的對象為系統層級管理員或 Analytics 管理員，目的在方便這些人員開始資料收集。

## 必備條件

[Adobe Analytics 的第一個管理指南](first-admin-guide.md): 確保系統層級管理員已透過 Experience Cloud Admin Console 將 Adobe Analytics 的權限授予您

## 建立報表套裝

> [!NOTE] 您也可以使用舊版管理員在 Adobe Analytics 中建立報表套裝。Adobe 建議您使用本文所說明的報表套裝設定精靈。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
1. 系統應會自動顯示「歡迎使用 Adobe Analytics」強制回應快顯視窗。如果沒有，請按一下右上方的說明圖示，然後選取「歡迎使用 Adobe Analytics」。
1. 在強制回應視窗中，按一下「開始設定」。
1. 逐步按照每項提示操作，各項提示會概略說明屬性類型、產業與時區等基本知識。按「下一步」。
1. 報表套裝此時已建立完畢。Adobe 建議您也使用開發報表套裝，這樣客戶資料才不會摻雜測試用的資料。按一下右上方的說明圖示，然後再次選取「歡迎使用 Adobe Analytics」。
1. 在強制回應視窗中，按一下「開始設定」。用相同名稱來命名這個報表套裝，但結尾加上「- DEV」。由於此報表套裝只會接收內部流量，因此預估大小可設為最小。
1. 按「下一步」即可完成開發報表套裝的建立。

如需此模式視窗中步驟的詳細資訊，請參閱「實 [作使用指南](/help/implement/prepare/implementation-modal.md) 」中的「實作模式」。

## 疑難排解

**登入 Experience Cloud 後，Analytics 圖示會變灰。**

這表示您的帳戶尚未取得 Analytics 的正確權限。請與您組織的系統層級管理員合作，確保您所屬的設定檔具備存取 Adobe Analytics 的足夠權限。

**登入 Adobe Analytics 後，「歡迎使用 Adobe Analytics」快顯視窗和下拉式清單已經消失。**

請確認您是透過 Experience Cloud 登入，而非透過 my.omniture.com 登入。透過 my.omniture.com 登入的使用者無法使用報表套裝設定精靈。

## 下一步

[在啟動時建立並設定 Adobe Analytics 的屬性](/help/implement/launch/create-analytics-property.md): 建立一個管理 Analytics 實施情形的區域
