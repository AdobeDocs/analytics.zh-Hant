---
description: 'null'
seo-description: 'null'
seo-title: 標籤範例
title: 標籤範例
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: d2134271c4586d629c8b25f60c746902ba13683b

---


# 標籤範例

## 範例點擊資料

假設您有以下點擊資料:

* 第一行含有每個變數的標籤。
* 第二行是變數的名稱。如果變數具有 ID 標籤，則會在括號中包含指派的命名空間。
* 第三行之後是點擊資料。

| 標籤 | I2<br>ID-<br>PERSONDEL-<br>PERSONACC-PERSON | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL | I2<br>DEL-<br>PERSONACC-PERSON | I2<br>DEL-<br>DEVICEDEL-<br>PERSONACC-ALL | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL |
|---|---|---|---|---|---|
| **變數名稱**<br>**（命名空間）** | **MyProp1**<br>**（使用者）** | **訪客ID**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| 點擊資料 | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## 範例存取請求

如果我提交存取請求，摘要檔案將會含有下表指出的值。請求可能只會傳回一個裝置檔案、一個人員檔案，或是每種檔案各一。唯有使用人員 ID 且 expandIds 設為 true 時，系統才會傳回兩個摘要檔案。

| API 值 | API 值 | 傳回的檔案類型 | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **命名空間/ID** | **expandIDs** |  | **MyProp1** | **訪客 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | 裝置 | 變數不存在 | 77 | 變數不存在 | M、P | X、W |
| AAID=77 | true | 裝置 | 變數不存在 | 77 | 變數不存在 | M、P | X、W |
| user=Mary | false | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | 裝置 | 不存在 | 77、88 | 不存在 | N、P | U、W |
| user=Mary AAID=66 | true | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary AAID=66 | true | 裝置 | 不存在 | 66、77、88 | 不存在 | N、P | U、W、Z |
| xyz=X | false | 裝置 | 不存在 | 55、77 | 不存在 | M、R | X |
| xyz=X | true | 裝置 | 不存在 | 55、77 | 不存在 | M、P、R | W、X |

請注意，使用 cookie ID 時，expandIDs 的設定不會影響輸出。

## 範例刪除請求

將使用 API 值的刪除請求列示在表格的第一行，點擊表格的內容將會更新並看起來像這樣:

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] 只有包含AAID = 77和DEL-DEVICE標籤的列上的儲存格會受到影響。

| user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] 只有包含user=Mary和DEL-PERSON標籤的行上的儲存格才會受到影響。 此外，在實務中，包含A_ID的變數可能是prop或eVar，其取代值會是以"Privacy-"開頭的字串，後面接著隨機數字(GUID)，而不是以不同的隨機數值取代數值。

| user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

請注意下列事項：

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2`第四和第五行的 會更新，因為這些兩行包含的 Visitor ID 值與第一和第二行的值相同，因此 ID 擴增會將其納入裝置層級的刪除作業。
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` 其行為與未進行ID擴增時截然不同，因為沒有ID擴增時，就不 `ID-DEVICES` 匹配。 Now `AAID` matches on the first five rows.
