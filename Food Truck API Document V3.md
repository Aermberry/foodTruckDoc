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

~~~http
UAT Server：https://foodtruck-uat.kanhan.com/json_v3
~~~
## API接口詳細列表
### versions（ 版本信息）
- request_absoult
  ```http
  get /foodtruck_version_n.json
  ```
- response_body
  ```json
  {
       version_pushalert: String,		//推送版本號
       version_page: String,			//頁面版本信息
       version_foodtruck: String,		//美食車版本號
       version_location: String,		//運營地點版本號
       version_event: String,			//盛事版本號
       version_dishes: String,		//招牌菜版本號
       version_album: String,			//相簿版本號
       version_calendar: String 		//營運時間版本號
  }
  ```
### 獲取警告
- request_absoult
  ~~~http
  get /foodtruck_pushalert.json
  ~~~

- response_body
  
  - 
  
  ~~~json
  {
      PushAlert: {
          en: String,		//英語語言
  	    tc: String,		//繁體字中文語言
  	    sc: String		//簡體字中文語言
  	     }    
  }
  ~~~

### 獲取美食車
- request_absoult

  ~~~http
  get /foodtruck_foodtruck.json
  ~~~
- response_body

  ~~~json
  {
      FoodTruck: {
  	     list: [
               {
                   FTID: String,		//food_truck_id 美食車id
                   new: bool,			//提醒有新的美食車提供服務:
               			  			//0:沒有新内容 
                            			//1:新内容
                   company: {  		//公司名字
                       en: String, 	//公司名字（EN）
                       tc: String,    //公司名字（TC）
                       sc: String     //公司名字（SC）
                   },
                   dishes: {			//美食车的招牌菜式
                       en: String,	//美食车的招牌菜式（EN）
                       tc: String,	//美食车的招牌菜式（TC）
                       sc: String		//美食车的招牌菜式（SC）
                   },
                   photo: {			//美食車封面圖的absoult
                       en: String,	//美食車封面圖的absoult（EN）
                       tc: String,	//美食車封面圖的absoult（TC）
                       sc: String	//美食車封面圖的absoult（SC）
                   },
                   logo: {			//logo圖片的absoult
                       en: String,	//logo圖片的absoult(EN)
                       tc: String,	//logo圖片的absoult(TC)
                       sc: String	//logo圖片的absoult(SC)
                   },
                   about: {			//美食車簡介
                       en: String,	//美食車簡介（EN）
                       tc: String,	//美食車簡介（TC）
                       sc: String	//美食車簡介（SC）
                   },
                   menu: {			//美食車菜單
                       en: String,	//美食車菜單（EN）
                       tc: String,	//美食車菜單（TC）
                       sc: String	//美食車菜單（SC）
                   },
                   twitter: {			//twitter_absoult
                       en: String,	//twitter_absoult（EN）
                       tc: String,	//twitter_absoult（TC）
                       sc: String	//twitter_absoult（SC）
                   },
                   facebook: {		//facebook_absoult
                       en: String,	//facebook_absoult（EN）
                       tc: String,	//facebook_absoult（TC）
                       sc: String	//facebook_absoult（SC）
                   }
               }
           ]
      }
  }
  ~~~
### 獲取運營地點
- request_absoult
  ~~~http
  get /foodtruck_location.json
  ~~~
- response_body
  ~~~json
  {
      operating_location: {			//美食车的运营地点
          list: [
              {
                  OLID: int,		   	// ID of operating location 經營地點的ID
                  new: bool,  		//提醒有新的區域可以有美食車服務:
                  					//0：沒有新内容 
                  					//1:新内容
                  latitude: String,	//緯度
                  longitude: String,	//經度
                  name: {				//運營地點名字
                      en: String,		//運營地點名字（EN）
                      tc: String,		//運營地點名字（TC）
                      sc: String		//運營地點名字（SC）
                  },
                  download_map: {		//離綫地圖
                      en: String,	//離綫地圖的absoult（EN）
                      tc: String,	//離綫地圖的absoult（TC）
                      sc: String		//離綫地圖的absoult（SC）
                  },
                  photo: {			//運營圖片的absoult
                      en: String,	//運營圖片的absoult(EN)
                      tc: String,	//運營圖片的absoult(TC)
                      sc: String		//運營圖片的absoult(SC)
                  },
                  logo: {				//logo圖片的absoult
                      en: String,	//logo圖片的absolute absoult(EN)
                      tc: String,	//logo圖片的absoult(TC)
                      sc: String		//logo圖片的absoult(SC)
                  },
                  about: {			//運營介紹的html
                      en: String,	//運營介紹的html（EN）
                      tc: String,	//運營介紹的html（TC）
                      sc: String		//運營介紹的html（SC）
                  }
              }
          ]
      }
  }
  ~~~
### 獲取盛事及運動
- request_absoult
  ~~~http
  get /foodtruck_event.json
  ~~~
