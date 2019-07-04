# 接口文档
所有的请求体、响应体表示方式均以TypeScript的表示方式为准。
----
## 响应代码
项目中所有可能出现的http响应代码列表如下：
+ 一切正常
-----
## 输入约束
目前项目具体限制为：

-----
## 各个请求的详细信息（所有请求格式前缀均为/bbs）
`/login`
+ 功能说明：用户登录
+ 请求方法：
+ 请求体：
~~~
~~~
`/register`
+ 功能说明：用户注册
+ 请求方法：
+ 请求体：
~~~
~~~
`/index`
+ 功能说明：首页
+ 请求方法：
+ 请求体：
~~~
~~~
###  用户中心管理部分(请求前缀为 '/user/control')
`/home`
+ 功能说明：用户中心页,需要判断是不是用户本人
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  String userName;
}
~~~
+ 响应体：
~~~
{
  if(isAjax){//如果是Ajax方式提交
			WebUtil.writeToWeb(JsonUtils.toJSONString(returnValue), "json", response);
			return null;
		}else{
			String dirName = templateService.findTemplateDir_cache();
			return "templates/"+dirName+"/"+accessSourceDeviceManage.accessDevices(request)+"/home";	
		}
}
~~~
`/topicList`
+ 功能说明：我的话题列表
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  PageForm pageForm;
}
~~~
+ 响应体
~~~
  if(isAjax){
			WebUtil.writeToWeb(JsonUtils.toJSONString(pageView), "json", response);
			return null;
		}else{
			String dirName = templateService.findTemplateDir_cache();
		    return "templates/"+dirName+"/"+accessSourceDeviceManage.accessDevices(request)+"/topicList";	
		}
~~~
`/commentList`
+ 功能说明：我的评论列表
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  PageForm pageForm;
}
~~~
+ 响应体
~~~
  if(isAjax){
			WebUtil.writeToWeb(JsonUtils.toJSONString(pageView), "json", response);
			return null;
		}else{
			String dirName = templateService.findTemplateDir_cache();
		    return "templates/"+dirName+"/"+accessSourceDeviceManage.accessDevices(request)+"/commentList";	
		}
~~~ 
`/replyList`
+ 功能说明：我的评论列表
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  PageForm pageForm;
}
~~~
+ 响应体
~~~
  if(isAjax){
			WebUtil.writeToWeb(JsonUtils.toJSONString(pageView), "json", response);
			return null;
		}else{
			String dirName = templateService.findTemplateDir_cache();
		    return "templates/"+dirName+"/"+accessSourceDeviceManage.accessDevices(request)+"/replyList";	
		}
~~~ 
`/point`
+ 功能说明：积分
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  PageForm pageForm;
}
~~~
+ 响应体
~~~
  if(isAjax){
			WebUtil.writeToWeb(JsonUtils.toJSONString(pageView), "json", response);
			return null;
		}else{
			String dirName = templateService.findTemplateDir_cache();
		    return "templates/"+dirName+"/"+accessSourceDeviceManage.accessDevices(request)+"/replyList";
		}
~~~ 
`/editUser`
+ 功能说明：会员修改 显示部分
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
  User formbean;
  String jumpUrl;
  String encryptionData;//加密数据
  String secretKey;//密钥
}
~~~
+ 响应体
~~~
  if(isAjax){
			returnValue.put("user", viewUser);
			returnValue.put("userCustomList", userCustomList);
			
			WebUtil.writeToWeb(JsonUtils.toJSONString(returnValue), "json", response);
			return null;
		}else{
			return "templates/"+dirName+"/"+accessPath+"/editUser";	
		}
~~~ 
`/editUser`
+ 功能说明：密码修改
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  User formbean;
  String jumpUrl;
  String oldPassword;
  String token;
  RedirectAttributes redirectAttrs;
}
~~~
+ 响应体
~~~
  
~~~ 
`/updateAvatar`
+ 功能说明：修改头像
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  MultipartFile imgFile;
}
~~~
+ 响应体
~~~
  
~~~ 
`/realNameAuthentication`
+ 功能说明：实名认证
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
}
~~~
+ 响应体
~~~
  
~~~ 
`/phoneBinding`
+ 功能说明：手机绑定
+ 请求方法：GET
+ 请求体：
~~~
{
  ModelMap model;
}
~~~
+ 响应体
~~~
  
~~~ 
`/phoneBinding`
+ 功能说明：手机绑定
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  String mobile;
  String smsCode;
  String captchaKey;
  String captchaValue;
  String jumpUrl;
  String token;
  RedirectAttributes redirectAttrs;
}
~~~
+ 响应体
~~~
  
~~~ 
`/getSmsCode`
+ 功能说明：获取短信验证码
+ 请求方法：POST
+ 请求体：
~~~
{
  ModelMap model;
  String mobile;
  Integer module;
  String captchaKey;
  String captchaValue;
  String token;
}
~~~
+ 响应体
~~~
  
~~~ 
`/updatePhoneBinding/step1`
+ 功能说明：修改手机绑定 第一步验证旧手机界面
+ 请求方法：GET
+ 响应体
~~~
{
	return json;
}
~~~
`/updatePhoneBinding/step1`
+ 功能说明：修改手机绑定 第一步验证旧手机界面
+ 请求方法：POST
+ 请求体
~~~
{
	ModelMap model;
	String smsCode;
	String captchaKey;
	String captchaValue;
	String jumpUrl;
	String token;
	RedirectAttributes redirectAttrs;
}
+ 响应体
~~~
{
	return step2;
}
`/updatePhoneBinding/step2`
+ 功能说明：修改手机绑定 第二步验证新手机界面
+ 请求方法：GET
+ 响应体
~~~
{
	return json;
}
~~~
`/updatePhoneBinding/step2`
+ 功能说明：修改手机绑定 第二步验证新手机界面
+ 请求方法：POST
+ 请求体
~~~
{
	ModelMap model;
	String mobile;
	String smsCode;
	String captchaKey;
	String captchaValue;
	String jumpUrl;
	String token;
	RedirectAttributes redirectAttrs;
}
+ 响应体
~~~
{
	return /jump;
}
`/userLoginLogList`
+ 功能说明：用户登录日志列表
+ 请求方法：GET
+ 请求体
~~~
{
	PageForm pageForm;
}
~~~
+ 响应体
~~~
{

}
`/privateMessageList`
+ 功能说明：私信列表
+ 请求方法：GET
+ 请求体
~~~
{
	PageForm pageForm;
}
~~~
+ 响应体
~~~
{
			//查询结果集
}
`/privateMessageChatList`
+ 功能说明：私信列表
+ 请求方法：GET
+ 请求体
~~~
{
	PageForm pageForm;
	String friendUserName;//对方用户名称
}
~~~
+ 响应体
~~~
{
			//查询结果集
}
