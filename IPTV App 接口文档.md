# IPTV App 接口文档

> 测试服务器 http://58.58.66.74:15180/

### 1.**用户登录**
* 接口说明：用于给验证设备账号。
* 请求地址：*/api/tv/userlogin*
* 请求方式：*GET*
* 参数:
>* *username* 用户名 (必填)
>* *mac_address1* 无线网卡mac地址 (必填)
>* *mac_address2* 有线网卡mac地址 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *suc* | bool | 是否登录成功|
| *msg* | string | 错误信息|

### 2. **广告接口**
* 接口说明：获取app相关广告信息。
* 请求地址：*/api/tv/ads*
* 请求方式：*GET*
* 参数:
>* *无*

* 说明:
>如果设置为播放2次 间隔时间为10分钟则2次播放完成为20分钟，执行完后开始下一条的播放。 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *befor_play* | object | 映前广告 |
| *befor_play.src* | string| 映前广告访问地址 |
| *befor_play.countdown* | string| 映前广告倒计时 |
| *appad* | object | app启动广告 |
| *appad.src* | object | app启动广告访问地址 |
| *appad.countdown* | object | app启动广告倒计时 |
| *captionad* | array | 字幕广告(多个)|
| *captionad[0].playtimes* | integer  | 字幕广告播放次数|
| *captionad[0].content* | string | 字幕广告内容|
| *captionad[0].interval* | integer | 字幕广告间隔时间|