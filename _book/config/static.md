# 静态资源配置
* 目前只写了阿里云的静态资源配置。

* 修改静态资源为OSS，会有效减轻服务器压力，并提高资源加载速度（特别是带宽低的服务器）

#####步骤
1、在后台修改文件上传为阿里云，并修改对应的配置项

![阿里云上传配置](../images/upload_config.jpg)

2、修改`.nev`文件下的配置：
* `EASYADMIN.CDN`：静态资源地址（例如：https://easyadmin.oss-cn-shenzhen.aliyuncs.com/static_easyadmin）
* `EASYADMIN.OSS_STATIC_PREFIX`：静态资源上传前缀（例如：static_easyadmin）

3、在项目的主目录下执行：`php think OssStatic`，就会将`public/static`路径下的所有静态资源上传上去

![执行命令行](../images/oss_static.jpg)

4、删除该目录下`runtime/admin/cache`的缓存资源