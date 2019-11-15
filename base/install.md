# 环境要求
* PHP >= 7.0
* Mysql >= 5.5.0 (需支持innodb引擎)
* Apache 或 Nginx

# git下载
* 使用git克隆资源下来

    * `git clone https://github.com/zhongshaofa/easyadmin`

    * `git clone https://gitee.com/zhongshaofa/easyadmin`

* 网站入口请部署至public文件夹下（即 easyadmin/public 目录下）

* 手动安装主目录下的`easyadmin.sql`的数据库文件

* 复制主目录下的`.example.env`文件为`.env`

* 修改`.env`的数据库配置信息以及后台入口后台入口配置项为：EASYADMIN.ADMIN

* 修改伪静态，请参考下方伪静态的配置

* 运行网站地址+后台入口

# 伪静态配置
可以通过URL重写隐藏应用的入口文件`index.php`
###Apache 
把下面的内容保存为`.htaccess`文件放到应用入口文件的同级目录下
```dotenv
<IfModule mod_rewrite.c>
  Options +FollowSymlinks -Multiviews
  RewriteEngine On

  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^(.*)$ index.php/$1 [QSA,PT,L]
</IfModule>
```
###Nginx 
在Nginx低版本中，是不支持PATHINFO的，但是可以通过在`Nginx.conf`中配置转发规则实现
```dotenv
location / { // …..省略部分代码
   if (!-e $request_filename) {
   		rewrite  ^(.*)$  /index.php?s=/$1  last;
    }
}
```