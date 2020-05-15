# table列表
虽然layui已经提供了很多方便的方法，但是还是不够简便，目前系统对layui table模块进行了重新封装，并兼容所有的layui table的方法。

使得开发起来更加得心应手，减轻工作量。

东西有点多，一时半会写不完，有空再写。。。。。

# 表格上方搜索器的自动生成

###示例
```js
define(["jquery", "admin",], function ($, admin) {

    var init = {
        table_elem: 'currentTable',
        table_render_id: 'currentTableRenderId',
        index_url: 'system.admin/index',
        add_url: 'system.admin/add',
        edit_url: 'system.admin/edit',
        del_url: 'system.admin/del',
        modify_url: 'system.admin/modify',
    };

    var Controller = {

        index: function () {
            admin.table.render({
                elem: '#' + init.table_elem,
                id: init.table_render_id,
                url: admin.url(init.index_url),
                init: init,
                toolbar: ['refresh', 'add', 'delete'],
                cols: [[
                    {type: "checkbox"},
                    {field: 'id', width: 80, title: 'ID', sort: true, align: "center"},
                    {field: 'username', minWidth: 80, title: '登录账户', align: "center"},
                    {field: 'head_img', minWidth: 80, title: '头像', search: false, imageHeight: 40, align: "center", templet: admin.table.image},
                    {field: 'phone', minWidth: 80, title: '手机', align: "center"},
                    {field: 'login_num', minWidth: 80, title: '登录次数', align: "center"},
                    {field: 'remark', minWidth: 80, title: '备注信息', align: "center"},
                    {field: 'status', title: '状态', width: 85, align: "center", search: 'select', selectList: {0: '禁用', 1: '启用'}, filter: 'status', templet: admin.table.switch},
                    {field: 'create_time', minWidth: 80, title: '创建时间', align: "center", search: 'range'},
                    {
                        width: 250, align: 'center', title: '操作', init: init, templet: admin.table.tool, operat: ['edit',
                            [
                                {
                                    class: 'layui-btn layui-btn-normal layui-btn-xs',
                                    text: '设置密码',
                                    open: 'system.admin/password',
                                    auth: 'password',
                                    extend: ""
                                }
                            ], 'delete'
                        ]
                    }
                ]],
            });

            admin.listen();
        },
        add: function () {
            admin.listen();
        },
        edit: function () {
            admin.listen();
        },
        password: function () {
            admin.listen();
        }
    };
    return Controller;
});
```

# `init`参数一览表

> 以下参数是`miniAdmin.render();`初始化时进行传入。

| 参数 | 说明 |类型 | 默认值| 备注 |
| --- | --- |--- |--- |--- |
| iniUrl | 初始化接口 | string | null | 实际使用，请对接后端接口动态生成，格式请参考文件：`api/init.json` |
| clearUrl | 缓存清理接口 | string | null | 实际使用，请对接后端接口动态生成，格式请参考文件：`api/init.json` |
| urlHashLocation | 是否打开hash定位 | bool | false | 开启后，会显示路由信息，刷新页面后将定位到当前页|
| bgColorDefault | 主题默认配置 | int | 0 | 如需添加更多主题信息，请在`js/lay-module/layuimini/miniTheme.js`文件内添加|
| multiModule | 是否开启多模块 | bool | false | 个人建议开启 |
| menuChildOpen | 是否默认展开菜单 | bool | false | 个人建议关闭 |
| loadingTime| 初始化加载时间 | 0 | 0 | 建议0-2之间 |
| pageAnim| iframe窗口动画 | bool | false | 添加tab或者切换时的过渡动漫 |
| maxTabNum| 最大的tab打开数量 | int | 20 | 防止打开太多的tab窗口导致页面卡死 |
# 表格内部操作栏的自动生成

# 表格左上方操作栏的自动生成

# 其它api接口

# 自行扩展
