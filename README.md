# (一）微信小程序图片直传阿里云OSS

[开通阿里云oss服务的介绍链接] (https://helpcdn.aliyun.com/document_detail/31884.html) 

下面的步骤一、步骤二是阿里云文档给出的对oss的Bucket配置和小程序配置

## 步骤一 配置 Bucket 跨域

如果不配置会出现跨域问题

![图片名称](https://github.com/webzhangxiaoyu/images/blob/master/BUCKET.png) 

__注意设定权限属性：__ 
__设定为公共读：上传需要授权，下载无需__ 

![图片名称](https://github.com/webzhangxiaoyu/images/blob/master/qx.png) 

__如果设置为私有，下载需要授权__ 

直接从数据库拿到的url是不能访问oss的图片的，需要通过签名算法给url加上签名标签和访问时效，给url一个临时授权才能访问到，过了访问时间这个url又变成无效，即防盗链。
数据库中拿到的url访问oss的图片会告诉你没有权限（如果oss设置为公共可读是可以通过这样访问的哦）

[阿里文档给的URL中包含签] (https://helpcdn.aliyun.com/document_detail/31884.html) 

[阿里云给我们提供了封装好的组件给我们使用，这个是js，其他可能要你自己去github上面找] (https://github.com/ali-sdk/ali-oss) 

![图片名称](https://github.com/webzhangxiaoyu/images/blob/master/sdk.png)  


## 步骤二 配置外网域名到小程序的上传域名白名单中

__建议测试阶段勾选不校验合法域名，因为小程序一个月就只能修改五次，测试好了在修改。__ 
![图片名称](https://github.com/webzhangxiaoyu/images/blob/master/cs.png)

[下载网站] (https://help.aliyun.com/document_detail/31925.html?spm=5176.doc31923.6.628.JYYHox) 

修改DEMO中的密钥和地址

![图片名称](https://github.com/webzhangxiaoyu/images/blob/master/id.png)

使用修改参数后的阿里OSS官方MODE就可以打开index.html进行上传测试了







