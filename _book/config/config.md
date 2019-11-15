# 配置

### env配置说明

   ``` dotenv
   APP_DEBUG = true
   
   [APP]
   DEFAULT_TIMEZONE = Asia/Shanghai
   
   [DATABASE]
   TYPE = mysql
   HOSTNAME = host.docker.internal
   DATABASE = easyadmin
   USERNAME = root
   PASSWORD = root
   HOSTPORT = 3306
   CHARSET = utf8
   DEBUG = true
   PREFIX = ea_
   
   [LANG]
   default_lang = zh-cn
   
   [EASYADMIN]
   ADMIN = admintest
   CAPTCHA = false
   CDN =
   EXAMPLE = true
   ```
   * EASYADMIN.ADMIN：后台路径
   * EASYADMIN.CAPTCHA：是否开启验证码
   * EASYADMIN.CDN：静态资源地址
   * EASYADMIN.EXAMPLE：是否为演示环境