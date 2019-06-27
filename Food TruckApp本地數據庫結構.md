## albums

相簿表：記錄相簿的信息

| 字段名 |  數據類型    | 可否爲空（Y/N）    | 注釋     |
| :---- |:---- | :-- | :-- |
| id | int | N | 相簿的id，主鍵 |
| event_id | int | N | 盛事的id（關聯到events中的id） |
|name_en|varchar|N|相簿名字(EN)|
|name_tc|varchar|N|相簿名字(TC)|
|name_sc|varchar|N|相簿名字(SC)|
| coverphoto_en | varchar | N | 相簿的圖標圖片url（（EN） |
| coverphoto_tc | varchar | N | 相簿的圖標圖片的url（TC） |
| coverphoto_sc | varchar | N | 相簿的圖標圖片的url（SC） |

## photo
相片：存儲相簿中的照片
| 字段名 |  數據類型    | 可否爲空（Y/N）    | 注釋     |
| :---- |:---- | :-- | :-- |
|photo_id|varchar|N|相簿中的圖片id|
|photo_url|varchar|N|相簿中的圖片地址|
|caption_en|varchar|N|位於照片下方的標題（EN）|
|caption_tc|varchar|N|位於照片下方的標題（TC）|
|caption_sc|varchar|N|位於照片下方的標題（SC）|
|alt_en|varchar|N|照片的文字替代(EN)（方便屏幕閲讀器檢測）|
|alt_tc|varchar|N|照片的文字替代(TC)（方便屏幕閲讀器檢測）|
|alt_sc|varchar|N|照片的文字替代(SC)（方便屏幕閲讀器檢測）|
|last_update|DATETIME|N|最後跟新日期|

## push_alerts

警告表：記錄發出的警告信息

| 字段名 | 數據類型     | 可否爲空（Y/N）    |注釋      |
| :---- | :-- | :-- | :-- |
|id|Int|N|id號，主鍵|
| alert_en | String | N | 警告信息（EN） |
| alert_tc | String | N | 警告信息（TC） |
| alert_sc | String | N | 警告信息（SC） |
|last_update|DATETIME|N|最後跟新日期|
## operating_schedules

行事日曆表：記錄日期信息

| 字段名 |  數據類型     | 可否爲空（Y/N）    |注釋      |
| :-- | :-- | :-- | :-- |
|id|int|N|id，主鍵|
|food_truck_id|int|N|美食車的id（關聯到food_trucks表中的id）|
|shift|varchar|Y|晝夜更替<br> "morning" —> the foodtruck work on morning<br/>"night" —> the foodtruck work on night<br/> "full_day" —> the foodtruck work on full day|
|  date    |  datetime    | N | 日期  格式：YYYY-MM-DD |
| business_hours_describe_en | varchar | N | 描述營業時間信息（EN） |
| business_hours_describe_tc | varchar | N | 描述營業時間信息（TC） |
|business_hours_describe_sc|varchar|N|描述營業時間信息（SC）|
|event_id|int|N|盛事id(關聯到events表的id)|
|operating_location_id|int|N|ID of operating location 運營地點的ID(關聯到locations表的id)|
|english_version|float|N|版本號信息（英文）|
|traditional_chinese version|float|N|版本號信息（TC）|
|simplified_chinese_version|float|N|版本號信息（SC）|
|last_update|DATETIME|N|更新時間|

##   signature_dishs
招牌菜式表：記錄菜式的信息
|字段名|數據類型|可否爲空（Y/N）|注釋 |
|:--|:--|:--|:--|
|id|int|N|美食車招牌菜id，主鍵|
|food_truck_id|int|N|美食車id（關聯到food_trucks表中的id）|
|name_en|varchar|N|美食车的招牌菜式名字(EN)|
|name_tc|varchar|N|美食车的招牌菜式名字（TC）|
|name_sc|varchar|N|美食车的招牌菜式名字（SC）|
|company_en|varchar|N|公司名（EN）|
|company_tc|varchar|N|公司名（TC）|
|company_sc |varchar|N|公司名（SC）|
|photo_en|varchar|N|文字圖片的url(EN)|
|photo_tc|varchar|N|文字圖片的url(TC)|
|photo_sc|varchar|N|文字圖片的url(SC)|
|last_update|DATETIME|N|最後更新時間|

