# table列表
虽然layui已经提供了很多方便的方法，但是还是不够简便，目前系统对layui table模块进行了重新封装，并兼容所有的layui table的方法。

使得开发起来更加得心应手，减轻工作量。

# `init`初始化配置

建议在此处统一配置table容器以及相关的链接地址。另外还可以自己进行扩展属性。

> 初始化的参数有

| 参数 | 说明 | 类型 | 是否必填 | 备注|
| --- | --- | --- |--- |--- |
| table_elem | table容器或者dom | string/dom| 是 |   |
| table_render_id | 容器唯一 id | string | 否 | |
| index_url | 列表接口 | string| 是 | |
| add_url | 添加接口 | string| 否 | 需用添加功能必填 |
| edit_url | 编辑接口 | string| 否 | 需用编辑功能必填 |
| del_url | 删除接口 | string| 否 | 需用删除功能必填 |
| export_url | 导出接口 | string| 否 | 需用导出功能必填 |
| modify_url | 属性修改接口 | string| 否 | 需用属性修改功能必填（例如：状态的切换） |

> 实例，下方`stock_url`就是扩展属性

```js
    var init = {
        table_elem: '#currentTable',
        table_render_id: 'currentTableRenderId',
        index_url: 'mall.goods/index',
        add_url: 'mall.goods/add',
        edit_url: 'mall.goods/edit',
        del_url: 'mall.goods/del',
        export_url: 'mall.goods/export',
        modify_url: 'mall.goods/modify',
        stock_url: 'mall.goods/stock',
    };
```

# 表格实例化

表格实例化方法为`ea.table.render()`, 兼容layui table的所有功能，另外还扩展了一些新的功能。

# 扩展表格参数

这些是基于layui的table的进行扩展的基础参数，如需查看其他的参数，请去layui官网查看。
 
| 参数 | 说明 | 类型 | 是否必填| 默认值 | 备注|
| --- | --- | --- |--- | --- | --- |
| init | `init`初始化配置 | object| 是 | |  一般情况下，请传入上方配置好的初始化参数 |
| search | 是否开启搜索功能 | bool| 否 | true | 开启会自动根据`列`生成搜索表单 |
| modifyReload | 修改属性时是否刷新表格 | bool| 否 | true |  |
| toolbar | table操作栏 | object| 否 | ['refresh','add','delete','export'] | 除了这些内置的，还可以自己进行扩展 |

> 代码示例

```js
    ea.table.render({
        init: init,
        toolbar: [...表格toolbar...],
        cols: [...请参考下方列参数...],
    });
```

# 表格toolbar

# 列参数

# 列operat

| 参数 | 说明 | 类型 | 是否必填| 默认值 | 备注|
| --- | --- | --- |--- | --- | --- |
| class | 样式信息 | string| 否 | |   |
| icon | 图标信息 | string| 否 | | 在行操作里面，不建议使用图标 |
| title | 提示信息 | string| 否 | 为空则读取`text`属性 | |
| text | 文本信息 | string| 否 | 为空则读取`title`属性 | |
| method | 执行方式 | string| 否 | open | `open` 为弹出层打开  `request` 为直接请求|
| url | 请求链接 | string| 是 | | |
| auth | 权限规则 | string| 是 | | 权限规则，具体请参考配置`auth权限验证`模块 |
| field | 绑定行字段 | string| 否 | id | 会自动根据此字段生成链接后缀 |
| extend | 扩展属性 | string| 否 | | 例如弹出层全屏操作，可以加上：`data-full="true"` |

# 内置templet方法

| 方法 | 说明 | 备注|
| --- | --- | --- |
| ea.table.list | 根据行的`selectList`返回对应列表值 | 一般类型之类的会用到 |
| ea.table.image | 显示图片 | 行参数`imageHeight`是控制图片的高度 |
| ea.table.url | 格式化显示链接 |  |
| ea.table.switch | 生成开关组件 |  |
| ea.table.price | 格式化为价格 |  |
| ea.table.percent | 格式化为百分比 |  |
| ea.table.icon | 显示图标 |  |
| ea.table.value | 格式化数据 | 多层对象数据的显示 |
