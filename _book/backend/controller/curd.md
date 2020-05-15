# Curd trait引入

文件位置：`app/admin/traits/Curd.php`

默认的CURD方法有：
* index：列表
* add：添加
* edit：编辑
* del：删除
* modify：属性修改

###使用方法
* 在类里面引入`use \app\admin\traits\Curd;`
* 在类直接引入`use EasyAdmin\annotation\NodeAnotation;`,（备注：因为方法内有使用到权限注解，至少要引入该类，不然会在节点更新的时候报出异常）
* 初始化当前模型

#####示例
```php
<?php
namespace app\admin\controller;

use app\admin\model\SystemConfig;
use app\common\controller\AdminController;
use EasyAdmin\annotation\ControllerAnnotation;
use EasyAdmin\annotation\NodeAnotation;
use think\App;

/**
 * Class Test
 * @package app\admin\controller
 * @ControllerAnnotation(title="测试控制器")
 */
class Test extends AdminController{

    use \app\admin\traits\Curd;
    
    public function __construct(App $app){
        parent::__construct($app);
        $this->model = new SystemConfig();
    }
}
```

#####修改覆盖
因为默认的Curd只能适用于单表，如果不适用你的场景，请复制`app/admin/traits/Curd.php`文件内容到你的控制器覆盖修改。

#####modify属性修改限制
为了安全，modify方法默认允许修改的字段有：
* status
* sort
* remark
* is_delete
* is_auth
* title

如果该方法不适用你的场景请修改：`SystemConstant::ALLOW_MODIFY_FIELD`，或者在modify方法内取消限制。

文件位置：`app/common/constants/SystemConstant.php`

```php
<?php
namespace app\common\constants;

class SystemConstant{

    /**
     * 允许修改的字段值
     */
    const ALLOW_MODIFY_FIELD = [
        'status',
        'sort',
        'remark',
        'is_delete',
        'is_auth',
        'title',
    ];

}
```



