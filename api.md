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
'/login'
+ 功能说明：用户登录
+ 请求方法：
+ 请求体：
~~~
~~~
'/register'
+ 功能说明：用户注册
+ 请求方法：
+ 请求体：
~~~
~~~
'/index'
+ 功能说明：首页
+ 请求方法：
+ 请求体：
~~~
~~~
###  用户中心管理部分(请求前缀为 '/user/control')
'/home'
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
'/topicList'
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
'/commentList'
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
'/replyList'
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
'/point'
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
