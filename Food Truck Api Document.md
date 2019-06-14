# Food Truck Api Document 

## API接口詳細列表
### versions（ 版本信息）
- request_url
  ```http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_version_n.json
  ```

- request_body
  ```json
  noen
  ```

- response_body
  ```json
  {
       version_pushalert: "201801031614",//推送版本號
       version_page: "201810241638",//頁面版本信息
       version_foodtruck: "201806180939",//美食車版本號
       version_location: "201906101303",//運營地點版本號
       version_event: "201906101303",//盛事版本號
       version_dishes: "201711091042",//招牌菜版本號
       version_album: "201903261755",//相簿版本號
       version_calendar: "201906101303" //營運時間版本號
  }
  ```
  

### push_alert（推送信息）

- request_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_pushalert.json
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
    	          en: "Book Brothers, Ma Ma's Dumpling Limited and Pineapple Canteen start operating on 3 Feb.",//英語語言
    	          tc: "大師兄美食車、有得餃水餃專門店及菠蘿仔食堂於2月3日投入服務。",//繁體字中文語言
    	          sc: "大师兄美食车、有得饺水饺专门店及菠萝仔食堂于2月3日投入服务。"//簡體字中文語言
    	     }
    	}
    ~~~

### food_truck
- request_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_foodtruck.json
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
  	          id: "1",//food_truck_id 美食車id
  	          is_new: "0",//提醒有新的美食車提供服務:
               			  //0:沒有新内容 
                            //1 :新内容
  	          company: {  //公司名字
  	               en: "Chee Kei", //公司名字（EN）
  	               tc: "池記",     //公司名字（TC）
  	               sc: "池记"     //公司名字（SC）
  	          },
  	          signature_dish: {//美食车的招牌菜式
  	               en: "Braised Pork Ribs Bento Box",//美食车的招牌菜式（EN）
  	               tc: "蘿白豬軟骨飯紅油雲吞便當",//美食车的招牌菜式（TC）
  	               sc: "萝白猪软骨饭红油云吞便当"//美食车的招牌菜式（SC）
  	          },
  	          photo: {//美食車封面圖的url
  	               en: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/Ftid1.png",//美食車封面圖的url（EN）
  	               tc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/Ftid1.png",//美食車封面圖的url（TC）
  	               sc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/Ftid1.png"//美食車封面圖的url（SC）
  	          },
  	          logo: {//logo圖片的url
  	               en: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/logo1.png",//logo圖片的url(EN)
  	               tc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/logo1.png",//logo圖片的url(TC)
  	               sc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/logo/logo1.png"//logo圖片的url(SC)
  	          },
  	          about: {//美食車簡介
  	               en: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_en.html",//美食車簡介（EN）
  	               tc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_tc.html",//美食車簡介（TC）
  	               sc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_sc.html"//美食車簡介（SC）
  	          },
  	          menu: {//美食車菜單
  	               en: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_20180613_menu_en.html",//美食車菜單（EN）
  	               tc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_20180613_menu_tc.html",//美食車菜單（TC）
  	               sc: "https://foodtruck.tourism.gov.hk/pages/foodtruck/foodtruck1_20180613_menu_sc.html"//美食車菜單（SC）
  	          },
  	          twitter: {//twitter_url
  	               en: "http://www.cheekeiwonton.com",//twitter_url（EN）
  	               tc: "http://www.cheekeiwonton.com",//twitter_url（TC）
  	               sc: "http://www.cheekeiwonton.com"//twitter_url（SC）
  	          },
  	          facebook: {//facebook_url
  	               en: "http://www.facebook.com/cheekeihk",//facebook_url（EN）
  	               tc: "http://www.facebook.com/cheekeihk",//facebook_url（TC）
  	               sc: "http://www.facebook.com/cheekeihk"//facebook_url（SC）
  	          }
  	     }
  	     ]
  	}
  	}
  ~~~

  

