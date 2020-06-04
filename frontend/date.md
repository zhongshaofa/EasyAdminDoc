# 时间控件参数

| 参数 | 说明 | 类型 | 是否必填| 默认值 | 备注|
| --- | --- | --- |--- | --- | --- |
| data-date | 开启时间控件 | string | 是 |  | 如果填写值, 此处是 format - 自定义格式 |
| data-date-type | 选择类型 | string | 否 | datetime | |
| data-date-range | 开启范围选择 | string | 否 | - | |

> 相关参数说明

* `data-date-type` 类型有：
    * `year` 年选择器
    * `month` 年月选择
    * `date` 日期选择器
    * `time` 时间选择器
    * `datetime` 日期时间选择器

# 代码示例

```html
<div class="layui-form-item">
    <label class="layui-form-label">上架时间</label>
    <div class="layui-input-block">
        <input type="text" name="up_date" data-date="" data-date-type="date" data-date-range="-" class="layui-input"  placeholder="请选择上架时间" value="">
    </div>
</div>>
```