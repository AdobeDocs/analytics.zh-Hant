---
description: 如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。
keywords: Analytics Implementation
title: 備援 ID 方法
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 備援 ID 方法

如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。

## 備援訪客身分識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). 過去在無法設定 Cookie 時，在資料收集期間會使用 IP 位址和使用者代理字串的組合來識別訪客。

透過這項更新，在標準 `s_vi` Cookie 無法使用時，將會以隨機產生的唯一 ID 在網站的網域上建立備援 Cookie。此 Cookie (名為 `s_fid`) 會設定 2 年的有效期，且會作為後續的備援身份識別方法。在無法設定主要 Cookie (`AMCV_` 或 `s_vi`) 的情況下，此變更應該導致瀏覽正確性和瀏覽數增加。

瀏覽總計會包含所有以 `s_vi` Cookie 識別，或使用備援方法識別的訪客數。

## IP 位址、使用者代理、閘道 IP 位址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。如果無法設定 `AMCV_` 或 `s_vi` 和 `s_fid` Cookie，將會使用 IP 位址和使用者代理的組合來識別訪客。
