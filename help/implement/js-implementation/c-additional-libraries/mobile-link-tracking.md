---
description: 'null'
keywords: Analytics Implementation;link reference;redir
title: 行動通訊協定上的自訂連結測量
topic: Developer and implementation
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 行動通訊協定上的自訂連結測量

許多行動裝置使用者會將檔案 (例如播客、鈴聲及類似檔案) 下載至其裝置。因為許多行動裝置不支援 JavaScript，因此連結測量必須透過重新導向實施。若要使用重新導向，您必須修改 html 中的 href 連結以加入 REDIR 元素。自訂連結的一般格式如下:

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

建立連結參考時請記住下列事項:

* URL 值必須是 URL 編碼。
* 應設定 pageName 或 page URL (g) 參數。
* 動態變數可以讀取 URL 參數，但無法設定該參數。
* 若未設定 Cookie，Adobe 伺服器會執行正常 Cookie 交握。
* 若要追蹤連結，您必須加入 pe、pev1 和 pev2 參數。

自訂連結測量 URL 看起來類似下列:

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

如需詳細資訊，請參閱[退出連結追蹤重新導向白皮書](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/)。
