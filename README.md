laravel-admin login-captch
======

Installation
First, install dependencies:

    composer require jianhuawang/login-captcha
 
Configuration
 In the extensions section of the config/admin.php file, add some configuration that belongs to this extension.

    'name' => 'Laravel Admin',
    'html_name' => '<h2 style="color: #ffffff;">Laravel Admin</h3><br/><h3>Login Catpcha</h3>', // Set title by html code. this value is higher priority then "name".

    'logo_img' => '/image/logo.png', // set Logo image on the "name" left.

    'extensions' => [
     'login-captcha' => [
         // set to false if you want to disable this extension
         'enable' => true,
     ]
    ]
     
### 修改中文

    php artisan vendor:publish --tag=lang
    
### 导出验证码配置文件。Export Captchat config file.

    php artisan vendor:publish --provider="Mews\Captcha\CaptchaServiceProvider"

    在配置目录下会生成一个验证码配置文件：
    config/catpcha.php

    修改配置
    ```php
    ...
    'admin' => [
        'length' => 4,
        'width' => 120,
        'height' => 36,
        'quality' => 90,
        'math' => false,
        'expire' => 60,
        'encrypt' => false,
    ],
    ...
    ```
    
### 修改标题样式
    在admin.php中添加html_name可以输入html标签
```php
...
   'name' => 'Laravel Admin',
   'html_name' => '<span style="color: #dddddd;">Laravel Admin</span><br/><span>login captcha</span>',
...
```

### 输入框背景透明化

在config/admin.php 中添加 

	'background' => true,

### 注意事项
<div>
    <table border="0">
	  <tr>
	    <th>Version</th>
	    <th>Laravel-Admin Version</th>
	  </tr>
	  <tr>
	    <td>^1.7.1</td>
	    <td>< 1.6.10</td>
	  </tr>
	  <tr>
            <td>^1.8</td>
            <td>1.6.10 <= 1.7</td>
          </tr>
	  <tr>
            <td>^2.0</td>
            <td>>= 1.7</td>
          </tr>
	</table>
</div> 
