# 环境要求

* PHP >= 7.1.0
* Mysql >= 5.7.0 (需支持innodb引擎)
* Apache 或 Nginx

# git下载

* 使用git克隆资源下来
    * `git clone https://github.com/zhongshaofa/easyadmin`
    * `git clone https://gitee.com/zhongshaofa/easyadmin`
* 将网站入口部署至`public`目录下面（即`easyadmin/public`目录下）
* 修改伪静态配置, 请参考下方伪静态设置。
* 运行网站地址, 会自动进入安装界面, 请根据提示进行设置, 然后点击安装。
* 安装完成后会自动生成安装锁`config/install/lock/install.lock`, 如需重新安装, 删掉该文件即可。

# 伪静态配置

通过伪静态配置, 将URL重写隐藏应用的入口文件`index.php`, 不配置的话, 会存在访问路径不正确的问题。

###Apache 

把下面的内容保存为`.htaccess`文件放到应用入口`public`文件的同级目录下
```dotenv
<IfModule mod_rewrite.c>
Options +FollowSymlinks -Multiviews
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^(.*)$ index.php?/$1 [QSA,PT,L]
</IfModule>
```
###Nginx 

在Nginx低版本中，是不支持PATHINFO的，但是可以通过在`Nginx.conf`中配置转发规则实现

```dotenv
location / { 
   if (!-e $request_filename) {
   		rewrite  ^(.*)$  /index.php?s=/$1  last;
    }
}
```