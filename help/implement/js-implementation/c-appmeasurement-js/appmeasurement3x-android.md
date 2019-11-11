---
description: AppMeasurement 3.x for ios
seo-description: AppMeasurement 3.x for ios的舊版檔案
seo-title: AppMeasurement 3.x for ios
solution: Analytics
subtopic: 書籤
title: AppMeasurement 3.x for ios
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 4907b2930d894525b93b02f743c095f824a61a3b

---


# AppMeasurement 3.x for iOS

*注意：本檔案包含舊版AppMeasurement的舊版資訊，尤其是iOS 3.x版的舊版資訊。
如需目前AppMeasurement實作的詳細資訊，請參[閱關於Javascript適用的AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。*

*上次更新日期： 2018年3月15日適用於iOS的AppMeasurement 3.x*

Adobe appMeasurement for iOS可讓您在Adobe Experience cloud中測量原生的Apple iPhone和iPad應用程式。

本指南分為兩節：其中一節是針對具備Adobe Analytics經驗的分析師，另一節則是針對具備行動應用程式開發經驗的OS開發人員。

**支援的版本**:iOS 4.3或更新版本。

**如需下載所有AppMeasurement**&#x200B;行動平台的「程式庫下載」指示和連結，請參閱Developer Connection上的「測量與最佳化行動應用程式」頁面。 您必須有免費的 Developer Connection 帳戶或報表與分析登入，才能下載程式庫。直到您登入以後，下載連結才會出現。

## 分析師快速入門

本節會逐步帶您實作 iOS 程式庫和新增標準實作所需要的程式碼。內含的步驟將告訴您如何傳送自訂事件和其他資料。

身為分析師的您，必須為您的報表套裝啟用「行動應用報表」。如果您要擷取其他量度，則必須將應用程式所應傳送的上下文資料變數相關的說明提供給您的開發人員。例如，若要在登入後收集使用者名稱，可以讓開發人員在名為 `myco.username` 的上下文資料變數中設定使用者名稱。

### 在 Analytics 中啟用行動應用報表

Analytics 提供用以啟用「行動應用生命週期追蹤」的介面。此映射可以讓 Analytics 自動產生行動應用報表。

1. 開啟「管理控制台 &gt; 報表套裝 &gt; 編輯設定 &gt; 行動管理 &gt; 行動應用報表」。
1. 按一下「啟用行動應用程式生命週期追蹤」。

現在已擷取生命週期量度，而「行動應用報表」會出現在 SiteCatalyst 的「報表」功能表中。

### 使用處理規則擷取其他度量

如果您的實施使用上下文資料傳送其他事件和維度，則必須設定擷取該資料的處理規則。

在建立處理規則前，您的組織中必須擁有認證合格的人員。如需詳細資訊，請參閱處理規則說明。

啟用了「處理規則」之後，複製上下文資料變數範例會示範映射上下文資料所需的程序。

### (選擇性) 啟用離線追蹤

若計劃在裝置離線時儲存點擊，您的報表套裝必須已啟用時間戳記。

啟用離線追蹤後，所有點擊都必須有時間戳記，否則不會加以收集。如果您目前回報 AppMeasurement 資料的報表套裝也可從 JavaScript 收集資料，則必須為行動資料設定個別的報表套裝，以免資料遺失，或使用 s.timestamp 變數在 JavaScript 點擊上加上自訂時間戳記。

如果不確定您的報表套裝是否啟用時間戳記，請聯絡客戶服務。

## 開發人員快速入門

本節會逐步帶您實作iOS程式庫並開始傳送測量資料的步驟，包括：

* 取得程式庫
* 新增程式庫至您的專案
* TrackingHelper 簡述
* 實施


### 取得程式庫

請造訪 Developer Connection 上的測量和最佳化行動應用程式以下載 Android 程式庫。將下載的檔案解壓縮後，會有下列軟體元件:

* admsAppLibrary.jar: 為搭配 Android 裝置和模擬器使用而設計的程式庫。需要 Android 2.0 (含) 以上版本。
* Examples\TrackingHelper.java: 設計來將追蹤程式碼與您的應用程式邏輯分開的選用類別。

### 新增程式庫至您的專案

1. 在 Eclipse IDE 中，用滑鼠右鍵按一下專案名稱。
1. 選取「組建路徑 &gt; 新增外部封存」。
1. 選擇 `admsAppLibrary.jar`.
1. 按一下開啟。
1. 再次以滑鼠右鍵按一下專案，然後選取「組建路徑 &gt; 設定組建路徑」。
1. 按一下訂購及匯出標籤。
1. Ensure that `admsAppLibrary.jar` is selected.

您的應用程式可以使用import com.adobe.ADMS，從admsAppLibrary.jar程式庫匯入類別／介面。*;

### 新增應用程式權限

AppMeasurement 資料庫需要下列權限，才能傳送資料及記錄離線追蹤呼叫:

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### TrackingHelper 簡述

SDK 包含其他選用類別，其名稱為 TrackingHelper。TrackingHelper 用以將測量程式碼與應用程式邏輯分開。

請考慮以下範例: 在您的應用程式中，您想傳送可追蹤每次登入的事件。您可以在登入程式碼之後直接加上下列程式碼以傳送此事件 (別擔心程式碼的詳細資料，稍後我們會討論):

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

這種直接方法也可以，不過為什麼不將此程式碼放在其他地方，以免妨礙您開發應用程式？TrackingHelper 就是「其他地方」。在 TrackingHelper 內部，您可以將此程式碼放入名稱為 trackLogonEvent 的方法中:

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

現在，在您的應用程式碼中只要簡單呼叫 trackLogonEvent 就能追蹤登入事件:

TrackingHelper.trackLogonEvent("username");

您應用程式碼中的測量呼叫減少為一行。此外，如果基本測量邏輯需要變更，只需要更新 TrackingHelper 即可。如果另一個開發人員加入您的程式碼，可以使用您已定義的簡化方法，不需再學習 AppMeasurement 程式庫的速成課程。

我們認為，雖然設定需要多花一兩分鐘，不過您應該偏好在新實施使用 TrackingHelper。本指南中的其餘步驟會引導您進行設定 TrackingHelper 並開始傳送測量資料的步驟。

請務必將 TrackingHelper.java 複製至包含您應用程式之類別檔案的目錄，並取代此檔案上方的套裝名稱，以符合您的套裝結構 (com.company.application)。如果您不想使用 TrackingHelper 來實施，也可在 TrackingHelper 中找到一些範例，您可將之複製至應用程式。

### 實施

1. 開啟 TrackingHelper.java，並以您的報表套裝 ID 和追蹤伺服器更新 TRACKING_RSID 和 TRACKING_SERVER。例如:

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   這些是必要值，而且必須正確，否則無法進行測量。如果不確定這些值，請洽詢您的 SiteCatalyst 專家。

2. 尋找 configureAppMeasurement 方法。您在這裡啟用 SSL、啟用離線追蹤，以及對您的設定進行其他全域變更。現在，解除這行的註解以啟用 debugLogging，直到結果正常為止。

3. 從您應用程式的根活動將新增 configureAppMeasurement 的呼叫。

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

這些就是開始追蹤自訂度量需要的全部程式碼。不過，只要再增加幾行程式碼，就可以啟用生命週期追蹤以自動傳送生命週期度量，包括啟動、升級、當機和每日及每月使用者。

AppMeasurement 程式庫會執行所有費力的工作，您只需要新增兩個方法呼叫至每個應用程式的「活動」類別。

### (建議採用) 追蹤生命週期事件

啟用生命週期追蹤時，每次啟動應用程式時，都會傳送單一點擊來追蹤安裝、升級、參與天數和其他生命週期度量。

若要開始追蹤生命週期事件，請在您的應用程式內部的每個活動中新增對 onResume() 和 onPause() 方法的呼叫，如以下範例所示。也建議您將「活動」或「服務」當成上下文物件傳遞，而非當成全域「應用程式」上下文。

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

完成了！您現在已經在 Android 應用程式中實施了基本生命週期追蹤。在您的網路分析師設定 SiteCatalyst 處理您所報告的 AppMeasurement 度量後，您的 SiteCatalyst 報表套裝中就會包含預設的生命週期度量。

可從此處前往:

* (選擇性) 追蹤自訂事件. 將自訂方法新增至 TrackingHelper，追蹤您要在應用程式中測量的所有事件。 您可以新增方法來追蹤登入、應用程式中購買等等。
* (選擇性) 追蹤應用程式狀態. 應用程式狀態類似頁面檢視。本節告訴您如何將自訂方法加入 TrackingHelper，以追蹤應用程式狀態。
* 視訊測量快速入門. 新增程式碼以追蹤視訊量度，包含視訊檢視、總播放時間和最熱門的視訊。

### (選擇性) 追蹤自訂事件

自訂事件是您的應用程式專有的成功度量。您可以在使用者登入、起始應用程式內的購買，或按一下到您的 Facebook 頁面的連結時，傳送自訂事件。追蹤協助程式類別包含顯示如何追蹤自訂事件的範例。您可以使用此方法作為加入更多事件追蹤方法的範本。

在 TrackingHelper.java 中，定義自訂事件追蹤方法:

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

您可以在程式碼中任一處呼叫此方法來追蹤自訂事件:

`TrackingHelper.trackCustomEvents();`

使用此程序，新增您所需數量的事件追蹤方法。TrackingHelper 簡介包含用以追蹤登入事件的範例方法。

### (選擇性) 追蹤應用程式狀態

追蹤協助程式類別還包含顯示如何追蹤應用程式狀態的範例。追蹤自訂狀態與追蹤事件極為類似，唯一的差別在於您使用 trackAppState 方法而非 trackEvents。

```
measure.trackAppState("name", contextData);
```

從報表觀點來看，trackAppState 會增加頁面檢視，而 trackEvents 不會。

## 視訊測量快速入門

會在「在 SiteCatalyst 中測量視訊指南」中說明視訊測量。所有 AppMeasurement 平台上測量視訊的一般程序都很相似。這一節快速入門提供開發人員任務的基本概覽和程式碼範例。

應用程式和視訊追蹤使用同一個程式庫 admsAppLibrary.jar。說明文件會參照這些方法，作為保持所有平台一致性的媒體模組。

您必須先設定好測量例項，才能使用媒體模組。

若要在 Android 上實施視訊追蹤，請完成下列任務:

* 將播放器事件映射至 SiteCatalyst 變數
* 設定里程碑、區段和呼叫頻率
* 追蹤播放器事件

### 將播放器事件映射至 SiteCatalyst 變數

若要設定視訊測量，必須將您為視訊追蹤選擇的 SiteCatalyst 事件和 eVar 映射至上下文資料變數。如需詳細資訊，請參閱 SiteCatalyst 視訊設定。

您的網路分析師應提供您一份視訊實施工作表，工作表中包含其設定好用來接收視訊資料的 SiteCatalyst 變數清單:

* 視訊名稱(eVar):eVar2
* 視訊名稱(Prop):prop2
* 區段(eVar):eVar3
* 內容類型(eVar):eVar1
* 視訊時間（事件）:event3
* 視訊檢視（事件）:event1
* 視訊完成（事件）:event7
* 視訊區段檢視（事件）:event2

1. 將下列程式碼新增於您在實施中新增的程式碼之後，並以程式碼中的範例取代您選取的 SiteCatalyst 變數:

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. 設定里程碑、區段和呼叫頻率.

3. 追蹤播放器事件.


### 設定里程碑、區段和呼叫頻率

里程碑可讓您在到達視訊中的特定點時傳送事件。區段可讓您將視訊分割為小區段，以執行更詳細的追蹤。呼叫頻率可讓您以特定間隔隨觀賞時間傳送測量呼叫。如需詳細資訊，請參閱視訊度量。

### 映射里程碑

您可以根據總長度百分比或根據經過的秒數定義里程碑。此範例以總長度的百分比來定義里程碑。在 2 分鐘的視訊中，下列程式碼會在 30 秒、60 秒和 90 秒傳送里程碑事件。

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### 映射偏移里程碑

此範例以從視訊開始的經過秒數來定義里程碑。在 2 分鐘的視訊中，下列程式碼會在 20 秒、40 秒和 60 秒傳送里程碑事件，不受視訊總長度的影響。

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### 範例

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### 追蹤播放器事件

若要測量視訊，您必須新增程式碼，告知媒體模組事件何時發生於您的播放器中 (使用 open、play、stop 和 close 方法)。當使用者開始播放視訊時，您必須呼叫 play 方法，讓媒體模組開始計算觀賞的秒數。

如果使用者暫停視訊，您必須呼叫 stop 以暫停計數。這通常會使用播放器公開的事件處理常式來執行。

例如:

載入: 呼叫 open 和 play

Pause: 呼叫 stop。 例如，使用者若在 15 秒後暫停視訊，則呼叫 stop("Video1",15)。

Buffer: 當訊息進行緩衝時呼叫 stop。 當繼續播放時呼叫 play。

Resume: 呼叫 play。 例如，使用者若在起始播放視訊 15 秒後繼續播放視訊，則呼叫 s.play("Video1",15)。

Scrub (滑桿): 當使用者拖曳視訊滑桿時，呼叫 stop。 當使用者放開視訊滑桿時，呼叫 play。

End: 呼叫 stop，然後呼叫 close。 例如，在長 100 秒的視訊結束時，呼叫 stop("Video1",100)，然後呼叫 close("Video1")。

若要完成此操作，可以定義能夠從媒體播放器事件處理常式呼叫的四個自訂函數。傳入 open、play、stop 和 close 的各種參數皆來自播放器。 下列偽代碼說明如何進行操作:

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## 生命週期度量

此工作表列出啟用自動生命週期追蹤時會測量的度量和維度。

### 生命週期度量和維度

設定時，生命週期度量會在上下文資料參數中傳送至 Analytics，隨著每個 mbox 呼叫傳送參數至 Target，並作為觀眾管理的信號。Analytics 和 Target 會使用相同格式，而觀眾管理則對每個度量使用不同的首碼。

針對 Analytics，會自動擷取隨著每個生命週期追蹤呼叫傳送的上下文資料並使用第一欄中列出的度量或維度報表，說明欄中所列者例外。

| 量度 | Analytics內容 | Analytics Context Audience manager信號說明 | 資料／目標參數 |
|--- |--- |--- |--- |
| 首次啟動 | a.InstallEvent | c_a_InstallEvent | 在安裝 (或重新安裝) 後首次執行時觸發。 |
| 升級 | a.UpgradeEvent | c_a_UpgradeEvent | 在升級後首次執行時觸發（只要版本號碼變更）。 |
| 每日參與使用者 | a.DailyEngUserEvent | c_a_DailyEngUserEvent | 於特定一天使用應用程式時觸發。 |
| 每月參與使用者 | 每月參與使用者 | a.MonthlyEngUserEvent | 於特定月份使用應用程式時觸發。 |
| 啟動 | a.LaunchEvent | c_a_LaunchEvent | 在每次執行時觸發，包括損毀和安裝。 | 啟動當超過生命週期作業逾時時時，也會在從背景繼續時觸發。 |
| 當機 | a.CrashEvent | c_a_CrashEvent | 當應用程式未正常退出時觸發。會在當機後啟動應用程式時傳送事件 (如果未呼叫退出，應用程式視為當機)。 |
| 前一個作業長度 | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 彙總的前一個作業長度 (以秒為單位)。 |

*注意：「每&#x200B;**日參與使用者**」和「每&#x200B;****月參與使用者」不會自動儲存在Analytics量度中。 您必須建立處理規則，設定自訂事件來擷取這些量度。*

### 維度

| 量度 | Analytics 上下文資料/目標參數 | Analytics Context Audience manager信號 | 說明 |
|--- |--- |--- |--- |
| 安裝日期 | a.InstallDate | c_a_InstallDate | 安裝後首次啟動的日期。MM/DD/YYYY |
| 升級 | a.UpgradeEvent | c_a_UpgradeEvent | 在升級後首次執行時觸發（只要版本號碼變更）。 |
| 應用程式 ID | a.AppID | c_a_AppID | 以下列格式儲存應用程式名稱和版本:`[AppName] [BundleVersion]`. 例如，myapp 1.1. |
| 距首次使用的天數 | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | 自首次執行起的天數。 |
| 每月參與使用者 | 每月參與使用者 | a.MonthlyEngUserEvent | 於特定月份使用應用程式時觸發。 |
| 啟動 | a.LaunchEvent | c_a_LaunchEvent | 在每次執行時觸發，包括損毀和安裝。 | 啟動當超過生命週期作業逾時時時，也會在從背景繼續時觸發。 |
| 當機 | a.CrashEvent | c_a_CrashEvent | 當應用程式未正常退出時觸發。會在當機後啟動應用程式時傳送事件 (如果未呼叫退出，應用程式視為當機)。 |
| 前一個作業長度 | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 彙總的前一個作業長度 (以秒為單位)。 |
| 上次使用間隔天數 | a.DaysSinceLastUse | c_a_DaysSinceLastUse | 距離上次使用的天數。 |
| 星期 | a.DayOfWeek | c_a_DayOfWeek | 應用程式啟動的工作日數。 |
| 小時 | a.HourOfDay | c_a_HourOfDay | 測量應用程式的啟動時數。使用 24 小時數字格式。用於時間分界，以判斷尖峰使用時間。 |
| 作業系統版本 | a.OSVersion | c_a_OSVersion | OS 版本。 |
| 上次升級的間隔天數 | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | 距應用程式版本編號上次變更的天數。 |
| 上次升級後啟動次數 | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | 自應用程式版本編號上次變更後的啟動次數。 |
| 裝置名稱 | a.DeviceName | c_a_DeviceName | 儲存裝置名稱。 | iOS: 以逗號分隔的 2 位元字串，用以識別 iOS 裝置。 第一個數字通常代表裝置代別，第二個數字通常提供裝置系列的不同成員版本。請參閱 iOS 裝置版本以取得常用裝置名稱清單。 |
| 電信業者名稱 | a.CarrierName | c_a_CarrierName | 儲存行動服務提供者的名稱，如裝置所提供。 |
| 解析度 | a.Resolution | c_a_Resolution | 寬 x 高 (以實際像素表示)。 |

*注意：自上&#x200B;**次升級後的天數**，自上次升級後啟動和電信業者名稱&#x200B;********，不會自動儲存在Analytics變數中。 You must create a processing rule to copy these values to an Analytics variable for reporting.*

## 上下文資料

上下文資料是將應用程式資料傳送到收集伺服器的偏好方法。

您不必明確為 prop 和 eVar 指派值，可以使用上下文資料變數傳送在 SiteCatalyst 中映射的名稱值配對。您可以根據這些索引鍵值配對，設定事件、將值複製至eVar和prop，並執行其他條件陳述式。 這樣的話不需要更新程式碼，就能支援不同的報表套裝設定。

有兩種方法可以使用追蹤方法傳送上下文資料。直接在 PersistentContextData 物件上設定的任何上下文資料隨每個呼叫傳送。也可以將上下文資料當成參數，傳送至只以該呼叫傳送的單一追蹤呼叫。

### 永久性上下文資料

在「永久性上下文資料」中設定的值會隨每個伺服器呼叫傳送。在下列範例中，"key" 和 "value" 會隨所有 trackAppState 呼叫一起傳送:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### 單一呼叫上下文資料

若要傳送單一呼叫的上下文資料，請傳送上下文資料作為追蹤呼叫 (trackAppState、trackEvents 等等) 的參數。

在下列範例中，"key" 和 "value" 會隨三個 trackAppState 呼叫一起傳送。 但是，"key2" 和 "value2" 只會隨第二個 trackAppState 呼叫一起傳送:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## 設定變數

應用程式啟動時會設定下列變數:

*注意：除了ReportSuiteID和trackingServer之外，所有組態變數都是選用的。*

**共用例項**

在呼叫測量前，您必須針對在測量程式庫上呼叫的每個方法擷取程式庫中的例項:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意: 組態變數為私人專用。使用 get 和 set 方法來變更這些值。*

### 設定變數

**reportSuiteIDs**:（必要）您要追蹤的報表套裝或報表套裝（多套裝標籤）。 若要追蹤多個報表套裝，請傳遞每個報表套裝名稱的逗號分隔清單。

您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

範例:

`measure.setReportSuiteIDs("rsid");`

多套裝標記:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**:（必要）識別收集伺服器。

應該以您的追蹤伺服器網域填入此變數，不帶「http://」或「https://」通訊協定首碼。通訊協定字首會由程式庫根據 ssl 變數自動處理。

如果 ssl 為 true，會對此伺服器進行安全連線。如果 ssl 為 false，會對此伺服器進行非安全連線。

您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

範例:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**:預設值：uuid每個訪客的唯一識別碼。 如果未設定自訂 visitorID，會產生唯一的 visitorID。

除非您有特殊使用案例需設定訪客 ID，否則建議使用預設值。設定自訂訪客 ID 有可能在使用生命週期追蹤時，造成重複的瀏覽次數。若要避免此情形，請在設定 App Measurement 前，先設定訪客 ID。

**characterSet**:預設值為UTF-8

語法:

```
String getCharSet()
void setCharSet(String charSet)
```

範例:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:Default is none(used for report suite is defined value)

用於購買或貨幣事件的貨幣代碼，這些事件在 Android 應用程式中得到追蹤。

語法:

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

範例:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**:預設值為5分鐘

指定在兩次應用程式啟動之間需經過的時間長度 (單位為秒)，超過該秒數後，該次啟動即視同新的作業階段。這個逾時值也套用至將應用程式傳送至背景並重新啟動時。應用程式在背景花的時間，不算在作業階段長度中。

語法:

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

範例:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**:預設為false

啟用 (true) 或停用 (false) 經由 SSL (HTTPS) 傳送測量資料。您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

`void setSSL(boolean ssl)`

範例:

`measure.setSSL(true);`

**debugLogging** Default is false

在輸出主控台中啟用 (true) 或停用 (false) 檢視偵錯資訊和程式庫版本。預設情況下，該變數為 false。您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

`void setDebugLogging(boolean debugLogging)`

範例:

`measure.setDebugLogging(true);`

## 追蹤變數

**共用例項**

在呼叫測量前，您必須針對在測量程式庫上呼叫的每個方法擷取程式庫中的例項:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意: 組態變數為私人專用。使用 get 和 set 方法來變更這些值。*

### 永久追蹤變數

**Evar**:將指定的eVar設為提供的值。 eVar 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫清除變數，藉以將其清除為止。

語法:

`void setEvar(int evarNum, String evarValue)`

範例:
`measure.setEvar(1, "value");`

**Prop**:將指定的prop設為提供的值。 prop 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫 clearVars，藉以將其清除為止。

語法:

`void setProp(int propNum, String propValue)`

範例:

`measure.setProp(1, "value");`

**Hier**:將指定的heir變數設為提供的值。 heir 變數會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫 clearVars，藉以將其清除為止。

語法:

`void setHier(int hierNum, String hierValue)`

範例:

`measure.setHier(1, "value");`


**ListVar**:將指定的listVar設為提供的值。 listVar 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫 clearVars，藉以將其清除為止。

語法:

`void setListVar(int listNum, String listValue)`

範例:

`measure.setListVar(1, "value");`

**purchaseID**:purchaseID可用來防止SiteCatalyst重複計算訂單。

每次在您的網站上使用購買事件時，您都必須使用 purchaseID 變數指派獨特的 ID 給此購買。

`measure.setPurchaseID("unique_id");`

**transactionID**:整合資料來源使用交易ID將離線資料與線上交易（如線上產生的銷售機會或購買）關聯。

每個傳送至 Adobe 的唯一 transactionID 都會記錄下來，以便「整合資料來源」上傳有關該交易的離線資訊。

`measure.setTransactionID("unique_id");`

**appState**:（頁面名稱）為應用程式狀態提供的值會儲存在頁面名稱變數中。

`measure.setAppState("state");`

**channel**:measure.setChannel("mobile");

**appSection**:為應用程式區段提供的值會儲存在伺服器變數中。

語法:

`void setAppSection(String Section)`

範例:
`measure.setAppSection("news");`

**campaign**

語法:

`void setCampaign(String Campaign)`

範例:

`measure.setCampaign("112233");`

**products**

語法:

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

範例:

`measure.setProducts("Running;Shoe");`

**events**

語法:

`void setEvents(String Event) //comma-delimited list`

範例:

`measure.setEvents("event1, event2");`

**geoState**

語法:

`void setGeoState(String GeoState)`

範例:

`measure.setGeoState("UT");`

**geoZip**

語法:

`void setGeoZip(String GeoZip)`

範例:

`measure.setGeoZip("12345");`

**永續性內容資料**:放置在「永續性內容資料」中的值會隨每個伺服器呼叫傳送。 若要傳送單一呼叫的上下文資料，請傳送 contextData 雜湊表作為追蹤呼叫 (trackAppState、trackEvents 等等)·的參數。

範例:

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

請參閱內容資料。

**linkTrackVars**:逗號分隔的變數名稱清單，限制目前的連結追蹤變數集。 如果未定義 linkTrackVars，AppMeasurement for Android 會以 trackLink 呼叫傳送所有已定義的變數。

語法:

`void setLinkTrackVars(String Vars) //comma-delimited list`

範例:

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**:逗號分隔的事件清單，限制目前的連結追蹤事件集。 如果未定義 linkTrackEvents，AppMeasurement for Android 會以 trackLink 呼叫傳送所有的事件。

語法:

`void setLinkTrackEvents(String Events) //comma-delimited list`

範例:

`measure.setLinkTrackEvents("event1, event2");`

## 方法

此節包含 Android 程式庫提供的方法清單。

**共用例項**

在呼叫測量前，您必須針對在測量程式庫上呼叫的每個方法擷取程式庫中的例項:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### 初始設定

此方法會設定所需變數，並且必須在呼叫其他方法前先行呼叫。

**configureMeasurement**:此方法用於設定啟動應用程式測量所需的兩個參數。 您必須先使用此方法在測量物件上設定 reportSuiteIDs 和 trackingServer 值，再傳送伺服器呼叫。

語法:

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

範例:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### 事件及狀態追蹤

這些是用來追蹤自訂事件和應用程式狀態的主要方法。

**trackAppState**:這是追蹤應用程式中應用程式狀態的建議方式。 appState 中提供的值會顯示為伺服器呼叫的頁面名稱變數。必須針對每次呼叫提供 appState 字串，因為此字串不會存留到下次呼叫。

隨此呼叫傳送的上下文資料會附加至 persistentContextData 中的任何值，並隨呼叫一起傳送。只有在 persistentContextData 中設定的值會保留到下次呼叫。

語法:

`void trackAppState(string AppStateName)`

範例:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**:這是追蹤應用程式中事件的建議方式。 trackEvents類似trackAppState，但會傳送事件而非頁面名稱。 事件是以逗號分隔字串的形式提供的。必須針對每次呼叫提供 events 字串，因為此字串不會存留到下次呼叫。

此方法會對trackLinkURL進行基礎呼叫，其中linkURL設定為nil、linkType設定為"o"，而linkName會填入應用程式ID。

這表示您的 linkTrackVars 和 linkTrackEvents 適用於對 trackEvents 的呼叫。

隨此呼叫傳送的上下文資料會附加至 persistentContextData 中的任何值，並隨呼叫一起傳送。只有在 persistentContextData 中設定的值會保留到下次呼叫。

語法:

`void trackEvents(string Events)`

範例:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**如果您是使用 trackLink 方法，請匯入附註**

trackEvents 會對 trackLink 進行基礎呼叫，其中 linkURL 設定為 null、linkType 設定為 "o"，而 linkName 會填入應用程式 ID。這個動作可防止頁面檢視 (狀態檢視) 計數在您每次傳送事件時增加。

如果直接呼叫 trackLink 並設定 linkTrackVars 和 linkTrackEvents 的值，這些變數和事件限制就會套用至 TrackEvents。這表示只有在這些清單上定義的變數和事件會隨 TrackEvents 一起傳送。您必須將 linkTrackVars 和 linkTrackEvents 設定為 null，除非您要將這些限制套用到 trackEvents。

### 進階追蹤 (track 和 trackLink)

這些方法提供其他追蹤選項，讓您能直接填入 props、eVars 和其他 SiteCatalyst 變數。這些變數應該要由具有現有實施的客戶或對其他 SiteCatalyst 實施十分熟悉的客戶來使用。

`track` 和 `trackLink` 是核心測量方法，會在多個平台上的所有 Adobe Measurement Library ·版本中實施。在大多數環境中追蹤行動應用程式時，使用 trackAppState、trackEvents 方法比較簡單，而非直接呼叫追蹤和 trackLink。

頁面檢視追蹤 (track) 和連結追蹤 (trackLink) 會傳送具有值 (非 null、非空白、非零) 的所有永久性變數。您必須先視需要重設或空出所有變數，然後再呼叫 track 或 trackLink。

*注意：由於現代應用程式的多執行緒性質，因此不建議設定要隨未來追蹤呼叫一起傳送的永久性變數值（使用setEvar、setProp、setHier、SetListVar和setPersistentContextData）。 例如，若變數值設定在多個執行緒中，則值在進行追蹤呼叫時可能處於不一致狀態。 若要避免這種情形，建議您與每個追蹤呼叫一起傳遞上下文資料，並在「處理規則」中設定變數值。

**方法說明**

**track**:傳送標準頁面檢視以及在測量物件上設定的任何其他變數至收集伺服器。

每個用以追蹤的呼叫會傳送所有在測量物件上定義的持久資料 (這些列於 clearVars 的說明中)，加上任何 contextData 或您專門針對該呼叫提供的變數。如果您傳送已定義的變數，則會覆寫所有對應的持久變數中的值。

語法:

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

範例:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**:傳送自訂、下載或退出連結資料至Adobe資料收集伺服器，以及任何具有值的trackconfig變數。

使用 trackLink 追蹤所有不應擷取頁面檢視的活動。

語法:

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**: 識別已點按的 URL。 若沒有指定 URL，則使用名稱。僅在從 Android 應用程式內部連結到網頁時使用它。否則，請為該參數傳入空值。

**linkType**: 識別將顯示 URL 或名稱的連結報表。支援的值包括:
* 「o」(自訂連結)
* 「d」(檔案下載)
* 「e」(退出連結)

**linkName**: 出現在連結報表中的名稱。 若沒有指定名稱，則該報表使用 URL。

若要收集資料，您必須指定 linkURL 或 linkName 參數。當不使用其中一個參數、上下文資料或其他變數時，請傳入null作為值。

範例:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**:將指定的eVar設為提供的值。 eVar 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫清除變數，藉以將其清除為止。

語法:

`void setEvar(int evarNum, String evarValue)`

**setProp**:將指定的prop設為提供的值。 prop 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫清除變數，藉以將其清除為止。

語法:

`void setProp(int propNum, String propValue)`

**setHier**:將指定的heir變數設為提供的值。 繼承變數會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫清除變數，藉以將其清除為止。

語法:

`void setHier(int hierNum, String hierValue)`

**setListVar**:將指定的listVar設為提供的值。 listVar 會與所有追蹤呼叫一起傳送，直到將其設為空字串或呼叫清除變數，藉以將其清除為止。

語法:

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**:放置在「永續性內容資料」中的值會隨每個伺服器呼叫傳送。 若要傳送單一呼叫的上下文資料，請傳送 contextData 雜湊表作為追蹤呼叫 (trackAppState、trackEvents 等等)·的參數。

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

請參閱內容資料。

**clearVars**:從對象上的以下變數中刪除值：

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

語法:

`void clearVars()`

範例:
`measure.clearVars();`

**離線追蹤**

*注意: 若要啟用離線 AppMeasurement，您的報表套裝必須已啟用時間戳記。*

下列變數讓您在應用程式離線時，儲存測量呼叫。若要啟用離線 AppMeasurement，您的報表套裝必須已啟用時間戳記。在您進行變更之後，所有的點擊都必須有時間戳記，否則會被丟棄。如果您目前是將 AppMeasurement 資料報告至也會從 JavaScript 收集資料的報告套裝，則您可能需要為離線 AppMeasurement 設定不同的報告套裝，以避免資料遺失。

啟用後，離線 AppMeasurement 會以下列方式運作:
* 應用程式會傳送伺服器呼叫，但資料傳輸會失敗。
* AppMeasurement 會生成目前點按的時間戳記。
* AppMeasurement 會緩衝處理點按資料，然後將緩衝點按資料備份至永久性儲存體以免資料丟失。

後續每次點擊時，或在 offlineThrottleDelay 定義的間隔時間中，AppMeasurement 會試圖傳送緩衝點擊資料；保持原始的點擊順序。如果資料傳輸失敗，將會繼續緩衝點擊資料 (會在裝置離線時持續進行)。

### 設定方法

**setOfflineTrackingEnabled**:預設為false。 啟用或停用測量程式庫的離線追蹤。

語法:

`void setOfflineTrackingEnabled(boolean Enabled);`

範例："measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**:預設值為1000。 儲存在佇列中的離線點擊數量上限。如果將點擊限制設為超過 5000，效能可能會受到影響。

語法:

`void setOfflineHitLimit(int offlineHitLimit)`

範例:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**:傳回離線佇列中儲存的追蹤呼叫數。

語法:

`int getTrackingQueueSize()`

範例:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**:從離線佇列移除所有儲存的追蹤呼叫。

語法:

`void clearTrackingQueue()`

範例:

`measure.clearTrackingQueue();`

**警告: 手動清除佇列時請格外小心，因為此動作無法回復。**


**setOnline和setOffline**:手動設定測量物件的線上或離線狀態。 程式庫會自動偵測裝置為離線或上線，因此只有在您要將測量強制離線時，才需要這些方法。SetOnline 只用於在手動離線後，恢復為上線狀態。

當測量為離線時:

* 如果 offlineTrackingEnabled 為 true: 會儲存點擊，直到測量上線為止。
* 如果 offlineTrackingEnabled 為 false: 會捨棄點擊。

語法:

```
void setOnline()
void setOffline()
```

範例:

```
measure.setOffline();
measure.setOnline();
```

## 離線追蹤

即使在 Android 裝置離線的情況下，AppMeasurement 仍可讓您測量應用程式的使用情形。

*注意: 若要啟用離線 AppMeasurement，您的報表套裝必須已啟用時間戳記。*

請參閱離線追蹤。

## 目標

Adobe 提供在 Android 應用程式內遞送鎖定內容的能力。

從 Test&amp;Target 傳回的內容可以是任何文字型的內容，例如 HTML、XML 或純文字。載入內容之後，則由 Android 應用程式開發人員決定如何在應用程式中使用內容。內容可以顯示成 HTML，或用來變更應用程式的行為。本指南提供 Test&amp;Target 類別的簡單使用範例。

要求

* JDK 5/6/7
* Android SDK for Platform 1.5 或更高版本。

本節中的範例以 Eclipse 為基礎。

**取得程式庫**

請造訪 Developer Connection 上的測量和最佳化行動應用程式以下載 Android 程式庫。

將下載的檔案解壓縮後，會有下列軟體元件:

* admsAppLibrary.jar: 為搭配 Android 裝置和模擬器使用而設計的程式庫。需要 Android 2.0 (含) 以上版本。
* Examples\TrackingHelper.java: 設計來將追蹤程式碼與您的應用程式邏輯分開的選用類別。

**新增程式庫至您的專案**

1. 在 Eclipse IDE 中，用滑鼠右鍵按一下專案名稱。
1. 選取「組建路徑 &gt; 新增外部封存」。
1. 選擇 admsAppLibrary.jar。
1. 按一下開啟。
1. 再次以滑鼠右鍵按一下專案，然後選取「組建路徑 &gt; 設定組建路徑」。
1. 按一下訂購及匯出標籤。
1. 確定已選擇 admsAppLibrary.jar。

您的應用程式可以使用 `importcom.adobe.ADMS.*;` .*; 從 admsAppLibrary.jar 程式庫匯入 classes/interfacesby 

**新增應用程式權限**

AppMeasurement 資料庫需要下列權限，才能傳送資料及記錄離線追蹤呼叫:

* INTERNET
* ACCESS_NETWORK_STATE

若要新增這些權限，請在您的 AndroidManifest.xml 檔案中 (在應用程式專案目錄裡) 加入下列各行:

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

範例

將程式庫新增至您的專案並新增應用程式權限之後，您可以使用兩個 Test&amp;Target 類別: MboxFactory 和 Mbox。

以下範例顯示如何在簡單 Android 應用程式中從 Test&amp;Target 將 HTML 內容載入 WebView。此範例假設已在 Test&amp;Target 管理工具中建立相關的 HTML 選件和促銷活動，而且該促銷活動已經核准。

1. 完成實施步驟，然後匯入位於「應用程式」或「活動」子類別頂端的 testandtarget 套裝:

   `com.adobe.adms.testandtarget.*;`

2. 依照下列的編號程式碼建立 mbox (每一行程式碼的說明請參閱註解)。若要完成此步驟，必須知道您的用戶端程式碼和 Test&amp;Target 管理工具中促銷活動設定裡使用的 mbox 的名稱。

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. 定義實施 MboxContentConsumer 介面的自訂類別。這個抽象介面只要求您定義要傳遞內容的目標方法，名為 “consume”。以下定義的 CustomConsumer 類別僅在 WebView 中顯示內容。

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. 用滑鼠右鍵按一下您的專案，然後選取「執行身分 &gt; Android 應用程式」以建立和測試應用程式。如果您已正確設定及核准您的 Test&amp;Target 促銷活動，在 Android 裝置模擬器中應該會顯示您的選件。

**生命週期量度**

如果已啟用生命週期度量，會將生命週期度量傳送作為每個 Mbox 負載的參數。

* (建議採用) 追蹤生命週期事件
* 生命週期量度

## 讀者管理

Adobe 可讓您透過觀眾管理傳送信號及擷取訪客區段。

### 要求

* JDK 5/6/7
* Android SDK for Platform 1.5 或更高版本。

本節中的範例以 Eclipse 為基礎。

### 取得程式庫

請造訪 Developer Connection 上的測量和最佳化行動應用程式以下載 Android 程式庫。

將下載的檔案解壓縮後，會有下列軟體元件:

* admsAppLibrary.jar: 為搭配 Android 裝置和模擬器使用而設計的程式庫。需要 Android 2.0 (含) 以上版本。
* Examples\TrackingHelper.java: 設計來將追蹤程式碼與您的應用程式邏輯分開的選用類別。

### 新增程式庫至您的專案

1. 在 Eclipse IDE 中，用滑鼠右鍵按一下專案名稱。
1. 選取「組建路徑 &gt; 新增外部封存」。
1. 選擇 admsAppLibrary.jar。
1. 按一下開啟。
1. 再次以滑鼠右鍵按一下專案，然後選取「組建路徑 &gt; 設定組建路徑」。
1. 按一下訂購及匯出標籤。
1. 確定已選擇 admsAppLibrary.jar。

您的應用程式可以使用 `importcom.adobe.ADMS.*;` .*; 從 admsAppLibrary.jar 程式庫匯入 classes/interfacesby 

### 新增應用程式權限

AppMeasurement 資料庫需要下列權限，才能傳送資料及記錄離線追蹤呼叫:
* INTERNET
* ACCESS_NETWORK_STATE

若要新增這些權限，請在您的 AndroidManifest.xml 檔案中 (在應用程式專案目錄裡) 加入下列各行:

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### 程式碼範例

將程式庫新增至您的專案之後，您可以使用 ADMS_AudienceManager 類別。To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. 設定觀眾管理:

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   將 mycompany.demdex.net 以您的端點取代。可以在應用程式的任何點中設定觀眾管理。


2. 選擇性地設定 dpid 和 dpuuid。

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. 建立特徵字典，並在信號中提交字典。

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

會在回呼中傳回訪客設定檔字典，作為 content 參數。

### 生命週期量度

如果已啟用生命週期度量，並在 application:didFinishLaunchingWithOptions: 中設定觀眾管理，在設定完成之後，會傳送包含生命週期度量的信號。

* (建議採用) 追蹤生命週期事件
* 生命週期量度

### ADMS_AudienceManager 參考

**方法**

**ConfigureAudienceManager**:設定觀眾管理端點。

語法:

`public static void ConfigureAudienceManager(String server, Context context);`

範例:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**:傳回布林值，指出Audience manager方法是否會在主控台中提供除錯記錄。

語法:

`public static boolean GetDebugLogging();`

**GetDpid**:傳回dpid。

語法:

`public static String GetDpid();`

**GetDpuuid**:傳回dpuuid。

語法:

`public static String GetDpuuid();`

**GetVisitorProfile**:在您提交訊號以擷取最近訪客資料後，可隨時呼叫此方法。

訪客設定檔包含 stuff 物件中傳回的所有索引鍵值組。

語法:

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**:啟用或停用主控台中的除錯記錄。

語法:

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**:如果已設定newDpid和newDpuuid，則會隨每個訊號傳送。

語法:

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**:在特徵字典中傳送，並在回呼中接收更新的訪客描述檔。

來自 JSON 回應的 uuid 會在內部儲存並用於所有後續的信號中。像素要求也會傳送到在 dests 物件中找到的每個 URL。

語法:

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### 介面

**方法**


**AudienceManagerCallback**

語法:

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

用於來自 SubmitSignal 呼叫中物件的介面。


## PhoneGap 外掛程式

此外掛程式可讓您從 PhoneGap 專案傳送 Android AppMeasurement 呼叫。

如需建立 PhoneGap 專案的說明，請參閱在 Android 中使用 PhoneGap 入門。

若要下載外掛程式，請參閱適用於 SiteCatalyst 的 PhoneGap iOS 和 Android 外掛程式。

### 納入外掛程式

1. 將 ADMS_plugin.java 複製到 src 資料夾中的套裝。
2. 將 ADMS_Helper.js 複製到 PhoneGap 專案的 assets/www/js 資料夾。
3. 在 res/xml 資料夾中開啟 config.xml 檔案，並在 plugins`<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />` 下建立新的子節點，以註冊新外掛程式: 

例如，如果您的套裝名稱為 com.example.phonegaptest，則您的外掛程式節點如下: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### 納入 AppMeasurement 程式庫

若要下載 AppMeasurement 程式庫，請參閱取得程式庫。

1. 將 admsAppLibrary.jar 複製到 PhoneGap 專案的 libs 資料夾。
2. 以滑鼠右鍵按一下 「libs &gt; 組建路徑 &gt; 設定組建路徑」，驗證 admsAppLibrary.jar 是否在您的組建路徑中。
3. 在「資料庫」索引標籤中，如果清單中尚未列出JAR，請按一下「新增JAR」，然後從libs資料夾選取admsAppLibrary.jar。


### 生命週期度量自動追蹤

追蹤生命週期度量需要在 PhoneGap 外部進行設定。 若要啟用「生命週期自動追蹤」，請完成「開發人員快速入門」中的實施步驟。

### 使用外掛程式

在您要使用追蹤的 html 檔案中，納入:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

完成，現在您可以進行測量呼叫了。請參閱 PhoneGap 外掛程式方法。

### 疑難排解

**我的語法正確，為什麼無法到達外掛程式中的程式碼?**

請查看您的輸出主控台中是否有下列錯誤: `java.lang.ClassNotFoundException: ADMS_plugin`

如果發生此錯誤，請確定您已執行「包含外掛程式」區段中的步驟3。

## PhoneGap 外掛程式方法

在您要使用這些方法的 html 檔案中，納入:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**設定方法**


**configureMeasurementWithReportSuiteIDsTrackingServer**:此方法用於設定啟動應用程式測量所需的兩個參數。 您必須先使用此方法在測量物件上設定 reportSuiteIDs 和 trackingServer 值，再傳送伺服器呼叫。

語法:

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

範例:

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline和setOffline**:手動設定測量物件的線上或離線狀態。 程式庫會自動偵測裝置為離線或上線，因此只有在您要將測量強制離線時，才需要這些方法。SetOnline 只用於在手動離線後，恢復為上線狀態。

當測量為離線時:

* 如果 offlineTrackingEnabled 為 true: 會儲存點擊，直到測量上線為止。
* 如果 offlineTrackingEnabled 為 false: 會捨棄點擊。

語法:

```
void setOnline();
void setOffline();
```

範例:

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**:啟用(true)或停用(false)檢視除錯資訊。 預設情況下，該變數為 false。

您不能使用變數覆蓋來覆蓋此變數。

語法:

`void setDebugLogging(bool debugLogging);`

範例:

`ADMS.setDebugLogging(true);`

### 事件和狀態追蹤方法


**trackAppState**:這是追蹤應用程式中應用程式狀態（例如頁面）的建議方式。 appState 中提供的值會顯示為伺服器呼叫的頁面名稱變數。必須針對每次呼叫提供 appState 字串，因為此字串不會存留到下次呼叫。

語法:

`void trackAppState(string stateName);`

範例:

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**:這是追蹤應用程式中應用程式狀態（例如頁面）的建議方式。 appState 中提供的值會顯示為伺服器呼叫的頁面名稱變數。必須針對每次呼叫提供 appState 字串，因為此字串不會存留到下次呼叫。

隨此呼叫傳送的上下文資料會附加至 persistentContextData 中的任何值，並隨呼叫一起傳送。只有在 persistentContextData 中設定的值會保留到下次呼叫。

語法:

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData: 具有要在上下文資料中傳送之索引鍵值配對的 JSON 物件。

範例:

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**:這是追蹤應用程式中事件的建議方式。 trackEvents類似trackAppState，但會傳送事件而非頁面名稱。 事件是以逗號分隔字串的形式提供。 必須針對每次呼叫提供 events 字串，因為此字串不會存留到下次呼叫。

此方法會對trackLinkURL進行基礎呼叫，其中linkURL設為null、linkType設為"o"，而linkName會填入應用程式ID。

這表示您的 linkTrackVars 和 linkTrackEvents 適用於對 `trackEvents` 的呼叫。

語法:

`void trackEvents(string eventNames);`

範例:

`ADMS.trackEvents("login,event2");`

**如果您是使用 trackLink 方法，請匯入附註**

`trackEvents` 會對 trackLinkURL 進行基礎呼叫，其中 linkURL 設定為 null、linkType 設定為 "o"，而 linkName 會填入應用程式 ID。 這個動作可防止頁面檢視 (狀態檢視) 計數在您每次追蹤事件時增加。

如果直接呼叫 trackLinkURL 並設定 linkTrackVars 和 linkTrackEvents 的值，這些變數和事件限制就會套用至 TrackEvents。 這表示只有在這些清單上定義的變數和事件會隨 TrackEvents 一起傳送。您必須將 linkTrackVars 和 linkTrackEvents 設定為 null，除非您要將這些限制套用到 trackEvents。

**trackEventsWithContextData**:這是追蹤應用程式中事件的建議方式。 trackEvents類似trackAppState，但會傳送事件而非頁面名稱。 事件是以逗號分隔字串的形式提供的。必須針對每次呼叫提供 events 字串，因為此字串不會存留到下次呼叫。

此方法會對 trackLinkURL 進行基礎呼叫，其中 linkURL 設定為 null、linkType 設定為 "o"，而 linkName 會填入應用程式 ID。

這表示您的 linkTrackVars 和 linkTrackEvents 適用於對 trackEvents 的呼叫。

隨此呼叫傳送的上下文資料會附加至 persistentContextData 中的任何值，並隨呼叫一起傳送。只有在 persistentContextData 中設定的值會保留到下次呼叫。

語法:

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData: 具有要在上下文資料中傳送之索引鍵值配對的 JSON 物件。

範例:

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**如果您是使用 trackLink 方法，請匯入附註**

trackEvents 會對 trackLinkURL 進行基礎呼叫，其中 linkURL 設定為 null、linkType 設定為 "o"，而 linkName 會填入應用程式 ID。 這個動作可防止頁面檢視 (狀態檢視) 計數在您每次追蹤事件時增加。

如果直接呼叫 trackLinkURL 並設定 linkTrackVars 和 linkTrackEvents 的值，這些變數和事件限制就會套用至 TrackEvents。 這表示只有在這些清單上定義的變數和事件會隨 TrackEvents 一起傳送。您必須將 linkTrackVars 和 linkTrackEvents 設定為 null，除非您要將這些限制套用到 trackEvents。

**進階追蹤方法（track和trackLink）**

這些方法提供其他追蹤選項，讓您能直接填入 props、eVars 和其他 SiteCatalyst 變數。這些變數應該要由具有現有實施的客戶或對其他 SiteCatalyst 實施十分熟悉的客戶來使用。

`track` 和 `trackLink` 是核心測量方法，會在多個平台上的所有 Adobe Measurement Library ·版本中實施。在大多數環境中追蹤行動應用程式時，使用 trackAppState、trackEvents 方法比較簡單，而非直接呼叫追蹤和 trackLink。

頁面檢視追蹤 (track) 和連結追蹤 (trackLink) 會傳送具有值 (非 null、非空白、非零) 的所有永久性變數。您必須先視需要重設或空出所有變數，然後再呼叫 track 或 trackLink。

**方法**

**track**:傳送標準頁面檢視以及在測量物件上設定的任何其他變數至收集伺服器。

語法:

`void track();`

範例:

`ADMS.track();`

**trackWithContextData**:傳送標準頁面檢視以及在測量物件上設定的任何其他變數至收集伺服器。

每個對 trackWithContextData 的呼叫會傳送所有在測量物件上定義的持久資料 (這些列於 clearVars 的說明中)，加上您專門針對該呼叫提供的任何 contextData。

語法:

`void trackWithContextData(JSON cData);`

cData: 具有要在上下文資料中傳送之索引鍵值配對的 JSON 物件。

範例:

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**:傳送標準頁面檢視以及在測量物件上設定的任何其他變數至收集伺服器。

每個對 trackWithContextDataAndVariables 的呼叫會傳送所有在測量物件上定義的持久資料 (這些列於 clearVars 的說明中)，加上您專門針對該呼叫提供的任何 contextData 和變數。如果您傳送已定義的變數，則會覆寫所有對應的持久變數中的值。

語法:

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData: 具有要在上下文資料中傳送之索引鍵值配對的 JSON 物件。

範例:

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**:傳送自訂、下載或退出連結資料至Adobe資料收集伺服器，以及任何具有值的追蹤設定變數。

使用 trackLink 追蹤所有不應擷取頁面檢視的活動。

每個對 trackLinkURLWithLinkTypeNameContextDataVariables 的呼叫會傳送所有在測量物件上定義的持久資料 (這些列於 clearVars 的說明中)，加上您專門針對該呼叫提供的任何 contextData。

語法:

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData: 具有要在上下文資料中傳送之索引鍵值配對的 JSON 物件。

範例:

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### 設定並取得 AppMeasurement 變數

**方法**

**setEvarToValue**:將指定的eVar設為提供的值。 eVar 會隨下次追蹤呼叫傳送。

語法:

`void setEvarToValue(int evar, string value);`

範例:

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**:將指定的prop設為提供的值。 prop 會隨下次追蹤呼叫傳送。

語法:

void setPropToValue（int prop，字串值）;

範例:

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**:將指定的hier變數設為提供的值。 變數會隨下次追蹤呼叫傳送。

語法:

`void setHierToValue(int hier, string value);`

範例:

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**:將指定的listvar設為提供的值。 listvar 會隨下次追蹤呼叫傳送。

語法:

`void setListVarToValue(int list, string value);`

範例:

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**:取得指定的變數。

語法:

`void getEvar(int evar, function success, function fail);`

範例:

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**:取得指定的變數。

語法:

`void getProp(int prop, function success, function fail);`

範例:

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**:取得指定的變數。

語法:

`void getHier(int hier, function success, function fail);`

範例:

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**:取得指定的變數。

語法:

`void getListVar(int list, function success, function fail);`

範例:

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**:從對象上的以下變數中刪除值：

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

語法:

`void clearVars();`

範例:

`ADMS.clearVars();`

**trackingQueueSize**:取得或設定離線佇列中儲存的追蹤呼叫數。

語法:

`void trackingQueueSize(function success, function fail);`

範例:

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**:從離線佇列移除所有儲存的追蹤呼叫。 警告: 手動清除佇列時請格外小心，因為此動作無法回復。

語法:

`void clearTrackingQueue();`

範例:

`ADMS.clearTrackingQueue();`

### 設定並取得組態變數

**方法**

**getVersion**:取得程式庫版本。

語法:

`void getVersion(function success, function fail);`

範例:

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**:（必要）您要追蹤的報表套裝或報表套裝（多套裝標籤）。 若要追蹤多個報表套裝，請傳遞每個報表套裝名稱的逗號分隔清單。

您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:
`void setReportSuiteIDs(string reportSuiteIDs);`

範例:

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**:（必要）識別收集伺服器。

此變數應填入在「程式碼管理員」中產生的值。

如果啟用了 SSL，會使用相同的值來保護追蹤。

您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

`void setTrackingServer(string trackingServer);`

範例:

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

語法:

`void setDataCenter(string dataCenter);`

範例:

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**:預設值為CFUUID。

每位訪客的唯一識別碼。如果您未設定自訂 visitorID，會在初始啟動時產生唯一的 visitorID (使用 Apple 的 CFUUID)，然後儲存在使用者預設金鑰中。此後 AppMeasurement 和 PhoneGap 就會沿用此金鑰。標準應用程式進行備用程序時，也會儲存及還原該金鑰。

語法:

`void setVisitorID(string visitorId);`

範例:

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**:預設值為UTF-8。

語法:

`void setCharSet(string charSet);`

範例:

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**:預設值為無（使用為報表套裝定義的值）。

用於購買或貨幣事件的貨幣代碼，這些事件在 iOS 應用程式中得到追蹤。

語法:

`void setCurrencyCode(string currencyCode);`

範例:

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**:預設為false。

啟用 (true) 或停用 (false) 經由 SSL (HTTPS) 傳送測量資料。您不能覆蓋此變數的單一呼叫，必須變更永久值。

語法:

`void setSSLEnabled(bool sslEnabled);`

範例:

`ADMS.setSSLEnabled(false);`

### 設定並取得永久追蹤變數

**方法**

**setPurchaseID**:

語法:

`void setPurchaseID(string purchaseId);`

範例:

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

語法:

`void setTransactionID(string transactionId);`

範例:

`ADMS.setTransactionID("transaction1");`

**setAppState**:

語法:

`void setAppState(string stateName);`

範例:

`ADMS.setAppState("myAppState");`

**setChannel**:

語法:

`void setChannel(string channel);`

範例:

`ADMS.setChannel("myChannel");`

**setAppSection**:

語法:

`void setAppSection(string appSection);`

範例:

`DMS.setAppSection("myAppSection");`

**setCampaign**:

語法:

`void setCampaign(string campaign);`

範例:

`ADMS.setCampaign("myCampaign");`

**setProducts**:

語法:

`void setProducts(string products);`

範例:

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

語法:

`void setEvents(string events);`

範例:

`ADMS.setEvents("event1, event2");`

**setGeoState**

語法:

`void setGeoState(string state);`

範例:

`ADMS.setGeoState("FL");`

**setGeoZip**:

語法:

`void setGeoZip(string zip);`

範例:

`ADMS.setGeoZip("39984");`

**setPersistentContextData**:上下文資料是收集資料的建議方式。 若要傳送上下文資料，請建立一個 JSON 物件，並為您要傳送的值指派索引鍵值配對。

語法:

`void setPersistentContextData(JSON cData);`

範例:

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

語法:

`void persistentContextData(function success, function fail);`

範例:

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**:逗號分隔的變數名稱清單，限制目前的連結追蹤變數集。

如果未定義 linkTrackVars，PhoneGap 外掛程式會以 trackLink 呼叫傳送所有已定義的變數。

語法:

`void setLinkTrackVars(string linkTrackVars);`

範例:

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**:逗號分隔的事件清單，限制目前的連結追蹤事件集。 如果未定義 linkTrackEvents，PhoneGap 外掛程式會以 trackLink 呼叫傳送所有事件。

語法:

`void setLinkTrackEvents(string linkTrackEvents);`

範例:

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**:以逗號分隔的變數清單，可限制光追蹤呼叫的目前變數集。 您隨輕伺服器呼叫傳送的變數由 ClientCare 設定。

語法:

`void setLightTrackVars(string lightTrackVars);`

範例:

`ADMS.setLightTrackVars("prop1,hier3");`

### 離線追蹤

**方法**

**setOfflineTrackingEnabled**:

語法:

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

範例:

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

語法:

`void setOfflineHitLimit(int offlineHitLimit);`

範例:

`ADMS.setOfflineHitLimit(3000);`

## Androidx 2.x 至 3.x 版遷移指南

* AppMeasurement 現在稱為 ADMS_Measurement。 尋找您參考此類別的位置，並將名稱更新為 ADMS_Measurement。
* getInstance 現在稱為 sharedInstance。尋找您呼叫 getInstance 的位置，並以 sharedInstance 進行取代。
* 移除對混合測量的所有呼叫 (getChurnInstance)。這些呼叫已由自動追蹤處理，而現在是使用上下文資料插入變數。
* Timestamp 已經移除。程式庫會自動處理時間戳記。

下列方法的語法已經變更。所有屬性和方法的更新後範例均可在下列位置取得:  設定變數和方法。


### 報表套裝

**舊版本 (2.1.x)**

`account`

**新版本 (3.x)**

`reportSuiteIDs`

### Track

**舊版本 (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**新版本 (3.x)**

針對未使用的值傳遞 null。

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### 追蹤連結

**舊版本 (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**新版本 (3.x)**

這兩個呼叫已換成單一呼叫。針對未使用的值傳遞 null。

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### 離線追蹤方法

**舊版本 (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**新版本 (3.x)**

`void setOnline();`

`void setOffline();`


### 已重新命名的變數

以下清單顯示 2.x 版變數與其在 3.x 版中的對應值。已從 3.x 版移除數個變數，讓程式庫更具行動性並簡化實施方式。


*注意: 3.x 版使用 getter 與 setter，而非公用變數。您必須更新程式碼中您設定變數直接使用 get 和 set 方法的位置。*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## 使用 Bloodhound 測試行動應用程式

Bloodhound 工具可讓您傳送伺服器呼叫至本機電腦，用以測試行動應用程式。

*重要: Adobe Bloodhound 已於 2017 年 4 月 30 日起停止服務。自 2017 年 5 月 1 日起，不再提供額外的增強功能、額外工程支援，或 Adobe Expert Care 支援。*

在應用程式開發期間，Bloodhound 可讓您在本機檢視伺服器呼叫，以及選擇將資料轉送至 Adobe 收集伺服器。

Bloodhound 適用於 Mac 和 Windows。

### 要求

* 執行 Snow Leopard (10.6) 或更高版本的 Intel 型 Mac 電腦，或 Windows PC。
* 可連至行動裝置或模擬器的網路連線。

### 下載

請參閱 Developer Connection 上的 Bloodhound - App Measurement QA 工具。

### 安裝

* Mac: 開啟您所下載的 dmg，並將 Bloodhound 拖曳至 Applications 資料夾。
* Windows: 執行您所下載的安裝檔案。

### 使用 Bloodhound

啟動工具後，伺服器會停用，直到您按下「啟動」按鈕。當您準備要從應用程式擷取伺服器呼叫時，請按一下「啟動」按鈕。

或者，您可以在啟動伺服器前，指定自訂連接埠號碼 (必須高於 1024)。若未提供連接埠號碼，伺服器會自動選取開啟的連接埠。

在伺服器執行之後，您必須如下一節所述設定應用程式或裝置，將資料傳送給工具。

### 設定裝置以將點擊傳送給 Bloodhound

您可以變更裝置上的 Proxy 設定，傳送 http 要求給工具。傳送給工具的要求可以視需要選擇轉送至 Adobe 資料蒐集伺服器。

如果裝置不支援 Proxy，您可以將點擊直接傳送到 Bloodhound 進行測試。

*注意: Bloodhound 不支援 SSL 追蹤。 使用 Bloodhound 進行測試時，您必須停用 AppMeasurement 程式庫中的 SSL。*

#### iOS 裝置

iOS 裝置必須位於主控 Bloodhound 之電腦的相同網路上。

1. 導覽至「設定 &gt; Wi-Fi」。
1. 按一下目前 Wi-Fi 網路右邊的藍色箭頭。
1. 捲動至 HTTP Proxy 設定。
1. 選取「自動」。
1. 在 URL 欄位中輸入 Proxy URL 和連接埠 (來自 Bloodhound UI)。

#### 其他裝置

如果裝置支援 Proxy 自動設定，只需使用 Proxy URL (來自 Bloodhound UI) 作為 Proxy 自動設定 (PAC) URL。Proxy 支援能力依 Android 版本而異，市面上也有一些適用於 Android 的 Proxy 設定工具，可以用來簡化設定。

### 直接傳送點擊

若為不支援 Proxy 的裝置 (iOS Simulator、較舊的 Android 版本等)，即不可能指定 Bloodhound 作為追蹤伺服器以便擷取它所產生的點擊。若要這麼做，請將追蹤伺服器設為 "<Bloodhound IP>:<BloodhoundPort>".

例如:

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### 疑難排解/常見問題

* Bloodhound 僅適用於非 SSL 追蹤。不論以上使用的方法為何，都不會擷取任何透過 SSL 傳送的追蹤點擊。

## Android 介面工具集

可以使用與您的應用程式相同的方法追蹤 Android 介面工具集。介面工具集會與您的應用程式共用應用程式內容，因此會保留點擊順序和訪客識別。

下列指引將協助您追蹤 Android 介面工具集:

* 請勿在介面工具集本身實施生命週期度量 (startActivity/stopActivity) 呼叫。
* 若要追蹤介面將工具集新增至主畫面的時間，請新增 trackState 或 trackEvent 呼叫至介面工具集的 onEnabled 方法。
* 若要追蹤從介面工具集新增應用程式的時間，請在建立啟動應用程式的目的之前，新增 trackState 或 trackEvent 呼叫。
* 如果您有興趣追蹤動作的上下文，您可以定義一個 ContextData 變數，其提供將各項個別劃分的選項 (例如，AppExperienceType="widget" 與 "app")。
