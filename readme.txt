https://ceshiren.com/t/topic/24784
Litemall商品接口文档

一、获取 token
获取X-Litemall-Admin-Token是调用Litemall商城后台管理API接口的第一步，相当于创建了一个登录凭证，其它的业务API接口，都需要依赖于X-Litemall-Admin-Token来鉴权调用者身份。

请求方式： POST（HTTP ）
请求地址：https://litemall.hogwarts.ceshiren.com/admin/auth/login
参数说明：

参数	是否必填	说明
username	是	用户名，默认hogwarts
password	是	密码，默认密码test12345
返回结果：

{
    "errno":0,
    "data":{
        "adminInfo":{
            "nickName":"admin123",
            "avatar":"https://wpimg.wallstcn.com/f778738c-e4f8-4870-b634-56703b4acafe.gif"
        },
        "token":"830cd329-befb-4ec5-9960-626197abaa9a"
    },
    "errmsg":"成功"
}
备注：X-Litemall-Admin-Token 使用方法：在每个业务接口的headers中添加token键值对，键为“X-Litemall-Admin-Token”，值为具体的token值。

字段	值	备注
X-Litemall-Admin-Token	随机文本，例如“7172bbc7-f81a-4a78-9220-e55e3cfdf98c”	通过登录接口获取
二、增加商品类别
管理员可以通过此接口实现添加商品类别功能。
请求方式：POST(HTTP)
请求地址：https://litemall.hogwarts.ceshiren.com/admin/category/create 6
请求示例：

{
"id": 123456,
"name": "ceshiren",
"keywords": "666",
"desc": "",
"iconUrl": "https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png",
"picUrl": "https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png",
"level": "L1",
"children": [],
"preview": [
"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png"
],
"pid": 0
}
参数说明:

参数	字段类	是否必填	说明
name	对象	是	商品类别名称
返回结果:

{"errno":0,"data":{"id":1045593,"name":"ceshiren","keywords":"666","desc":"","pid":0,"iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","addTime":"2023-05-09 16:04:38","updateTime":"2023-05-09 16:04:38"},"errmsg":"成功"}
三、查询商品类别
请求方式：GET (HTTP)**
请求地址：https://litemall.hogwarts.ceshiren.com/admin/category/list 5
参数说明:

{"name":"ceshiren"}
返回结果:

{"errno":0,"data":{"total":13,"pages":1,"limit":13,"page":1,"list":[{"id":1045513,"name":"东方青仓","keywords":"","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/dyiuzz6o6p48gdt05spr.jpg","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/4jb9a5l96mcagvrhgx7b.jpg","level":"L1","children":[]},{"id":1045526,"name":"gxd","keywords":"","desc":"","iconUrl":"","picUrl":"","level":"L2","children":[]},{"id":1045569,"name":"@@@","keywords":"","desc":"","iconUrl":"","picUrl":"","level":"L2","children":[]},{"id":1045570,"name":"字","keywords":"","desc":"","iconUrl":"","picUrl":"","level":"L2","children":[]},{"id":1045573,"name":"巩固","keywords":"","desc":"","iconUrl":"","picUrl":"","level":"L1","children":[]},{"id":1045574,"name":"发送","keywords":"色粉","desc":"","iconUrl":"","picUrl":"","level":"L1","children":[]},{"id":1045577,"name":"都是","keywords":"","desc":"","iconUrl":"","picUrl":"","level":"L2","children":[]},{"id":1045588,"name":"???","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]},{"id":1045589,"name":"???","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]},{"id":1045590,"name":"ceshiren","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]},{"id":1045591,"name":"ceshiren","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]},{"id":1045592,"name":"???","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]},{"id":1045593,"name":"ceshiren","keywords":"666","desc":"","iconUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/8ln70p6vkxoo7ka6qwgo.png","picUrl":"https://litemall.hogwarts.ceshiren.com/wx/storage/fetch/wrp477xszr0azoirp6ql.png","level":"L1","children":[]}]},"errmsg":"成功"}