### operating_location
- require_url
  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_location.json
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
                 id: "1",// ID of operating location 經營地點的ID
              is_new: "0",//提醒有新的區域可以有美食車服務:0：沒有新内容 1:新内容 
             latitude: "22.284134",//緯度
             longitude: "114.174035",//經度
                 name: {//地方名字
                      en: "Golden Bauhinia Square",//地方名字（EN）
                      tc: "金紫荊廣場",//地方名字（TC）
                      sc: "金紫荆广场"//地方名字（SC）
                 },
                download_map: {//離綫地圖
                      en: "https://foodtruck.tourism.gov.hk/pages/location/map1_Golden_Bauhinia_Square.png",//離綫地圖的url（EN）
                      tc: "https://foodtruck.tourism.gov.hk/pages/location/map1_Golden_Bauhinia_Square.png",//離綫地圖的url（TC）
                      sc: "https://foodtruck.tourism.gov.hk/pages/location/map1_Golden_Bauhinia_Square.png"//離綫地圖的url（SC）
                 },
                 photo: {//景點圖片的url
                      en: "https://foodtruck.tourism.gov.hk/pages/location/Olid1_GoldenBauhiniaSquare.jpg",//景點圖片的url(EN)
                      tc: "https://foodtruck.tourism.gov.hk/pages/location/Olid1_GoldenBauhiniaSquare.jpg",//景點圖片的url(TC)
                      sc: "https://foodtruck.tourism.gov.hk/pages/location/Olid1_GoldenBauhiniaSquare.jpg"//景點圖片的url(SC)
                 },
                 logo: {//logo圖片的url
                      en: "https://foodtruck.tourism.gov.hk/pages/location/logo1.png",//logo圖片的url(EN)
                      tc: "https://foodtruck.tourism.gov.hk/pages/location/logo1.png",//logo圖片的url(TC)
                      sc: "https://foodtruck.tourism.gov.hk/pages/location/logo1.png"//logo圖片的url(SC)
                 },
                 about: {//景點介紹的html
                      en: "https://foodtruck.tourism.gov.hk/pages/location/location1_en.html",//景點介紹的html（EN）
                      tc: "https://foodtruck.tourism.gov.hk/pages/location/location1_tc.html",//景點介紹的html（TC）
                      sc: "https://foodtruck.tourism.gov.hk/pages/location/location1_sc.html"//景點介紹的html（SC）
                 }
            }
       ]
       }
  }
  ~~~

  

### events

- require_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_event.json
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
                 id: "11",//盛事活動id
              is_new: "0",// 提醒此爲新的盛事活動:1 代表新内容 0 代表沒有新内容
            latitude: "22.283841",//緯度
           longitude: "114.162073",//經度
                 name: { //盛事活動名字
                      en: "Hong Kong Dragon Boat Carnival",
                      tc: "「香港龍舟嘉年華」",
                      sc: "「香港龙舟嘉年华」"
                 },
                 location: { //位置信息
                      en: "Central Harbourfront Event Space",
                      tc: "中環海濱活動空間",
                      sc: "中环海滨活动空间"
                 },
                 desc: {//活動開放時間日期
                      en: "Date:\n 14 June 2019\n\nBusiness Hour:\n1:00pm - 9:00pm\n\nDate:\n 15-16 June 2019\n\nBusiness Hour:\n10:00am - 9:00pm",
                      tc: "日期:\n 2019年6月14日\n\n營業時間:\n1:00pm - 9:00pm\n\n日期:\n 2019年6月15-16日\n\n營業時間:\n10:00am - 9:00pm",
                      sc: "日期:\n 2019年6月14日\n\n营业时间:\n1:00pm - 9:00pm\n\n日期:\n 2019年6月15-16日\n\n营业时间:\n10:00am - 9:00pm"
                 },
                download_map: {//下載地圖
                      en: "https://foodtruck.tourism.gov.hk/pages/event/map_DragonBoat.png",
                      tc: "https://foodtruck.tourism.gov.hk/pages/event/map_DragonBoat.png",
                      sc: "https://foodtruck.tourism.gov.hk/pages/event/map_DragonBoat.png"
                 },
                 photo: {//活動主題圖片
                      en: "https://foodtruck.tourism.gov.hk/pages/event/event0614_tc.jpg",
                      tc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_tc.jpg",
                      sc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_sc.jpg"
                 },
                 logo: {//logo圖片的url
                      en: "https://foodtruck.tourism.gov.hk/pages/event/event0614_tc.png",
                      tc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_tc.png",
                      sc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_sc.png"
                 },
                 about: {//活動簡介
                      en: "https://foodtruck.tourism.gov.hk/pages/event/event0614_en.html",
                      tc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_tc.html",
                      sc: "https://foodtruck.tourism.gov.hk/pages/event/event0614_sc.html"
                 }
            }
       ]
       }
  }
  ~~~

