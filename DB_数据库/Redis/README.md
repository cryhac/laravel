```
'default' => [
    'host' => env('REDIS_HOST', '127.0.0.1'),
    'password' => env('REDIS_PASSWORD', null),
    'port' => env('REDIS_PORT', 6379),
    'database' => env('REDIS_DATABASE', 0),
    //不超时
    'read_write_timeout' => '-1',
    'options' => [
        'prefix' => env('REDIS_PREFIX', ''),
    ]
],
```

- 如果上面前缀不起作用，那就放出来吧
```
    'redis' => [
        'client' => 'predis',
        'cluster' => false,
        'options' => [
            'prefix' => env('REDIS_PREFIX', 'product-centre'),
        ],
        'default' => [
            'host' => env('REDIS_HOST', 'localhost'),
            'password' => env('REDIS_PASSWORD', null),
            'port' => env('REDIS_PORT', 6379),
            'database' => 0,

        ],
        // session 专用
        'session' => [
            'host' => env('REDIS_HOST', 'localhost'),
            'password' => env('REDIS_PASSWORD', null),
            'port' => env('REDIS_PORT', 6379),
            'database' => 2,
        ],

    ],
```

```
确保 .env 文件中 CACHE_DRIVER=redis ,更改缓存驱动为Redis

默认的缓存前缀为 laravel ，如果想要修改前缀可以在 config/cache.php 配置文件中 'prefix' => 'laravel' ，修改此项即可。

Laravel默认使用的Redis数据库为 db0 ，你也可以指定其他数据库，在 config/database.php 配置文件中。
```
