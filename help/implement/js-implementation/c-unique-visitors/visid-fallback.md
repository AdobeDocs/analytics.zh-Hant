---
description: 如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。
keywords: Analytics 實施
seo-description: 如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。
seo-title: 備援ID方法
solution: Analytics
title: 備援ID方法
topic: 開發人員和實施
uuid: f242d481-81f0-4287-be4 f-52fd03 eb01 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 備援ID方法

如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。

## 備援訪客身分識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

JavaScript 1.x 及 JavaScript H.25.3 適用的 AppMeasurement (於 2013 年 1 月發行) 包含新的備援訪客身分識別方法，適用於瀏覽器會封鎖 Adobe 資料收集伺服器所設定的 Cookie (名為 `s_vi`) 的訪客。過去在無法設定 Cookie 時，在資料收集期間會使用 IP 位址和使用者代理字串的組合來識別訪客。

透過這項更新，在標準 `s_vi` Cookie 無法使用時，將會以隨機產生的唯一 ID 在網站的網域上建立備援 Cookie。此 Cookie (名為 `s_fid`) 會設定 2 年的有效期，且會作為後續的備援身份識別方法。This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

瀏覽總計會包含所有以 `s_vi` Cookie 識別，或使用備援方法識別的訪客數。

## IP 位址、使用者代理、閘道 IP 位址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.
