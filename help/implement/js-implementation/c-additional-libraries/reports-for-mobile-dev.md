---
description: 如同其他訪客，行動裝置也是透過信標受到追蹤的，因此大部分的報表皆正確可用。
keywords: Analytics實作；報告；行動通訊協定；搜尋引擎；搜尋關鍵字；反向連結網域；反向連結；地域劃分；網域；連線類型；時區；Cookie；java；javascript；螢幕色彩；監視器解析度；瀏覽器寬度；高度；netscape外掛程式
seo-description: 如同其他訪客，行動裝置也是透過信標受到追蹤的，因此大部分的報表皆正確可用。
seo-title: 使用行動通訊協定的裝置報表
solution: Analytics
title: 使用行動通訊協定的裝置報表
topic: 開發人員和實施
uuid: aab125d-c131-4402-9bc8-1c7 fd1 bb1 be
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用行動通訊協定的裝置報表

如同其他訪客，行動裝置也是透過信標受到追蹤的，因此大部分的報表皆正確可用。

[!DNL VISTA] 可用來更改透過行動和標準方法所收集到的資料。所有[!UICONTROL 「自訂][!UICONTROL 分析」]([!UICONTROL prop] 和 [!UICONTROL eVar])、[!UICONTROL 「事件」]、[!UICONTROL 「網站流量」]和[!UICONTROL 「路徑分析」]報表皆受支援。

## 搜尋引擎、搜尋關鍵字、反向連結網域和反向連結 {#section_184D2EF9D906443FBDED04A09CDC50E9}

只有從行動頁面傳送的影像要求中已填入反向連結時，這些報表才會有資料。反向連結會透過 "r" 查詢字串參數填入，如「不使用 JavaScript 進行實施」白皮書所說明。您也必須手動將反向連結資訊傳入影像要求中。

'r' 查詢字串參數必須包含反向連結的通訊協定。如果不含通訊協定，將不會填入反向連結報表。For example, use `r=https://msn.com` not `r=msn.com`.

## 地域劃分和網域 {#section_2B4E9443AAFE4ECA961F9E993592E628}

地域劃分報表會以傳送要求之裝置的 IP 位址為基礎。由於行動裝置須透過閘道向 Adobe 伺服器要求影像，因此閘道的 IP 位址將會用來判斷使用者的地理位置。由於閘道及其 IP 位址的註冊網路範圍很大，因此相關聯的地理位置經常不夠精準。

網域也會以閘道的 IP 位址為基礎，這表示網域報表常會包含擁有該閘道之電信業者的名稱。這項資料也可能因為行動虛擬網路營運商 (MVNO) 而失準。

## 連線類型 {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe 會維護屬於行動電信業者之 IP 位址的已知範圍。從屬於已知的行動電信業者的 IP 位址收到點擊時，點擊會以「行動電信業者」出現在「連線類型報表」上。否則，"Lan/Wifi" 下會列出行動流量。

## 時區、Cookie、連接類型、Java、JavaScript、螢幕色彩和解析度、瀏覽器寬度和高度、Netscape 外掛程式 {#section_158C848273AE4691B4413767E849E846}

這些報表都是藉由使用 JavaScript 偵測瀏覽器特定設定而收集的。由於 JavaScript 無法用來在行動裝置上建立影像信標，因此從行動使用者收集而來的資料不會納入這些報表中。
