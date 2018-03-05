## 安装主题
在`hexo`根目录下，执行以下命令
```
git clone git@github.com:itgoyo/hexo-theme-indigoalter.git
```
### 依赖安装
#### Less
主题默认使用 less 作为 css 预处理工具。
```
$ npm install hexo-renderer-less --save
```
#### Feed
用于生成RSS
```
$ npm install hexo-generator-feed --save
```
#### Json-content
用于生成静态站点数据，用作站内搜索的数据源。
```
$ npm install hexo-generator-json-content --save
```
#### QRCode
用于生成分享二维码
```
$ npm install hexo-helper-qrcode --save
```
#### 开启分类页
```
hexo new page tags
```
修改 hexo/source/tags/index.md 的元数据
```
layout: tags
comments: false
---
```
#### 开启分类页
```
hexo new page categories
```
修改 hexo/source/categories/index.md 的元数据
```
layout: categories
comments: false
---
```
---
### 豆瓣电影和书籍
[hexo-douban](https://github.com/mythsman/hexo-douban)
#### 安装
```
npm install hexo-douban --save
```
#### 设置
将下面的配置写入站点的配置文件 `_config.yml` 里(不是主题的配置文件).
```
douban:
  user: itgoyo
  book:
    title: 'This is my book title'
    quote: 'This is my book quote'
  movie:
    title: 'This is my movie title'
    quote: 'This is my movie quote'
  game:
    title: 'This is my game title'
    quote: 'This is my game quote'
  timeout: 10000 #optional
```
- user: 你的豆瓣ID.打开豆瓣，登入账户，然后在右上角点击 "个人主页" ，就可以在这个URL里看到你的ID了: "https://www.douban.com/people/xxxxxx/".
- title: 该页面的标题.
- quote: 写在页面开头的一段话,支持html语法.
- timeout: 爬取数据的超时时间，默认是 10000ms ,如果在使用时发现报了超时的错(ETIMEOUT)可以把这个数据设置的大一点。
如果只想显示某一个页面(比如movie)，那就把其他的配置项注释掉即可。
#### 升级
我会不定期更新一些功能或者修改一些Bug，所以如果想使用最新的特性，可以用下面的方法来更新:
```
$ npm update hexo-douban --save
```
#### 显示
如果上面的配置都没问题，就可以在生成站点之后打开 //yourblog/books 和 //yourblog/movies, //yourblog/games, 来查看结果.
#### 菜单
如果上面的显示没有问题就可以在主题的配置文件 `_config.yml` 里添加如下配置来为这些页面添加菜单链接.
```
menu:
  Home: /
  Archives: /archives
  Books: /books     #This is your books page
  Movies: /movies   #This is your movies page
  Games: /games   #This is your games page
```