## events
盛事信息表：記錄盛事信息

|      字段名|數據類型      |可否爲空（Y/N）      | 注釋     |
| :-- | :-- | :-- | :-- |
| id | int |    N  | 盛事id，主鍵 |
| is_new | bool |    N  | 提醒此爲新的盛事:<br>**1** 代表新内容 <br>**0** 代表沒有新内容 |
| latitude | float |     N | Latitude 緯度 |
|longitude|float|N|longitude 經度|
|name_en|varchar|N|盛事名字（EN）|
|name_tc|varchar|N|盛事名字（TC）|
|name_sc|varchar|N|盛事名字（SC）|
|location_en|varchar|N|位置信息（EN）|
|location_tc|varchar|N|位置信息（TC）|
|location_sc|varchar|N|位置信息（SC）|
|describe_en|varchar|N|活動開放時間日期（EN）|
|describe_tc|varchar|N|活動開放時間日期（TC）|
|describe_sc|varchar|N|活動開放時間日期（SC）|
|download_map_en|varchar|N|下載地圖（EN）|
|download_map_tc|varchar|N|下載地圖（TC）|
|download_map_sc|varchar|N|下載地圖（SC）|
|photo_en|varchar|N|活動主題圖片的url（EN）|
|photo_tc|varchar|N|活動主題圖片的url（TC）|
|photo_sc|varchar|N|活動主題圖片的url（SC）|
|about_en|varchar|N|活動簡介（EN）|
|about_tc|varchar|N|活動簡介（TC）|
|about_sc|varchar|N|活動簡介（SC）|
|logo_en|varchar|N|logo圖片的url（EN）|
|logo_tc|varchar|N|logo圖片的url（TC）|
|logo_sc|varchar|N|logo圖片的url（SC）|
|last_update|DATETIME|N|最後更新時間|

## food_trucks

美食車表：記錄美食車的信息

| 字段名 |數據類型      |可否爲空（Y/N）      | 注釋     |
| :---------- | :-- | :-- | :-- |
| id           | int | N | 美食車id，主鍵 |
| is_new | bool |   N   | 提醒有新的美食車提供服務:<br>1 :新内容<br>0:沒有新内容 |
| company_en | varchar |  N    | 公司名字（EN） |
|company_tc|varchar|N|公司名字（TC）|
|company_sc|varchar|N|公司名字（SC）|
|signature_dish_en|varchar|N|美食车的招牌菜式（EN）|
|signature_dish_tc|varchar|N|美食车的招牌菜式（TC）|
|signature_dish_sc|varchar|N|美食车的招牌菜式（SC）|
|photo_en|varchar|N|美食車封面圖的url（EN）|
|photo_tc|varchar|N|美食車封面圖的url（TC）|
|photo_sc|varchar|N|美食車封面圖的url（SC）|
|about_en|varchar|N|美食車簡介（EN）|
|about_tc|varchar|N|美食車簡介（TC）|
|about_sc|varchar|N|美食車簡介（SC）|
|menu_url_en|varchar|N|美食車菜單（EN）|
|menu_url_tc|varchar|N|美食車菜單（SC）|
|menu_url_sc|varchar|N|美食車菜單（TC）|
|twitter_url_en|varchar|N|twitter_url（EN）|
|twitter_url_tc|varchar|N|twitter_url（SC）|
|twitter_url_sc|varchar|N|twitter_url（TC）|
|facebook_url_en|varchar|N|facebook_url（EN）|
|facebook_url_tc|varchar|N|facebook_url（SC）|
|facebook_url_sc|varchar|N|facebook_url（TC）|
|logo_en|varchar|N|logo圖片的url（EN）|
|logo_tc|varchar|N|logo圖片的url（SC）|
|logo_sc|varchar|N|logo圖片的url（TC）|
|last_update|DATETIME|N|最後更新時間|

## operating_locations

位置信息表：記錄位置信息

