## 收藏夹部分接口（前缀均为user/control/favorite）
### `/add`
+ 功能说明：收藏夹   添加
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long topicId;
  String content;
	String token;
  String jumpUrl;
	RedirectAttributes redirectAttrs;
}
~~~
+ 响应体：
~~~
if(Ajax)
{success:boolean}
else{
if(error){//return url参数}
else{//jump}
}
~~~