- response_body
  ~~~json
  {
      Location: {
          list: [
              {
                  EVID: String,		//盛事id
                  new: bool,			// 提醒此爲新的盛事:
                  					// 1 代表新内容
                  					// 0 代表沒有新内容
                  lat: String,		//緯度
                  long: String,		//經度
                  name: { 			//盛事名字
                      en: String,
                      tc: String,
                      sc: String
                  },
                  location: { 		//位置信息
                      en: String,
                      tc: String,
                      sc: String
              },
                  desc: {				//活動開放時間日期
                      en: String,
                      tc: String,
                      sc: String
                  },
                  download_map: {		//下載地圖
                      en: String,
                      tc: String,
                      sc: String
              },
                  photo: {			//活動主題圖片
                      en: String,
                      tc: String,
                      sc: String
              },
              logo: {					//logo圖片的absoult
                  en: String,
                  tc: String,
                  sc: String
              },
              about: {				//活動簡介
                  en: String,
                  tc: String,
                  sc: String
              }
              }
          ]
      }
  }
  ~~~
### 獲取運營時間
- request_absoult
  ~~~http
  get /foodtruck_calendar.json
  ~~~
- response_body
  ~~~json
  Calendar: {									//日曆
      list: [
          {
              date: String,								//日期  格式：YYYY-MM-DD
              locationEventList: [
                  {
                      operating_location_id: null|String,	//ID of operating location 
                      									//經營地點的ID
                      									//(關聯到locations表的id)
                      event_id: String,					//盛事id
                      									//(關聯到events表的id)
                      foodtruckList: [
                          {
                              food_truck_id: String,		//美食車的id
                              							//（關聯到food_trucks
                              							//表中的id）
                              SHIFT: null|bool,			//晝夜更替 
                              							//"morning": 
                              							//the foodtruck work on morning
                              							// "night":
                              							//the foodtruck work on night
                              							// "full_day":
                              							//the foodtruck 
                              							//work on full day
                              business_hours_describe: {
                                  en: String,				//描述營業時間信息（EN）
                                  tc: String,				//描述營業時間信息（TC）
                                  sc: String				//描述營業時間信息（SC）
                              }
                          }
                      ]
                  },
                  {
                      operating_location_id: String,
                      EVID: String,
                      foodtruckList: [
                          {
                              food_truck_id: String,
                              SHIFT: null|bool,
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
                          SHIFT:String,
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
                          SHIFT: null|bool,
                          desc: {
                              en: String,
                              tc: String,
                              sc: String
                          }
                      },
                      food_truck_id: String,
                      SHIFT: null|bool,
                      desc: {
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
### 獲取招牌菜式
- request_absoult
  ~~~http
  get /foodtruck_dishes.json
  ~~~
- response_body
  ~~~json
  {
      Dishs: {						//招牌菜式
          list: [
              {
                  SDID: String,		//美食車招牌菜id
                  FTID: String,		//美食車id
                  name: {				//美食车的招牌菜式名字
                      en: String,
                      tc: String,
                      sc: String
                  },
                  company: {			//公司名
                      en: String,
                      tc: String,
                      sc: String
                 },
                  photo: {			//文字圖片的absoult
                      en: String,
                      tc: String,
                      sc: String
                  },
              }
          ]
      }
  }
  ~~~
### 獲取相簿
- request_absoult
  ~~~http
  get /foodtruck_album.json
  ~~~
- response_body
  ~~~json
  {
      Album: {								//相簿
          list: [
              {
                  ABID: String,				//相簿的id
                  EVID: null| String,			//盛事id
                  name: {						//相簿名字
                      en:  String,
                      tc:  String,
                      sc:  String
                  },
                  covePhoto: String,			//相簿封面照片的absoult地址
                  photoList: [
                      {
                          absoult: String,		//相簿中的圖片地址
                          PHID: String,		//相簿中的圖片id
                          caption: {			//位於照片下方的標題
                              en: String,
                              tc: String,
                              sc: String
                          },
                          alt: {				//照片的文字替代（方便屏幕閲讀器檢測）
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
### 獲取頁面
- request_absoult
  ~~~http
  get /foodtruck_page.json
  ~~~
- response_body
  ~~~json
  {
      Page: {								//頁面信息
          AboutUs: {					    //“The Birth of 16 FoodTrucks”的html
              en: {
                  photo: String,			//宣傳照片的absoult
                  absoult: String
              },
              tc: {
                  photo: String,
                  absoult: String
              },
              sc: {
                  photo: String,
                  absoult: String
              }
          },
          TravellingHK: {					//隱私政策
              en: {
                  photo: String,
                  absoult: String
              },
              tc: {
                  photo: String,
                      absoult: String
                 },
              sc: {
                  photo: String,
                  absoult: String
              }
            },
            PrivacyPolicy: {
                 en: String,
                 tc: String,
                 sc: String
            },
            Disclaimer: {					//免責聲明
                 en: String,
                 tc: String,
                 sc: String
            }
       }
  }
  ~~~

  