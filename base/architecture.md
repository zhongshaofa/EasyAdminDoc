# 架构总览

```dotenv
EasyAdmin项目目录
├── addons                     //插件存放目录
├── app                        //应用目录
│   ├── admin                 //后台管理应用模块
│   ├── common                //通用应用模块
│   ├── BaseController.php    //控制器基础类
│   ├── common.php            //应用公共文件
│   ├── event.php             //事件定义文件
│   ├── ExceptionHandle.php   //应用异常处理类
│   ├── middleware.php        //全局中间件定义文件
│   ├── provider.php          //容器Provider定义文件
│   ├── Request.php           //应用请求对象类
├── extend                     //扩展辅助类目录
├── public
│   ├── static
│   │   ├── admin            //后台静态资源，js/css/images
│   │   ├── common           //公共资源
│   │   ├── plugs            //插件资源
│   └── uploads               //上传文件目录
│   ├── index.php             //应用入口主文件
│   └── router.php
├── runtime                    //缓存目录    
├── vendor                     //Compposer资源包位置
│   ├── zhongshaofa
│   │   ├── easy-addons      //插件扩展
│   │   ├── easy-admin       //后台扩展
├── view
│   │   ├── admin    //后台视图页面
│   │   ├── index    //前台视图页面
├── LICENSE
├── README.md
├── easyadmin.sql              //数据库安装文件
├── build.php                    
├── composer.json              //Composer包配置
└── think
```