| 字段名字 | 數據類型 | 可否爲空（Y/N） |注釋      |
| :------ | :------ | :------------- | :-- |
| id | int | N |ID of operating location 運營地點的ID，主鍵 |
|  is_new     | bool |                 N| 提醒有新的區域可以有美食車服務:<br> 1 :新内容 <br>0:沒有新内容 |
|     latitude     | float |                 N| Latitude 緯度 |
|longitude|float|N|longitude 經度|
|name_en|varchar|N|運營地點名字（EN）|
|name_tc|varchar|N|運營地點名字（TC）|
|name_sc|varchar|N|運營地點名字（SC）|
|download_map_en|varchar|N|離綫地圖的url（EN）|
|download_map_tc|varchar|N|離綫地圖的url（TC）|
|download_map_sc|varchar|N|離綫地圖的url（TC）|
|photo_en|varchar|N|運營圖片的url（EN）|
|photo_tc|varchar|N|運營圖片的url（TC）|
|photo_sc|varchar|N|運營圖片的url（SC）|
|about_en|varchar|N|運營介紹的html（EN）|
|about_tc|varchar|N|運營介紹的html（TC）|
|about_sc|varchar|N|運營介紹的html（SC）|
|logo_en|varchar|N|logo圖片的url（EN）|
|logo_tc|varchar|N|logo圖片的url（TC）|
|logo_sc|varchar|N|logo圖片的url（SC）|
|last_update|DATETIME|N|最後更新的時間|
## static_pages

頁面信息表:用於存放頁面信息

|字段名字 |  數據類型   |  可否爲空（Y/N）  | 注釋   |
| :--- | :-- | :-- | :-- |
|id|int|N|id，主鍵|
|photo_en|varchar|N|宣傳照片的url（EN）|
|photo_tc|varchar|N|宣傳照片的url（TC）|
|photo_sc|varchar|N|宣傳照片的url（SC）|
|travelling_HK_photo_en|varchar|N|"Travel in Hong Kong"的照片urlurl（TC）|
|travelling_HK_photo_tc|varchar|N|"Travel in Hong Kong"的照片url（SC）|
|travelling_HK_photo_sc|varchar|N|"Travel in Hong Kong"的照片url（EN）|
|travelling_HK_url_en|varchar|N|"Travel in Hong Kong"的html（EN）|
|travelling_HK_url_tc|varchar|N|"Travel in Hong Kong"的html（TC）|
|travelling_HK_url_sc|varchar|N|"Travel in Hong Kong"的html（SC）|
|privacy_policy_en|varchar|N|"Privacy Policy"的html（EN）|
|privacy_policy_tc|varchar|N|"Privacy Policy"的html（TC）|
|privacy_policy_sc|varchar|N|"Privacy Policy"的html（SC）|
|disclaimer_en|varchar|N|"Disclaimer"的html（EN）|
|disclaimer_tc|varchar|N|"Disclaimer"的html（TC）|
|disclaimer_sc|varchar|N|"Disclaimer"的html（SC）|
|about_us_url_en|varchar|N|“The Birth of 16 FoodTrucks”的html(EN)|
|about_us_url_tc|varchar|N|“The Birth of 16 FoodTrucks”的html(TC)|
|about_us_url_sc|varchar|N|“The Birth of 16 FoodTrucks”的html(SC)|
|last_update|DATETIME|N|最後更新的時間|

## local_date_versions
版本信息表：記錄本地數據版本號

|字段名字 |  數據類型   |  可否爲空（Y/N）  | 注釋   |
| :-- | :-- | :-- | :-- |
|id|int|N|id，主鍵|
|calendar_version|DATETIME|N|日曆版本號|
|food_truck_version|DATETIME|N|美食車版本號|
|location_version|DATETIME|N|位置信息版本號|
|event_version|DATETIME|N|盛事信息版本號|
|album_version|DATETIME|N|照片信息版本號|
|page_version|DATETIME|N|頁面信息版本號|
|pushalert_version|DATETIME|N|警告信息版本號|
|signature_dish_version|DATETIME|N|美食車招牌菜版本號|
|last_update|DATETIME|N|最後更新的時間|

