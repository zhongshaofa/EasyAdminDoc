# CURD命令大全

`EasyAdmin`框架以内置快速生成CURD的命令, 包括控制器、视图、模型、JS文件。能够使开发者效率得到进一步提升。

> 备注：在进行CURD命令行之前, 请按照规范设计表结构, 请参数`表结构规范`模块说明。

# 常用命令

```shell
# 生成ea_test_goods表的CURD
php think -t test_goods

# 生成ea_test_goods表的CURD, 文件冲突时强制覆盖
php think -t test_goods -f 1

# 删除ea_test_goods表的CURD
php think -t test_goods -d 1

# 生成ea_test_goods表的CURD, 控制器在目录demo下的Goods.php文件
php think -t test_goods -c demo/Goods

# 生成ea_test_goods表的CURD, 模型在目录demo下的Goods.php文件
php think -t test_goods -m demo/Goods

# 生成ea_test_goods表的CURD, 并关联ea_test_cate表, 并设置外键为cate_id
php think -t test_goods -r test_cate --foreignKey=cate_id --primaryKey=id

# 生成ea_test_goods表的CURD, 并设置logo字段后缀为单图片
php think -t test_goods --imageFieldSuffix=logo

# 生成ea_test_goods表的CURD, 并设置忽略remark, stock字段
php think -t test_goods --ignoreFields=remark --ignoreFields=stock
```

# 参数介绍

| 短参 | 长参 | 说明 | 
| --- | --- |--- |
| -t | --table=VALUE | 主表名 |
| -c | --controllerFilename=VALUE | 控制器文件名 |
| -m | --modelFilename=VALUE | 主表模型文件名 |
| -chfs | --checkboxFieldSuffix=VALUE | 复选框字段后缀 |
| -rafs | --radioFieldSuffix=VALUE | 单选框字段后缀 |
| -imfs | --imageFieldSuffix=VALUE | 单图片字段后缀 |
| -imsfs | --imagesFieldSuffix=VALUE | 多图片字段后缀 |
| -fifs | --fileFieldSuffix=VALUE | 单文件字段后缀 |
| -fisfs | --filesFieldSuffix=VALUE | 多文件字段后缀 |
| -dafs | --dateFieldSuffix=VALUE | 时间字段后缀 |
| -swf | --switchFields=VALUE | 开关的字段 |
| -sef | --selectFileds=VALUE | 下拉的字段 |
| -edf | --editorFields=VALUE | 富文本的字段 |
| -sof | --sortFields=VALUE | 排序的字段 |
| -igf | --ignoreFields=VALUE | 忽略的字段 |
| -r | --relationTable=VALUE | 关联表名 |
| -fkey | --foreignKey=VALUE | 关联外键 |
| -pkey | --primaryKey=VALUE | 关联主键 |
| -remf | --relationModelFilename=VALUE | 关联模型文件名 |
| -f | --force=VALUE | 强制覆盖模式 |
| -d | --delete=VALUE | 删除模式 |
