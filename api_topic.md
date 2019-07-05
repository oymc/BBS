##话题接收表单(前缀均为user/control/topic)
### `/add`
+ 功能说明：话题添加
+ 请求方式：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long tagId;
  String title;
  String content;
  String token;
  String captchaKey;
  String captchaValue;
  String jumpUrl;
  RedirectAttributes redirectAttrs,
}
~~~
+ 响应体：
~~~
if(Ajax)
{
  success:boolean
}
else{
if(error){//return url}
else{//jump}
~~~
