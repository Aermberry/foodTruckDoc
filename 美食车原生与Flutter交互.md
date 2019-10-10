
## 美食车原生与Flutter交互

- ### 地图

####1、地图控件标识符

```
viewType : plugins.google_map
```

####2、初始化需要传入的数据

##### viewID

```
viewID // Int 用于区分在不同页面使用的地图控件
```

##### arguments

~~~json
{
	"json": "JSON内容"
}
~~~


JSON内容格式
~~~json
[{
    station_id:int 			//当前美食车/营运地点ID
    name: String				//当前美食车/营运地点名称
    latitude:String 		//纬度
    longitude:string		//经度
    stations: [{				//当前营运地点下的美食车 不存在则为空
        url: String			//美食车Icon Url
    }]
}]
~~~

#### 3、更新数据(使用FlutterMethodChannel)

##### MethodChannel Name

```
plugins.google_map/methodChannel_viewID		// 其中 viewID 为上面的 viewID
```

##### method name

```
updateData
```

##### method arguments

```
{
	"json": "JSON内容",
}
JSON内容为 2 中的内容
```

##### CallBack

```
无
```

#### 4、地图点击事件(使用FlutterEventChannel)

##### EventChannel Name

```
plugins.google_map/click_viewID		// 其中 viewID 为上面的 viewID
```

##### CallBack

```
{
	  id:int 			// 当前美食车/营运地点ID
}
```

##### 注意事项：

##### FlutterMethodChannel和FlutterEventChannel需要在控件初始化后才能注册。