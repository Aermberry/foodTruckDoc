# Food Truck Api Document（V3）

[^Author]: 
[^Version]: 
[^Create_at]: 

[TOC]
## 錯誤碼
~~~http
以http status code为准

200:成功

400:请求错误（都是用户的问题）

401: 需要重新登录

404:请求不存在

500:服务端内部错误	
~~~
## API URL

~~~
前綴（url）：https://foodtruck-uat.kanhan.com/json_v3
~~~
## API接口詳細列表
### versions（ 版本信息）
- request_url
  ```http
  get /foodtruck_version_n.json
  ```
- request_body
  ```json
  noen
  ```
- response_body
  ```json
  {
       version_pushalert: String,//推送版本號
       version_page: String,//頁面版本信息
       version_foodtruck: String,//美食車版本號
       version_location: String,//運營地點版本號
       version_event: String,//盛事版本號
       version_dishes: String,//招牌菜版本號
       version_album: String,//相簿版本號
       version_calendar: String //營運時間版本號
  }
  ```
### push_alert（推送信息）
- request_url
  ~~~http
  get /foodtruck_pushalert.json
  ~~~
~~~
- request_body
  ~~~json
  none
~~~
- response_body
  - There is alert message
    ~~~json
    	{
    	     PushAlert: {
    	          en: String,//英語語言
    	          tc: String,//繁體字中文語言
    	          sc: String//簡體字中文語言
    	     }
    	}
    ~~~

### food_truck(美食車)
- request_url

  ~~~http
  get /foodtruck_foodtruck.json
  ~~~

- request_body

  ~~~json
  none
  ~~~

- response_body

  ~~~json
  	{
  	FoodTruck: {
  	     list: [
  	     {
  	          id: String,//food_truck_id 美食車id
  	          is_new: bool,//提醒有新的美食車提供服務:
               			  //0:沒有新内容 
                            //1 :新内容
  	          company: {  //公司名字
  	               en: String, //公司名字（EN）
  	               tc: String,     //公司名字（TC）
  	               sc: String     //公司名字（SC）
  	          },
  	          signature_dish: {//美食车的招牌菜式
  	               en: String,//美食车的招牌菜式（EN）
  	               tc: String,//美食车的招牌菜式（TC）
  	               sc: String//美食车的招牌菜式（SC）
  	          },
  	          photo: {//美食車封面圖的url
  	               en: String,//美食車封面圖的url（EN）
  	               tc: String,//美食車封面圖的url（TC）
  	               sc: String//美食車封面圖的url（SC）
  	          },
  	          logo: {//logo圖片的url
  	               en: String,//logo圖片的url(EN)
  	               tc: String,//logo圖片的url(TC)
  	               sc: String//logo圖片的url(SC)
  	          },
  	          about: {//美食車簡介
  	               en: String,//美食車簡介（EN）
  	               tc: String,//美食車簡介（TC）
  	               sc: String//美食車簡介（SC）
  	          },
  	          menu: {//美食車菜單
  	               en: String,//美食車菜單（EN）
  	               tc: String,//美食車菜單（TC）
  	               sc: String//美食車菜單（SC）
  	          },
  	          twitter: {//twitter_url
  	               en: String,//twitter_url（EN）
  	               tc: String,//twitter_url（TC）
  	               sc: String//twitter_url（SC）
  	          },
  	          facebook: {//facebook_url
  	               en: String,//facebook_url（EN）
  	               tc: String,//facebook_url（TC）
  	               sc: String//facebook_url（SC）
  	          }
  	     }
  	     ]
  	}
  	}
  ~~~
### operating_location（運營地點）
- require_url
  ~~~http
  get /foodtruck_location.json
  ~~~
- request_body
  ~~~json
  none
  ~~~
- response_body
  ~~~json
  {
    operating_location: {  //美食车的运营地点
       list: [
            {
                 id: int,// ID of operating location 經營地點的ID
              is_new: bool,//提醒有新的區域可以有美食車服務:0：沒有新内容 1:新内容 
             latitude: String,//緯度
             longitude: String,//經度
                 name: {//地方名字
                      en: String,//地方名字（EN）
                      tc: String,//地方名字（TC）
                      sc: String//地方名字（SC）
                 },
                download_map: {//離綫地圖
                      en: String,//離綫地圖的url（EN）
                      tc: String,//離綫地圖的url（TC）
                      sc: String//離綫地圖的url（SC）
                 },
                 photo: {//景點圖片的url
                      en: String,//景點圖片的url(EN)
                      tc: String,//景點圖片的url(TC)
                      sc: String//景點圖片的url(SC)
                 },
                 logo: {//logo圖片的url
                      en: String,//logo圖片的url(EN)
                      tc: String,//logo圖片的url(TC)
                      sc: String//logo圖片的url(SC)
                 },
                 about: {//景點介紹的html
                      en: String,//景點介紹的html（EN）
                      tc: String,//景點介紹的html（TC）
                      sc: String//景點介紹的html（SC）
                 }
            }
       ]
       }
  }
  ~~~
### events(盛事及運動)
- require_url
  ~~~http
  get /foodtruck_event.json
  ~~~
- require_body
  ~~~json
  none
  ~~~
