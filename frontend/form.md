# form表单
* form表单已经集成了快速验证以及提交的方法，无需手动重组数据再进行提交
* 默认提交的数据是提交当前url，如需提交到其它页面，修改一下`lay-submit`的值即可
* 在对应的js文件内引入`admin`模块，并执行`admin.listen();`进行监听
#####例子1
```html
{extend name="public:iframe" /}
{block name="cotent"}
<div class="layuimini-container">
    <div class="layuimini-main">
        <form id="app-form" class="layui-form layuimini-form">
            <div class="layui-form-item">
                <label class="layui-form-label required">权限名称</label>
                <div class="layui-input-block">
                    <input type="text" name="title" class="layui-input" lay-verify="required" lay-reqtext="请输入权限名称" placeholder="请输入权限名称" value="">
                </div>
            </div>
            <div class="layui-form-item">
                <div class="layui-input-block">
                    <button type="submit" class="layui-btn layui-btn-sm" lay-submit="" lay-filter="saveForm">确认</button>
                    <button type="reset" class="layui-btn layui-btn-primary layui-btn-sm">重置</button>
                </div>
            </div>
        </form>
    </div>
</div>
{/block}
```

#####例子2
```html
{extend name="public:iframe" /}
{block name="cotent"}
<div class="layuimini-container">
    <div class="layuimini-main">
        <form id="app-form" class="layui-form layuimini-form">
            <div class="layui-form-item">
                <label class="layui-form-label required">权限名称</label>
                <div class="layui-input-block">
                    <input type="text" name="title" class="layui-input" lay-verify="required" lay-reqtext="请输入权限名称" placeholder="请输入权限名称" value="">
                </div>
            </div>
            <div class="layui-form-item">
                <div class="layui-input-block">
                    <button type="submit" class="layui-btn layui-btn-sm" lay-submit="system/testauth" lay-filter="saveForm">确认</button>
                    <button type="reset" class="layui-btn layui-btn-primary layui-btn-sm">重置</button>
                </div>
            </div>
        </form>
    </div>
</div>
{/block}
```