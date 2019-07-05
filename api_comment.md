## 评论管理部分（前缀均为user/control/comment）
### `/add`
+ 功能说明：添加评论
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long topicId;
  String content;
	String token;
  String captchaKey;
  String captchaValue;
  String jumpUrl;
	RedirectAttributes redirectAttrs;
}
~~~
+ 响应体：
~~~
{
  success boolean;
}
~~~
### `/uploadImage`
+ 功能说明：评论  图片上传
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long topicId;
  MultipartFile imgFile;
}
~~~
+ 响应体：
~~~
//上传成功
{
  error: int,//0成功  1错误
  url: string,//"file/comment/"+topicId+"/"+newFileName
}
//上传失败
{
  error: int,//0成功  1错误
  message: String //errorMessage
}
~~~
### `/addQuote`
+ 功能说明：引用  添加
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long commentId;
  String content;
	String token;
  String captchaKey;
  String captchaValue;
  String jumpUrl;
	RedirectAttributes redirectAttrs;
}
~~~
+ 响应体：
~~~
//Ajax提交 错误
{
  success: boolean,//false
  error: string //returnError
  captchaKey
}
//Ajax提交 
{
	if(error)
		return //url参数
	else
	   //页面跳转
}
~~~
### `/addReply`
+ 功能说明：回复  添加
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  Long commentId;
  String content;
	String token;
  String captchaKey;
  String captchaValue;
  String jumpUrl;
	RedirectAttributes redirectAttrs;
}
~~~
+ 响应体：
~~~
//Ajax提交 错误
{
  success: boolean,//false
  error: string //returnError
  captchaKey
}
//Ajax提交 
{
	if(error)
		return //url参数
	else
	   //页面跳转
}
~~~