- response_body
  ~~~json
  {
       Location: {
       list: [
            {
                 id: String,//盛事活動id
              is_new: bool,// 提醒此爲新的盛事活動:1 代表新内容 0 代表沒有新内容
            latitude: String,//緯度
           longitude: String,//經度
                 name: { //盛事活動名字
                      en: String,
                      tc: String,
                      sc: String
                 },
                 location: { //位置信息
                      en: String,
                      tc: String,
                      sc: String
                 },
                 desc: {//活動開放時間日期
                      en: String,
                      tc: String,
                      sc: String
                 },
                download_map: {//下載地圖
                      en: String,
                      tc: String,
                      sc: String
                 },
                 photo: {//活動主題圖片
                      en: String,
                      tc: String,
                      sc: String
                 },
                 logo: {//logo圖片的url
                      en: String,
                      tc: String,
                      sc: String
                 },
                 about: {//活動簡介
                      en: String,
                      tc: String,
                      sc: String
                 }
            }
       ]
       }
  }
  ~~~
### operating_schedule  (Operating Schedule)
- require_url
  ~~~http
  get /foodtruck_calendar.json
  ~~~
- require_body
  ~~~json
  none
  ~~~
  
- response_body
  ~~~json
  operating_schedule: { //日曆
       list: [
            {
                date: String,//日期  格式：YYYY-MM-DD
                 locationEventList: [//
                      {
          				operating_location_id: "",//ID of operating location 經營地點的ID(關聯到locations表的id)
                           event_id: String,//盛事事件id(關聯到events表的id)
                           foodtruckList: [
                                {
                             food_truck_id: String,//美食車的id（關聯到food_trucks表中的id）
                                     shift: null|bool,//晝夜更替 
                                    //"morning" —> the foodtruck work on morning
                                    // "night" —> the foodtruck work on night
                                    // "full_day" —> the foodtruck work on full day
                                     business_hours_describe: {
                                          en: String,
                                         //描述營業時間信息（EN）
                                          tc: String,
                                         //描述營業時間信息（TC）
                                          sc: String
                                         //描述營業時間信息（SC）
                                     }
                                }
                           ]
                      },
                      {
                  		operating_location_id: String,
                           EVID: "",
                           foodtruckList: [
                                {
                                  food_truck_id: String,
                                     shift: null|bool,
                                     business_hours_describe: {
                                          en: String,
                                          tc: String,
                                          sc: String
                                     }
                                }
                           ]
                      },
                      {
                           operating_location_id: String,
                           EVID: String,
                           foodtruckList: [
                                {
                                     FTID: String,
                                     shift: null|bool,
                                     business_hours_describe: {
                                          en: String,
                                          tc: String,
                                          sc: String
                                     }
                                },
                                     FTID: String,
                                     shift: String,
                                     business_hours_describe: {
                                          en: String,
                                          tc: String,
                                          sc: String
                                     }
                                },
                           ]
                      },
                      {
                           operating_location_id: String,
                           EVID: String,
                           foodtruckList: [
                                {
                                     food_truck_id: String,
                                     shift: null|bool,
                                     business_hours_describe: {
                                          en: String,
                                          tc: String,
                                          sc: String
                                     }
                                },
                                     food_truck_id: String,
                                     shift: null|bool,
                                     business_hours_describe: {
                                          en: String,
                                          tc: String,
                                          sc: String
                                     }
                                },
                           ]
                      }
                 ]
            }
       ]
  }
  ~~~
### signature_dishs（招牌菜式）
- require_url
  ~~~http
  get /foodtruck_dishes.json
  ~~~
- require_body
  ~~~json
  none
  ~~~
- response_body
  ~~~json
  {
   signature_dishs: {//招牌菜式
       list: [
            {
                 SDID: String,//美食車招牌菜id
                 FTID: String,//美食車id
                 name: {//美食车的招牌菜式名字
                      en: String,
                      tc: String,
                      sc: String
                 },
                 company: {//公司名
                      en: String,
                      tc: String,
                      sc: String
                 },
                 photo: {//文字圖片的url
                      en: String,
                      tc: String,
                      sc: String
                 },
            }
       ]
       }
  }
  ~~~
### album（相簿）
- require_url
  ~~~http
  get /foodtruck_album.json
  ~~~
- require_body
  ~~~json
  none
  ~~~
- response_body
  ~~~json
  {
       Album: {//相簿
       list: [
            {
                 id: String,//相簿的id
             event_id: null,//盛事的id
                 name: {//相簿名字
                      en:  String,
                      tc:  String,
                      sc:  String
                 },
                 covePhoto: String,//相簿封面照片的url地址
                 photoList: [
                      {
                      url: String,//相簿中的圖片地址
                      photo_id: String,//相簿中的圖片id
                      caption: {//位於照片下方的標題
                           en: String,
                           tc: String,
                           sc: String
                      },
                      alt: {//照片的文字替代（方便屏幕閲讀器檢測）
                           en: String,
                           tc: String,
                           sc: String
                      }
                 }
            ]
            }
       ]
       }
  }
  ~~~
### page（頁面）
- require_url
  ~~~http
  get /foodtruck_page.json
  ~~~
- require_body
  ~~~json
  none
  ~~~
- response_body
  ~~~json
  {
       page: {//頁面信息
            about_us: {//“The Birth of 16 FoodTrucks”的html
                 en: {
                      photo: String,//宣傳照片的url
                      url: String
                 },
                 tc: {
                      photo: String,
                      url: String
                 },
                 sc: {
                      photo: String,
                      url: String
                 }
            },
            TravellingHK: {//隱私政策
                 en: {
                      photo: String,
                      url: String
                 },
                 tc: {
                      photo: String,
                      url: String
                 },
                 sc: {
                      photo: String,
                      url: String
                 }
            },
            privacy_policy: {
                 en: String,
                 tc: String,
                 sc: String
            },
            disclaimer: {//免責聲明
                 en: String,
                 tc: String,
                 sc: String
            }
       }
  }
  ~~~

  