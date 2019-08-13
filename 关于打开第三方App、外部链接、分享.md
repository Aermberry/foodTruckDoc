# 关于打开第三方App或者外部链接

### 使用url_launcher

```
https://pub.dev/packages/url_launcher
```



## 分享

### 分享内容

```
eg
shareTitle: "kanhan"
shareDesc: "看汉公司"
shareLink: "https://chinese.kanhan.com/"


shareMsg: %@\n%@\n%@
其中每一个%@分别代表上面三个信息

shareMsgURLEncode: 对 shareMsg进行 URL 编码(UTF8)
```

### iOS分享到 Line

```
链接格式：
line://msg/text/%@,其中%@表示shareMsgURLEncode
```

然后使用上面的 url_launcher 工具打开链接

### iOS分享到 WhatsApp

```
链接格式：
whatsapp://send?text=%@,其中%@表示shareMsgURLEncode
```

然后使用上面的 url_launcher 工具打开链接

### iOS发送邮件

```
直接使用url_launcher例子
```

