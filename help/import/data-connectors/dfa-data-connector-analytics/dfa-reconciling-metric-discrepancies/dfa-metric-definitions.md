---
description: 'Adobe 在討論與 DFA 整合有關的量度時，會使用下列詞彙 '
keywords: DFA
seo-description: 'Adobe 在討論與 DFA 整合有關的量度時，會使用下列詞彙 '
seo-title: 量度定義
solution: Analytics
title: 量度定義
topic: Data connectors
uuid: 062f6863-3da-4e8a-b6 ea-84279d49 c388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 量度定義{#metric-definitions}

Adobe 在討論與 DFA 整合有關的量度時，會使用下列詞彙:

**曝光數**:「曝光數」是指檢視廣告的次數。「曝光數」會就個別的廣告列入報表，但也可彙整至廣告群組或其他多重廣告群組中。Analytics 中的曝光數量度會透過夜間資料來源匯入，從 DFA 匯入。

**點按**:「點按」是指點按廣告的次數，如 DFA 所報告。「點按」會在訪客進入客戶的網站之前，登錄於 DFA 重新導向頁面上。如同曝光數，Analytics 中的點按量度也會透過夜間資料來源匯入，從 DFA 匯入。

**點進**:「點進」是指使用者在點按廣告後進入著陸頁面的次數。此量度可能與點按略有不同。

**閱覽**:「閱覽」是指訪客在檢視廣告後未點按廣告即進入客戶網站的次數。訪客必須在閱覽時程內進入網站，此時程預設為 30 天。產生曝光的時間必須早於前次點按的時間。閱覽會就每一個促銷活動、每一個造訪個別登錄，並且會在整合以 DFA 促銷活動 ID 填入閱覽 eVar 時，以及在設定閱覽事件時計算閱覽次數。
