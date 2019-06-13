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

