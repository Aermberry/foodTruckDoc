# 相冊照片

## albums

相冊記錄表：記錄相冊信息

| 字段名 |  數據類型    | 是否爲空（Y/N）     | 注釋     |
| ------ | ---- | ---- | ---- |
| album_id | int | N | 相冊的id |
| event_id | int | N | 盛事的id|
|name|varchar|N|相冊名字|
| coverphoto | varchar | N | 封面照片的url地址 |



## album_photos
照片記錄表：記錄各個相冊中的照片信息

| 字段名 | 數據類型 | 是否爲空（Y/N） |    注釋    |
| :----: | :------: | :-------------: | :--------: |
|  url   | varchar  |        N        | 美食車照片鏈接 |
|caption_en|varchar|N|標題（EN）|
|caption_tc|varchar|N|標題（TC）|
|caption_sc|varchar|N|標題（SC）|
|photo_id|int|N|圖片的id|
|album_id|int|N|相冊的id|

## warning_text

警告記錄表：記錄發出的警告信息

| 字段名 | 數據類型     | 是否爲空（Y/N）     |注釋      |
| ------ | ---- | ---- | ---- |
|ID|Int|N|id號|
| alert_en | String | N | 警告信息（EN） |
| alert_tc | String | N | 警告信息（TC） |
| alert_sc | String | N | 警告信息（SC） |
|lastUpdate|DATETIME|N|最後跟新日期|
## calendar

日期記錄表：記錄日期信息

| 字段名 |  數據類型     | 是否爲空（Y/N）     |注釋      |
| ---- | ---- | ---- | ---- |
|FoodTruck_id|int|N|美食車的id|
|  date    |  datetime    | N | 日期  格式：YYYY-MM-DD |
| Business_hours_describe_en | varchar | N | 描述營業時間信息（EN） |
| describe_tc | varchar | N | 描述營業時間信息（TC） |
|describe_sc|varchar|N|描述營業時間信息（SC）|
|Event_id|int|N|盛事事件id|
|olid|int|N|ID of operating location 經營地點的ID|
|English version|float|N|版本號信息（英文）|
|Traditional Chinese version|float|N|版本號信息（TC）|
|Simplified Chinese version|float|N|版本號信息（SC）|

## dishes
菜式記錄表：記錄菜式的信息
|字段名|數據類型|是否爲空（Y/N）|注釋 |
|----|----|----|----|
|sdid|int|N|菜式id|
|foodTrack_id|int|N|美食車id|
|name_en|varchar|N|菜式名字(EN)|
|name_tc|varchar|N|菜式名字（TC）|
|name_sc|varchar|N|菜式名字（SC）|
|company_en|varchar|N|公司名（EN）|
|company_tc|varchar|N|公司名（TC）|
|company_sc |varchar|N|公司名（SC）|
|photo_en|varchar|N|文字圖片(EN)|
|photo_tc|varchar|N|文字圖片(TC)|
|photo_sc|varchar|N|文字圖片(SC)|

## event
盛事信息記錄表：記錄盛事活動信息

|      字段名|數據類型      |是否爲空（Y/N）      | 注釋     |
| ---- | ---- | ---- | ---- |
| event_id | int |    N  | 盛事活動id |
| new | bool |    N  | 提醒此爲新的盛事活動1 —新内容 0---沒有新内容 |
| lat | float |     N | Latitude 緯度 |
|long|float|N|longitude 經度|
|name_en|varchar|N|盛事活動名字（EN）|
|name_tc|varchar|N|盛事活動名字（TC）|
|name_sc|varchar|N|盛事活動名字（SC）|
|location_en|varchar|N|位置信息（EN）|
|location_tc|varchar|N|位置信息（TC）|
|location_sc|varchar|N|位置信息（SC）|
|describe_en|varchar|N|活動開放時間日期（EN）|
|describe_tc|varchar|N|活動開放時間日期（TC）|
|describe_sc|varchar|N|活動開放時間日期（SC）|
|downloadmap_en|varchar|N|下載地圖（EN）|
|downloadmap_tc|varchar|N|下載地圖（TC）|
|downloadmap_sc|varchar|N|下載地圖（SC）|
|photo_en|varchar|N|活動主題圖片（EN）|
|photo_tc|varchar|N|活動主題圖片（TC）|
|photo_sc|varchar|N|活動主題圖片（SC）|
|about_en|varchar|N|活動簡介（EN）|
|about_tc|varchar|N|活動簡介（TC）|
|about_sc|varchar|N|活動簡介（SC）|
|logo_en|varchar|N|logo圖片（EN）|
|logo_tc|varchar|N|logo圖片（TC）|
|logo_sc|varchar|N|logo圖片（SC）|

## foodTruck

美食車記錄表：記錄美食車的信息

