# auth权限验证
为什么前端也做权限认证，权限认证不应该是后端做的吗？

这里的权限认证指的是前端判断是否有权限查看的数据（例如：添加、删除、编辑之类的按钮），这些只有在点击到对应的url之后，后端才会进行权限认证。

为了避免用户困扰，可以在此用上前端的权限认证，判断是否显示还是隐藏

### 页面权限例子

* 第一种示例, 通过`auth`方法生成`layui-hide`样式属性。
```html
<button class="layui-btn layui-btn-sm {if !auth('system.menu/add')}layui-hide{/if}" auth="system.menu/add">添加</button>
```

* 第二种, 通过`auth`方法判断, 是否显示html
```html
{if !auth('system.menu/add')}
<button class="layui-btn layui-btn-sm" auth="system.menu/add">添加</button>
{/if}
```

### table表格权限例子


