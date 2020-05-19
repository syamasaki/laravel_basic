# 1. Laravelのインストール

* 下記のURLよりLaravel自体のインストールを行う
    * https://readouble.com/laravel/7.x/ja/installation.html

# 2. データベースの設定

* 対応するデータベースの作成

```
CREATE DATABASE `laravel_basic` DEFAULT CHARACTER SET utf8mb4  COLLATE utf8mb4_bin;
```

* utf8mb4対応。app\Providers\AppServiceProvider.phpのboot()にデフォルト文字長を変更(191)

```php

use Illuminate\Support\Facades\Schema;

class AppServiceProvider extends ServiceProvider
{
    /**
     * Bootstrap any application services.
     *
     * @return void
     */
    public function boot()
    {
        // utf8mb4 string index 対策
        Schema::defaultStringLength(191);
    }

    /**
     * Register any application services.
     *
     * @return void
     */
    public function register()
    {
        //
    }
}
```