| 字段名 |數據類型      |是否爲空（Y/N）      | 注釋     |
| ------------ | ---- | ---- | ---- |
| foodTruck_id             | int | N | 美食車id |
| new | bool |   N   | 提醒有新的美食車提供服務1 —新内容 0---沒有新内容 |
| company_en | varchar |  N    | 公司名字（EN） |
|company_tc|varchar|N|公司名字（TC）|
|company_sc|varchar|N|公司名字（SC）|
|dishes_en|varchar|N|菜式（EN）|
|dishes_tc|varchar|N|菜式（TC）|
|dishes_sc|varchar|N|菜式（SC）|
|photo_en|varchar|N|美食車封面圖（EN）|
|photo_tc|varchar|N|美食車封面圖（TC）|
|photo_sc|varchar|N|美食車封面圖（SC）|
|about_en|varchar|N|美食車簡介（EN）|
|about_tc|varchar|N|美食車簡介（TC）|
|about_sc|varchar|N|美食車簡介（SC）|
|menuURL_en|varchar|N|美食車菜單（EN）|
|menuURL_tc|varchar|N|美食車菜單（SC）|
|menuURL_sc|varchar|N|美食車菜單（TC）|
|twitterURL_en|varchar|N|twitter外鏈（EN）|
|twitterURL_tc|varchar|N|twitter外鏈（SC）|
|twitterURL_sc|varchar|N|twitter外鏈（TC）|
|facebookURL_en|varchar|N|facebook外鏈（EN）|
|facebookURL_tc|varchar|N|facebook外鏈（SC）|
|facebookURL_sc|varchar|N|facebook外鏈（TC）|
|instagramURL_en|varchar|N|instagram外聯（EN）|
|instagramURL_tc|varchar|N|instagram外聯（SC）|
|instagramURL_sc|varchar|N|instagram外聯（TC）|
|logo_en|varchar|N|logo圖片（EN）|
|logo_tc|varchar|N|logo圖片（SC）|
|logo_sc|varchar|N|logo圖片（TC）|
|lastUpdate|DATETIME|N|最後更新時間|
## location

位置信息表：記錄位置信息

| 字段名字 | 數據類型 | 是否爲空（Y/N） |注釋      |
| -------- | -------- | --------------- | ---- |
| online_id | int | N |ID of operating location 經營地點的ID |
|  new        | bool |                 N| 提醒有新的區域可以有美食車服務 1 —新内容 0---沒有新内容 |
|     lat     | float |                 N| Latitude 緯度 |
|long|float|N|longitude 經度|
|name_en|varchar|N|地方名字（EN）|
|name_tc|varchar|N|地方名字（TC）|
|name_sc|varchar|N|地方名字（SC）|
|downloadmap_en|varchar|N|離綫地圖（EN）|
|downloadmap_tc|varchar|N|離綫地圖（TC）|
|downloadmap_sc|varchar|N|離綫地圖（TC）|
|photo_en|varchar|N|景點圖片（EN）|
|photo_tc|varchar|N|景點圖片（TC）|
|photo_sc|varchar|N|景點圖片（SC）|
|about_en|varchar|N|景點介紹（EN）|
|about_tc|varchar|N|景點介紹（TC）|
|about_sc|varchar|N|景點介紹（SC）|
|logo_en|varchar|N|logo圖片（EN）|
|logo_tc|varchar|N|logo圖片（TC）|
|logo_sc|varchar|N|logo圖片（SC）|

## menu

|字段名字 |  數據類型   |  是否爲空（Y/N）   | 注釋   |
| ------- | ---- | ---- | ---- |
|     page_id     | int | N | 頁面id |
|       title_en   | varchar | N | 標題 |
|     title_tc     | varchar | N | 標題 |
| title_sc  |varchar|N|標題|
| is_valid |bool|N|該菜式是否有效|

## page
|字段名字 |  數據類型   |  是否爲空（Y/N）   | 注釋   |
| ------- | ---- | ---- | ---- |
|aboutus_photo_en|varchar|N|照片（EN）|
|aboutus_photo_tc|varchar|N|照片（TC）|
|aboutus_photo_sc|varchar|N|照片（SC）|
|trvhk_photo_en|varchar|N|"Travel in Hong Kong"的照片（TC）|
|trvhk_photo_tc|varchar|N|"Travel in Hong Kong"的照片（SC）|
|trvhk_photo_sc|varchar|N|"Travel in Hong Kong"的照片（EN）|
|trvhk_url_en|varchar|N|"Travel in Hong Kong"的html（EN）|
|trvhk_url_tc|varchar|N|"Travel in Hong Kong"的html（TC）|
|trvhk_url_sc|varchar|N|"Travel in Hong Kong"的html（SC）|
|priv_en|varchar|N|"Privacy Policy"的html（EN）|
|priv_tc|varchar|N|"Privacy Policy"的html（TC）|
|priv_sc|varchar|N|"Privacy Policy"的html（SC）|
|dis_en|varchar|N|"Disclaimer"的html（EN）|
|dis_tc|varchar|N|"Disclaimer"的html（TC）|
|dis_sc|varchar|N|"Disclaimer"的html（SC）|
|aboutus_url_en|varchar|N|“The Birth of 16 FoodTrucks”的html(EN)|
|aboutus_url_tc|varchar|N|“The Birth of 16 FoodTrucks”的html(TC)|
|aboutus_url_sc|varchar|N|“The Birth of 16 FoodTrucks”的html(SC)|

## setting
|字段名字 |  數據類型   |  是否爲空（Y/N）   | 注釋   |
| ------- | ---- | ---- | ---- |
|text_size|number|N|文字大小|
|version|float|N|版本號|
|lang|varchar|N|語言|
|first|bool|N||
|calendar_version|varchar|N|日曆版本號|
|foodtruck_version|varchar|N|美食車版本號|
|location_version|varchar|N|位置信息版本號|
|event_version|varchar|N|盛事信息版本號|
|album_version|varchar|N|照片信息版本號|
|page_version|varchar|N|頁面信息版本號|
|pushalert_version|varchar|N|警告信息版本號|
|dishes_version|varchar|N|菜式版本號|