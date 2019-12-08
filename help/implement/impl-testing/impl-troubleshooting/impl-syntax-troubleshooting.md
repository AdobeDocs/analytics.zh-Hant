---
description: 下表列出正確與錯誤程式碼之間的差異。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 常見語法錯誤
topic: Developer and implementation
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 常見語法錯誤

下表列出正確與錯誤程式碼之間的差異。

| 不正確 | 正確 |
|---|---|
| prop1 | s.prop1 (使用 "s.") |
| s.evar1 | s.eVar1 (使用正確的大寫開頭) |
| s.pagetype='errorpage'; | s.pageType='errorPage'; (使用正確的大寫開頭) |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA'); (單引號的正確用法) |
| s.events='event1'; s.events='event2'; | s.events='event1,event2'; (正確格式) |
| s.pageName="John" (開啟智慧引號) | s.pageName="John" (關閉智慧引號) |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99" (使用分號，而非逗號) |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99" (不使用貨幣符號) |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (將過長的價格進位或截斷) |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2" (在執行多套裝標記時報表套裝 ID 之間不空格) |
| s.events="event1, event2" | s.events="event1,event2" (在執行多事件標記時事件 ID 之間不空格) |
| s.products="product name" | s.products=";product name" (未列出產品類別時使用分號) |

## 其他附註 {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

一律將結束 HTML 備註放在 Adobe 程式碼的結尾處 (即使您使用指令碼的 NOSCRIPT 部分亦然)。
