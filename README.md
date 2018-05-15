Yii2 高级模板，配置的后台样式
===============================

[![Latest Stable Version](https://poser.pugx.org/izyue/yii2-app-advanced/v/stable)](https://packagist.org/packages/izyue/yii2-app-advanced)
[![Total Downloads](https://poser.pugx.org/izyue/yii2-app-advanced/downloads)](https://packagist.org/packages/izyue/yii2-app-advanced)
[![License](https://poser.pugx.org/izyue/yii2-app-advanced/license)](https://packagist.org/packages/izyue/yii2-app-advanced)
[![Daily Downloads](https://poser.pugx.org/izyue/yii2-app-advanced/d/daily)](https://packagist.org/packages/izyue/yii2-app-advanced)

### 作者博客

[https://www.izyue.com/yii2-admin](http://www.izyue.com/yii2-admin/)

### 简介

系统基于yii2.0框架开发，保留框架原有的特性，适合作为二次开发的基础系统，也可以直接拿来作为后台系统。管理系统的模块在不断完善中，现有的功能包含，完整的RBAC权限管理~

### 功能

1. 基础功能：登录，登出，密码修改等常见的功能

2. 菜单配置：可视化配置菜单，可以根据配置用户的权限显示隐藏菜单

3. 权限机制：角色、权限增删改查，以及给用户赋予角色权限

4. 规则机制：除了权限角色之外有规则机制，即可以给对应的权限配置规则

5. 二次开发：完全可以基于该系统做二次开发，开发一套适合自己的后台管理系统，节约权限控制以及部分基础功能开发的时间成本，后台系统开发的不二之选

6. 持续更新：新的功能模块会持续更新，请关注

###安装

#### 1. 安装/izyue/Yii2模板
---

```
php composer.phar global require "fxp/composer-asset-plugin:~1.1.1"
php composer.phar create-project --prefer-dist izyue/yii2-app-advanced advanced
```

#### 2. 安装Composer
---

```
composer install
```

#### 3. 导入表结构(migration)
---

需要顺序执行

- 导入rbac migration

```
yii migrate --migrationPath=@yii/rbac/migrations
```
- 导入admin migration

```
yii migrate --migrationPath=@izyue/admin/migrations
```

### 后台登录密码
---

```
User: admin
Password: @newsnow.com.cn@
```

### Admin源码

源码点[这里](https://github.com/liulipeng/Yii2-Admin)

### 自己安装时具体步骤
1.在github克隆下来https://github.com/liulipeng/yii2-app-advanced 
2.在yii2-app-advanced 下运行 ：	composer global require "fxp/composer-asset-plugin:~1.1.1"
				composer create-project --prefer-dist izyue/yii2-app-advanced advanced
3.安装时需要github的token,要有一个github账号，在需要如输入token的时点击第二个链接跳转到github上，在github上生成token再复制到安装需要的地方粘贴再回车，要输入两次token才安装完成
4.之后在yii2-app-advanced 下多出一个advanced文件
5.在advanced文件文件下composer install
6.在advanced文件文件下php init （yii框架初始化选择步骤一致）
7.打开advanced/common/main-local.php的文件（也就是数据库链接配置文件）
8.由第7步得知数据库名称（默认是yii2_admin），在本地【数据库】建一个【数据库】名为第7步知道的数据库名称。
9.在advanced文件文件下执行：先1.php yii migrate --migrationPath=@yii/rbac/migrations 后2.php yii migrate --migrationPath=@izyue/admin/migrations
10：最后在浏览器访问：yii2-app-advanced/advanced文件文件下的backend/web/ (例如:localhost/Other/rabc/yii2-app-advanced/advanced/backend/web/);
11:登录账号密码是：User: admin
		   Password: @newsnow.com.cn@

DIRECTORY STRUCTURE
-------------------

```
common
    config/              contains shared configurations
    mail/                contains view files for e-mails
    models/              contains model classes used in both backend and frontend
console
    config/              contains console configurations
    controllers/         contains console controllers (commands)
    migrations/          contains database migrations
    models/              contains console-specific model classes
    runtime/             contains files generated during runtime
backend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains backend configurations
    controllers/         contains Web controller classes
    models/              contains backend-specific model classes
    runtime/             contains files generated during runtime
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
frontend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains frontend configurations
    controllers/         contains Web controller classes
    models/              contains frontend-specific model classes
    runtime/             contains files generated during runtime
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
    widgets/             contains frontend widgets
vendor/                  contains dependent 3rd-party packages
environments/            contains environment-based overrides
tests                    contains various tests for the advanced application
    codeception/         contains tests developed with Codeception PHP Testing Framework
```
