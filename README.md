# aox_proxy_pool | Ip代理池项目
本项目是为了解决在抓取代理ip后, 代理ip失效快, 不稳定的问题 以及代理ip使用不方便等问题。

1. 可以自己去增加抓取的代理ip网站, 项目会自动去重, 并且之前抓取过的ip会保存在数据库中, 不会删除, 所以放心不会出现重复抓取的问题
2. 通过校验服务器开放的端口、访问的速度、校验多个网址访问的情况来对代理ip设置权重排序, 达到过滤垃圾ip的目的, 运行一段时间后剩下的ip, 则可以进入使用, 而且实测比较稳定
3. 通过脚本自动更新squid配置文件, 这样使用的客户端只需要指定squid服务器的地址即可。

## 功能特色

1. 可自行增加代理抓取渠道
2. ip校验模块
3. squid配置自动更新
4. 客户端使用简单

## 运行环境
1. python 3.6
2. pipenv
3. scrapy模块
3. mysql5.6

## 运行部署
1. 克隆代码
```
git clone "https://github.com/aox-lei/aox_proxy_pool"
```

2. 本机安装python3.6、pip、pipenv、mysql
3. 安装虚拟环境以及python模块
```
> pipenv --three
> pipenv shell
> pipenv install 
```
4. 复制配置文件
```
> cp proxy_pool/config.ini.default proxy_pool/config.ini
```
5. 修改配置信息
6. 运行抓取项目
```
> scrapy crawl xici
> scrapy crawl kuaidaili
> scrapy crawl ip66
```
7. 运行ip检测
```
> python manager.py check_proxy
```
8. 运行squid同步

## 目前支持的抓取网站
1. 西祠代理
2. 快代理
3. ip66

如果有什么新的好一些的免费代理网站, 可以提ISSUE或者qq:2387813033, 微信: 18500402623
