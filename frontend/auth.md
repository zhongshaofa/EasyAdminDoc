# auth权限验证
为什么前端也做权限认证，权限认证不应该是后端做的吗？

这里的权限认证指的是前端判断是否有权限查看的数据（例如：添加、删除、编辑之类的按钮），这些只有在点击到对应的url之后，后端才会进行权限认证。

为了避免用户困扰，可以在此用上前端的权限认证，判断是否显示还是隐藏

##### 例子
* 添加上`auth="system.menu/add"`
* 如果页面中没有引入`public/static/admin/css/public.css`样式文件，需要手动添加该样式`[auth] { display: none; }`
* 在对应的js文件内引入`admin`模块，并执行`admin.listen();`进行监听

```html
<button class="layui-btn layui-btn-sm" auth="system.menu/add">添加</button>
```

