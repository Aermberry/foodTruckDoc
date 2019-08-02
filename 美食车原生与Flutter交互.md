
## 美食车原生与Flutter交互

###1.控件标识符

```
viewType : plugins.google_map
```

###2.传入数据JSON格式

Flutter
~~~
  creationParams: {
     "json": "JSON内容",
  },
~~~


JSON内容格式
~~~
[{
	  station_id:int 			//当前美食车/营运地点ID
      name: String			//当前美食车/营运地点名称
      latitude:String 		//纬度
      longitude:string		//经度
      stations: [{			//当前营运地点下的美食车 不存在则为空
          url: String		//美食车Icon Url
      }]
}]
~~~


### 3.方法标识符

```
MethodChannel Name : plugins_google_map	//MethodChannel标识符
Method Name : onCLickMarker //地图点击事件回调方法名
```

### 4.回传数据JSON格式
```
{
	  id:int 			//当前美食车/营运地点ID
}
```


