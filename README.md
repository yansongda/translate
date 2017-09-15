<h1 align="center">Translate</h1>

翻译的 SDK

## 安装
`composer require yansongda/translate`

## 对外接口
- trans(string $q, string $to, string $from = 'auto')  
$q: 待翻译的字符串  
$to: 目的语言    可选 - 默认 英文
$from: 源语言   可选 - 默认 auto

- pinyin(string $q)
$q: 待转换为拼音的字符串  

## 使用方法
```php
<?php

use Yansongda\Translate\Translate;

$config = [
    'log' => '/tmp/translate.log',

    'gateways' => [
        'baidu' => [
            'appid' => 'xxxx',
            'appsecret' => 'xxxx',
        ],
        'youdao' => [
            'appid' => 'xxxx',
            'appsecret' => 'xxxx',
        ],
    ],
    
];

$t = new Translate($config);

// 翻译
echo $t->trans("你好");

// 拼音
echo $t->pinyin("你好");
```

支持的翻译列表请传送至 [这里](http://api.fanyi.baidu.com/api/trans/product/apidoc)

## License
MIT