### operating_schedule  
- require_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_calendar.json
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
                date: "2019-06-14",//日期  格式：YYYY-MM-DD
                 locationEventList: [//
                      {
          				operating_location_id: "",//ID of operating location 經營地點的ID(關聯到locations表的id)
                           event_id: "11",//盛事事件id(關聯到events表的id)
                           foodtruckList: [
                                {
                             food_truck_id: "1",//美食車的id（關聯到food_trucks表中的id）
                                     shift: null,//晝夜更替 
                                    //"morning" —> the foodtruck work on morning
                                    // "night" —> the foodtruck work on night
                                    // "full_day" —> the foodtruck work on full day
                                     business_hours_describe: {
                                          en: "Date:\n 14 June 2019\n\nBusiness Hour:\n1:00pm - 9:00pm\n\nDate:\n 15-16 June 2019\n\nBusiness Hour:\n10:00am - 9:00pm",
                                         //描述營業時間信息（EN）
                                          tc: "日期:\n 2019年6月14日\n\n營業時間:\n1:00pm - 9:00pm\n\n日期:\n 2019年6月15-16日\n\n營業時間:\n10:00am - 9:00pm",
                                         //描述營業時間信息（TC）
                                          sc: "日期:\n 2019年6月14日\n\n营业时间:\n1:00pm - 9:00pm\n\n日期:\n 2019年6月15-16日\n\n营业时间:\n10:00am - 9:00pm"
                                         //描述營業時間信息（SC）
                                     }
                                }
                           ]
                      },
                      {
                  		operating_location_id: "0",
                           EVID: "",
                           foodtruckList: [
                                {
                                  food_truck_id: "6",
                                     shift: null,
                                     business_hours_describe: {
                                          en: "Out of service today",
                                          tc: "是日未能提供服務",
                                          sc: "是日未能提供服务"
                                     }
                                }
                           ]
                      },
                      {
                           operating_location_id: "1",
                           EVID: "",
                           foodtruckList: [
                                {
                                     FTID: "7",
                                     shift: null,
                                     business_hours_describe: {
                                          en: "Business Hour:\n11:30am - 6:00pm",
                                          tc: "營業時間:\n11:30am - 6:00pm",
                                          sc: "营业时间:\n11:30am - 6:00pm"
                                     }
                                },
                                     FTID: "10",
                                     shift: "n",
                                     business_hours_describe: {
                                          en: "Business Hour:\n4:00pm - 9:00pm",
                                          tc: "營業時間:\n4:00pm - 9:00pm",
                                          sc: "营业时间:\n4:00pm - 9:00pm"
                                     }
                                },
                           ]
                      },
                      {
                           operating_location_id: "2",
                           EVID: "",
                           foodtruckList: [
                                {
                                     food_truck_id: "2",
                                     shift: null,
                                     business_hours_describe: {
                                          en: "Business Hour:\n11:30am - 6:00pm",
                                          tc: "營業時間:\n11:30am - 6:00pm",
                                          sc: "营业时间:\n11:30am - 6:00pm"
                                     }
                                },
                                     food_truck_id: "10",
                                     shift: "m",
                                     business_hours_describe: {
                                          en: "Business Hour:\n10:00am - 1:00pm",
                                          tc: "營業時間:\n10:00am - 1:00pm",
                                          sc: "营业时间:\n10:00am - 1:00pm"
                                     }
                                },
                           ]
                      }
                 ]
            }
       ]
  }
  ~~~

### signature_dishs

- require_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_dishes.json
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
                 SDID: "12",//美食車招牌菜id
                 FTID: "12",//美食車id
                 name: {//美食车的招牌菜式名字
                      en: "The Notorious P.I.G.",
                      tc: "手撕豬肉漢堡",
                      sc: "手撕猪肉汉堡"
                 },
                 company: {//公司名
                      en: "Beef & Liberty",
                      tc: "Beef & Liberty",
                      sc: "Beef & Liberty"
                 },
                 photo: {//文字圖片的url
                      en: "https:\/\/foodtruck.tourism.gov.hk\/pages\/dish\/Ftid12_D6.jpg",
                      tc: "https:\/\/foodtruck.tourism.gov.hk\/pages\/dish\/Ftid12_D6.jpg",
                      sc: "https:\/\/foodtruck.tourism.gov.hk\/pages\/dish\/Ftid12_D6.jpg"
                 },
            }
       ]
       }
  }
  ~~~

### album

- require_url

  ~~~http
  https://foodtruck-uat.kanhan.com/json_v3/foodtruck_album.json
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
                 id: "1",//相簿的id
             event_id: "",//盛事的id
                 name: {//相簿名字
                      en: "Food Trucks",
                      tc: "美食車",
                      sc: "美食车"
                 },
                 covePhoto: "https://foodtruck.tourism.gov.hk/pages/galleryft/galleryft.png",//相簿封面照片的url地址
                 photoList: [
                      {
                      url: "https://foodtruck.tourism.gov.hk/pages/galleryft/ev01.png",
                      PHID: "1",
                      caption: {
                           en: "",
                           tc: "",
                           sc: ""
                      },
                      alt: {
                           en: "Food Trucks",
                           tc: "美食車",
                           sc: "美食车"
                      }
                 }
            ]
            }
       ]
       }
  }
  ~~~

  